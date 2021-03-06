---
title: 使用 Microsoft Graph Sdk 上载大型文件
description: 提供使用 Microsoft Graph Sdk 上载大型文件的指南。
localization_priority: Normal
author: DarrelMiller
ms.openlocfilehash: 44465dcc22dcd84c78ee8aa7abfc1f6dc9e36c8a
ms.sourcegitcommit: 3c8a92d89ac60a48cb63449976b1c3c2c6302281
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44743997"
---
# <a name="upload-large-files-using-the-microsoft-graph-sdks"></a>使用 Microsoft Graph Sdk 上载大型文件

Microsoft Graph 中的多个实体支持可恢复的[文件上载](/graph/api/driveitem-createuploadsession?view=graph-rest-1.0)，以便更轻松地上传大文件。 不是尝试在单个请求中上传整个文件，而是将该文件切片成更小的部分，并使用一个请求来上载单个切片。 为了简化此过程，Microsoft Graph Sdk 实施了一个大型文件上传任务，用于管理切片的上载。

## <a name="c"></a>[C#](#tab/csharp)

```csharp
using (var fileStream = System.IO.File.OpenRead(filePath))
{
    // Use properties to specify the conflict behavior
    // in this case, replace
    var uploadProps = new DriveItemUploadableProperties
    {
        ODataType = null,
        AdditionalData = new Dictionary<string, object>
        {
            { "@microsoft.graph.conflictBehavior", "replace" }
        }
    };

    // Create the upload session
    // itemPath does not need to be a path to an existing item
    var uploadSession = await graphClient.Me.Drive.Root
        .ItemWithPath(itemPath)
        .CreateUploadSession(uploadProps)
        .Request()
        .PostAsync();

    // Max slice size must be a multiple of 320 KiB
    int maxSliceSize = 320 * 1024;
    var fileUploadTask =
        new LargeFileUploadTask<DriveItem>(uploadSession, fileStream, maxSliceSize);

    // Create a callback that is invoked after each slice is uploaded
    IProgress<long> progress = new Progress<long>(progress => {
        Console.WriteLine($"Uploaded {progress} bytes of {fileStream.Length} bytes");
    });

    try
    {
        // Upload the file
        var uploadResult = await fileUploadTask.UploadAsync(progress);

        if (uploadResult.UploadSucceeded)
        {
            // The ItemResponse object in the result represents the
            // created item.
            Console.WriteLine($"Upload complete, item ID: {uploadResult.ItemResponse.Id}");
        }
        else
        {
            Console.WriteLine("Upload failed");
        }
    }
    catch (ServiceException ex)
    {
        Console.WriteLine($"Error uploading: {ex.ToString()}");
    }
}
```

## <a name="typescript"></a>[TypeScript](#tab/typescript)

```typescript
const options: any = {
    // Relative path from root to destination folder
    path: itemPath,
    // file is a File object, typically from an <input type="file"/>
    fileName: file.name,
    rangeSize: 320 * 1024
  }

  try {
    const uploadTask: MicrosoftGraph.OneDriveLargeFileUploadTask =
      await MicrosoftGraph.OneDriveLargeFileUploadTask.create(client, file, options);

    const uploadedFile: DriveItem = await uploadTask.upload();

    console.log(JSON.stringify(`Uploaded file with ID: ${uploadedFile.id}`));
    return `Uploaded file with ID: ${uploadedFile.id}`;
  } catch (err) {
    console.log(`Error uploading file: ${JSON.stringify(err)}`);
    return `Error uploading file: ${JSON.stringify(err)}`;
  }
}
```

## <a name="java"></a>[Java](#tab/java)

```java
// Get an input stream for the file
File file = new File(localFilePath);
InputStream fileStream = new FileInputStream(file);
long streamSize = file.length();

// Create a callback used by the upload provider
IProgressCallback<DriveItem> callback = new IProgressCallback<DriveItem>() {
    @Override
    // Called after each slice of the file is uploaded
    public void progress(final long current, final long max) {
        System.out.println(
            String.format("Uploaded %d bytes of %d total bytes", current, max)
        );
    }

    @Override
    public void success(final DriveItem result) {
        System.out.println(
            String.format("Uploaded file with ID: %s", result.id)
        );
    }

    public void failure(final ClientException ex) {
        System.out.println(
            String.format("Error uploading file: %s", ex.getMessage())
        );
    }
};

// Create an upload session
UploadSession uploadSession = graphClient
    .me()
    .drive()
    .root()
    // itemPath like "/Folder/file.txt"
    // does not need to be a path to an existing item
    .itemWithPath(itemPath)
    .createUploadSession(new DriveItemUploadableProperties())
    .buildRequest()
    .post();

ChunkedUploadProvider<DriveItem> chunkedUploadProvider =
    new ChunkedUploadProvider<DriveItem>
        (uploadSession, graphClient, fileStream, streamSize, DriveItem.class);

// Config parameter is an array of integers
// customConfig[0] indicates the max slice size
// Max slice size must be a multiple of 320 KiB
int[] customConfig = { 320 * 1024 };

// Do the upload
chunkedUploadProvider.upload(callback, customConfig);
```

---

## <a name="resuming-a-file-upload"></a>恢复文件上传

Microsoft Graph Sdk 支持[恢复正在进行的上载](/graph/api/driveitem-createuploadsession?view=graph-rest-1.0#resuming-an-in-progress-upload)。 如果您的应用程序在上载过程中遇到连接中断或 5. x HTTP 状态，则可以恢复上载。

<!-- markdownlint-disable MD024 -->
### <a name="c"></a>[C#](#tab/csharp)

```csharp
fileUploadTask.ResumeAsync(progress);
```

### <a name="typescript"></a>[TypeScript](#tab/typescript)

```typescript
const resumedFile: DriveItem = await uploadTask.resume();
```

### <a name="java"></a>[Java](#tab/java)

> [!NOTE]
> Java SDK 目前不支持恢复正在进行的下载。

---
<!-- markdownlint-enable MD024 -->
