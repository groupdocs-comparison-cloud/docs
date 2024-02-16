---
id: "working-with-file-api"
url: "comparison/working-with-file-api"
title: "Working with File Api"
productName: "GroupDocs.Comparison Cloud"
weight: 5
description: ""
keywords: ""
toc: True
---

This API allows you to download a file from [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud).

## API Explorer

[GroupDocs.Comparison Cloud API Reference](https://apireference.groupdocs.cloud/comparison/#/) lets you to try out [Download a File API](https://apireference.groupdocs.cloud/comparison/#/File/DownloadFile) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs exposes.

### Request parameters

|Parameter|Description
|---|---
|**Path**|Path of the file including file name and extension e.g. /Folder1/file.ext Required. Can be passed as query string parameter or as part of the URL
|**storageName**|Name of the storage. If not set, then default storage used
|**versionId**|File version id

### cURL example

{{< tabs "example1">}} {{< tab "Request" >}}

```bash
curl -X GET "https://api.groupdocs.cloud/v2.0/comparison/storage/file/one-page.docx?storageName#MyStorage" -H  "accept: multipart/form-data" -H  "authorization: Bearer [Access Token]"

```

{{< /tab >}} {{< tab "Response" >}}

```json
{
  "Code": 200,
  "Status": "OK"
}
```
{{< /tab >}} {{< /tabs >}}

### SDK example

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-comparison-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-comparison-cloud), it hides the [File API](https://apireference.groupdocs.cloud/comparison/#/) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.


{{< tabs "example2">}} {{< tab "C#" >}}

{{< gist groupdocscloud 622c78dd86e4c5ade7e870295b6db376 Comparison_CSharp_Download_File.cs >}}

{{< /tab >}} {{< tab "Java" >}}

{{< gist groupdocscloud fcf2013d068abf714662f99cba3c0d47 Comparison_Java_Download_File.java >}}

{{< /tab >}} {{< tab "PHP" >}}

{{< gist groupdocscloud 24ad96946345493cb230d7124f22c176 Comparison_Php_Download_File.php >}}

{{< /tab >}} {{< tab "Ruby" >}}

{{< gist groupdocscloud f830f503cb44c7aa38a757cb86b34f5d Comparison_Ruby_Download_File.rb >}}

{{< /tab >}} {{< tab "Node.js" >}}

{{< gist groupdocscloud 7999207c55ecfba6c2a125f5b77ca0d8 Comparison_Node_Download_File.js >}}

{{< /tab >}} {{< tab "Python" >}}

{{< gist groupdocscloud 5b471172e33a251d70b08127085d200e Comparison_Python_Download_File.py >}}

{{< /tab >}} {{< /tabs >}}

##  Upload File API

This API allows you to upload files to the [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud/).

### API Explorer

[GroupDocs.Comparison Cloud API Reference](https://apireference.groupdocs.cloud/comparison/#/) lets you try out [Upload a File API](https://apireference.groupdocs.cloud/comparison/#/File/UploadFile) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs exposes.

### Request Body parameters

|Parameter|Description
|---|---
|**path**|Path of the file including file name and extension e.g. /Folder1/file.ext Required. Can be passed as query string parameter or as part of the URL
|storageName|Name of the storage. If not set, then default storage used
|File|File content

### cURL example

{{< tabs "example3">}} {{< tab "Request" >}}

```bash
curl -X POST "https://api.groupdocs.cloud/v2.0/comparison/storage/file/comparisondocs%2Fone-page2.docx?storageName#MyStorage" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"

```

{{< /tab >}} {{< tab "Response" >}}

```json
Http status code: 200 (Returns OK and list of errors, which is empty if success.)
{
  "Uploaded": [
    "string"
  ],
  "Errors": [
    {
      "Code": "string",
      "Message": "string",
      "Description": "string",
      "InnerError": {
        "RequestId": "string",
        "Date": "2019-02-27T06:10:08.884Z"
      }
    }
  ]
}
```
{{< /tab >}} {{< /tabs >}}

### SDK example

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-comparison-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-comparison-cloud), it hides the [File API](https://apireference.groupdocs.cloud/comparison/#/File) calls and lets you use GroupDocs for Cloud features in a native way for your preferred language.

{{< tabs "example4">}} {{< tab "C#" >}}

{{< gist groupdocscloud 622c78dd86e4c5ade7e870295b6db376 Comparison_CSharp_Upload_File.cs >}}

{{< /tab >}} {{< tab "Java" >}}

{{< gist groupdocscloud fcf2013d068abf714662f99cba3c0d47 Comparison_Java_Upload_File.java >}}

{{< /tab >}} {{< tab "PHP" >}}

{{< gist groupdocscloud 24ad96946345493cb230d7124f22c176 Comparison_Php_Upload_File.php >}}

{{< /tab >}} {{< tab "Ruby" >}}

{{< gist groupdocscloud f830f503cb44c7aa38a757cb86b34f5d Comparison_Ruby_Upload_File.rb >}}

{{< /tab >}} {{< tab "Node.js" >}}

{{< gist groupdocscloud 7999207c55ecfba6c2a125f5b77ca0d8 Comparison_Node_Upload_File.js >}}

{{< /tab >}} {{< tab "Python" >}}

{{< gist groupdocscloud 5b471172e33a251d70b08127085d200e Comparison_Python_Upload_File.py >}}

{{< /tab >}} {{< /tabs >}}

## Delete File API

This API allows you to delete specific file from [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud/).

### API Explorer

[GroupDocs.Comparison Cloud API Reference](https://apireference.groupdocs.cloud/comparison/#/) lets you to try out [Delete a File](https://apireference.groupdocs.cloud/comparison/#/File/DeleteFile) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs exposes.

### Request parameters

|Parameter|Description
|---|---
|**path**|Path of the file including file name and extension e.g. /Folder1/file.ext Required. Can be passed as query string parameter or as part of the URL
|storageName|Name of the storage. If not set, then default storage used
|versionId|File version id

### cURL example

{{< tabs "example5">}} {{< tab "Request" >}}

```bash
curl -X DELETE "https://api.groupdocs.cloud/v2.0/comparison/storage/file/comparisondocs%2Fone-page1.docx?storageName#MyStorage" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"
```

{{< /tab >}} {{< tab "Response" >}}

```json
{
  "Code": 200,
  "Status": "OK"
}
```
{{< /tab >}} {{< /tabs >}}

### SDK example

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-comparison-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-comparison-cloud), it hides the [File API](https://apireference.groupdocs.cloud/comparison/#/File) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.

{{< tabs "example6">}} {{< tab "C#" >}}

{{< gist groupdocscloud 622c78dd86e4c5ade7e870295b6db376 Comparison_CSharp_Delete_File.cs >}}

{{< /tab >}} {{< tab "Java" >}}

{{< gist groupdocscloud fcf2013d068abf714662f99cba3c0d47 Comparison_Java_Delete_File.java >}}

{{< /tab >}} {{< tab "PHP" >}}

{{< gist groupdocscloud 24ad96946345493cb230d7124f22c176 Comparison_Php_Delete_File.php >}}

{{< /tab >}} {{< tab "Ruby" >}}

{{< gist groupdocscloud f830f503cb44c7aa38a757cb86b34f5d Comparison_Ruby_Delete_File.rb >}}

{{< /tab >}} {{< tab "Node.js" >}}

{{< gist groupdocscloud 7999207c55ecfba6c2a125f5b77ca0d8 Comparison_Node_Delete_File.js >}}

{{< /tab >}} {{< tab "Python" >}}

{{< gist groupdocscloud 5b471172e33a251d70b08127085d200e Comparison_Python_Delete_File.py >}}

{{< /tab >}} {{< /tabs >}}

## File Copy API

This API allows you to copy specific file from [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud/).

### API Explorer

[GroupDocs.Comparison Cloud API Reference](https://apireference.groupdocs.cloud/comparison/#/) lets you to try out [Copy File](https://apireference.groupdocs.cloud/comparison/#/File/CopyFile) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs exposes.

###  Request parameters

|Parameter|Description
|---|---
|**srcPath**|Path of the source file including file name and extension e.g. /Folder1/file.ext Required. Can be passed as query string parameter or as part of the URL
|**destPath**|Path of the destination file. Required.
|srcStorageName|Name of the storage of source file. If not set, then default storage used
|destStorageName|Name of the storage of destination file. If not set, then default storage used
|versionId|Source file version id

### cURL example

{{< tabs "example7">}} {{< tab "Request" >}}

```bash
curl -X PUT "https://api.groupdocs.cloud/v2.0/comparison/storage/file/copy/comparisondocs%2Fone-page1.docx?destPath#comparisondocs%2Fone-page1.docx'&#x26;srcStorageName#MyStorage&#x26;destStorageName#MyStorage" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"

```

{{< /tab >}} {{< tab "Response" >}}

```json
{
  "Code": 200,
  "Status": "OK"
}
```
{{< /tab >}} {{< /tabs >}}

### SDK example

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-comparison-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-comparison-cloud), it hides the [File API](https://apireference.groupdocs.cloud/comparison/#/File) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.


{{< tabs "example8">}} {{< tab "C#" >}}

{{< gist groupdocscloud 622c78dd86e4c5ade7e870295b6db376 Comparison_CSharp_Copy_File.cs >}}

{{< /tab >}} {{< tab "Java" >}}

{{< gist groupdocscloud fcf2013d068abf714662f99cba3c0d47 Comparison_Java_Copy_File.java >}}

{{< /tab >}} {{< tab "PHP" >}}

{{< gist groupdocscloud 24ad96946345493cb230d7124f22c176 Comparison_Php_Copy_File.php >}}

{{< /tab >}} {{< tab "Ruby" >}}

{{< gist groupdocscloud f830f503cb44c7aa38a757cb86b34f5d Comparison_Ruby_Copy_File.rb >}}

{{< /tab >}} {{< tab "Node.js" >}}

{{< gist groupdocscloud 7999207c55ecfba6c2a125f5b77ca0d8 Comparison_Node_Copy_File.js >}}

{{< /tab >}} {{< tab "Python" >}}

{{< gist groupdocscloud 5b471172e33a251d70b08127085d200e Comparison_Python_Copy_File.py >}}

{{< /tab >}} {{< /tabs >}}

## File Move API

This API allows you to copy specific file from [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud/).

### API Explorer

[GroupDocs.Comparison Cloud API Reference](https://apireference.groupdocs.cloud/comparison/#/) lets you to try out [Move File](https://apireference.groupdocs.cloud/comparison/#/File/MoveFile) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs exposes.

###  Request parameters

|Parameter|Description
|---|---
|**srcPath**|Path of the source file including file name and extension e.g. /Folder1/file.ext Required. Can be passed as query string parameter or as part of the URL
|**destPath**|Path of the destination file. Required.
|srcStorageName|Name of the storage of source file. If not set, then default storage used
|destStorageName|Name of the storage of destination file. If not set, then default storage used
|versionId|Source file version id

### cURL example

{{< tabs "example9">}} {{< tab "Request" >}}

```bash
curl -X PUT "https://api.groupdocs.cloud/v2.0/comparison/storage/file/move/comparisondocs%2Fone-page1.docx?destPath#comparisondocs%2Fone-page1.docx'&#x26;srcStorageName#MyStorage&#x26;destStorageName#MyStorage" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"

```

{{< /tab >}} {{< tab "Response" >}}

```json
{
  "Code": 200,
  "Status": "OK"
}
```
{{< /tab >}} {{< /tabs >}}

### SDK example

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-comparison-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-comparison-cloud), it hides the [File API](https://apireference.groupdocs.cloud/comparison/#/File) calls and lets you use GroupDocs for Cloud features in a native way for your preferred language.

{{< tabs "example10">}} {{< tab "C#" >}}

{{< gist groupdocscloud 622c78dd86e4c5ade7e870295b6db376 Comparison_CSharp_Move_File.cs >}}

{{< /tab >}} {{< tab "Java" >}}

{{< gist groupdocscloud fcf2013d068abf714662f99cba3c0d47 Comparison_Java_Move_File.java >}}

{{< /tab >}} {{< tab "PHP" >}}

{{< gist groupdocscloud 24ad96946345493cb230d7124f22c176 Comparison_Php_Move_File.php >}}

{{< /tab >}} {{< tab "Ruby" >}}

{{< gist groupdocscloud f830f503cb44c7aa38a757cb86b34f5d Comparison_Ruby_Move_File.rb >}}

{{< /tab >}} {{< tab "Node.js" >}}

{{< gist groupdocscloud 7999207c55ecfba6c2a125f5b77ca0d8 Comparison_Node_Move_File.js >}}

{{< /tab >}} {{< tab "Python" >}}

{{< gist groupdocscloud 5b471172e33a251d70b08127085d200e Comparison_Python_Move_File.py >}}

{{< /tab >}} {{< /tabs >}}
