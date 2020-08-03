---
id: "working-with-folder-api"
url: "comparison/working-with-folder-api"
title: "Working with Folder API"
productName: "GroupDocs.Comparison Cloud"
weight: 6
description: ""
keywords: ""
---






# Get the File Listing of a Specific Folder #

This API allows you to get a list of all files of a specific folder from the specified Cloud Storage. If you do not pass storage name API will find folder in GroupDocs Cloud Storage. 

## API Explorer ##

[GroupDocs.Comparison Cloud API Reference](https://apireference.groupdocs.cloud/comparison/) lets you to try out [List Files in a Folder API](https://apireference.groupdocs.cloud/comparison/#/Folder/GetFilesList) right away in your browser. It allows you to effortlessly interact and try out every single operation that our APIs exposes.
|---|---|---|---

### Request parameters ###

|Parameter|Description
|---|---
|**path**|Path of the file including file name and extension e.g. /Folder1/file.ext

Required. Can be passed as query string parameter or as part of the URL
|storageName|Name of the storage. If not set, then default storage used


## cURL Example ##





 Request

```html
curl -X GET "https://api.groupdocs.cloud/v2.0/comparison/storage/folder/comparisondocs?storageName#MyStorage" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"

 ```




 Response

```html
{
  "value": [
    {
      "name": "four-pages.docx",
      "isFolder": false,
      "modifiedDate": "2019-03-20T12:35:38+00:00",
      "size": 8651,
      "path": "/comparisondocs/four-pages.docx"
    },
    {
      "name": "one-page.docx",
      "isFolder": false,
      "modifiedDate": "2019-03-20T12:17:34+00:00",
      "size": 351348,
      "path": "/comparisondocs/one-page.docx"
    },
    {
      "name": "password-protected.docx",
      "isFolder": false,
      "modifiedDate": "2019-03-20T12:35:40+00:00",
      "size": 10240,
      "path": "/comparisondocs/password-protected.docx"
    },
    {
      "name": "sample.mpp",
      "isFolder": false,
      "modifiedDate": "2019-03-20T12:29:10+00:00",
      "size": 289792,
      "path": "/comparisondocs/sample.mpp"
    },
    {
      "name": "three-layouts.dwf",
      "isFolder": false,
      "modifiedDate": "2019-03-20T12:26:42+00:00",
      "size": 15433,
      "path": "/comparisondocs/three-layouts.dwf"
    },
    {
      "name": "two-hidden-pages.vsd",
      "isFolder": false,
      "modifiedDate": "2019-03-20T12:17:36+00:00",
      "size": 457728,
      "path": "/comparisondocs/two-hidden-pages.vsd"
    },
    {
      "name": "uses-custom-font.pptx",
      "isFolder": false,
      "modifiedDate": "2019-03-20T12:32:30+00:00",
      "size": 39823,
      "path": "/comparisondocs/uses-custom-font.pptx"
    },
    {
      "name": "with-hidden-rows-and-columns.xlsx",
      "isFolder": false,
      "modifiedDate": "2019-03-20T12:17:37+00:00",
      "size": 15986,
      "path": "/comparisondocs/with-hidden-rows-and-columns.xlsx"
    }
  ]
}


 ```






## SDKs ##

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-comparison-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-comparison-cloud), it hides the [Folder API](https://apireference.groupdocs.cloud/comparison/#/Folder) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.
|---|---|---|---|---|---

### SDK Examples ###





C# 




{{< gist groupdocscloud 622c78dd86e4c5ade7e870295b6db376 Comparison_CSharp_Get_Files_List.cs >}}







Java  




{{< gist groupdocscloud fcf2013d068abf714662f99cba3c0d47 Comparison_Java_Get_Files_List.Java  >}}







PHP 




{{< gist groupdocscloud 24ad96946345493cb230d7124f22c176 Comparison_Php_Get_Files_List.php >}}







Ruby  




{{< gist groupdocscloud f830f503cb44c7aa38a757cb86b34f5d Comparison_Ruby_Get_Files_List.rb >}}







 Node.js




{{< gist groupdocscloud 7999207c55ecfba6c2a125f5b77ca0d8 Comparison_Node_Get_Files_List.js >}}







 Python




{{< gist groupdocscloud 5b471172e33a251d70b08127085d200e Comparison_Python_Get_Files_List.py >}}









# Create a New Folder #

This API allows you to create a new Folder in the specified Cloud Storage. If you do not pass storage name API will create new Folder in default Cloud Storage.

## API Explorer ##

[GroupDocs.Comparison Cloud API Reference](https://apireference.groupdocs.cloud/comparison/) lets you to try out [Create Folder API](https://apireference.groupdocs.cloud/comparison/#/Folder/CreateFolder) right away in your browser. It allows you to effortlessly interact and try out every single operation that our APIs exposes.
|---|---|---|---


### Request parameters ###

|Parameter|Description
|---|---
|**path**|Target folder’s path e.g. Folder1/Folder2/. The folders will be created recursively

Required. Can be passed as query string parameter or as part of the URL
|storageName|Name of the storage. If not set, then default storage used


## cURL Example ##





 Request

```html
curl -X POST "https://api.groupdocs.cloud/v2.0/comparison/storage/folder/comparisondocs?storageName#MyStorage" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"

 ```




 Response

```html
{  
  "code": 200,
  "status": "OK"
}
 ```






## SDKs ##

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-comparison-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-comparison-cloud), it hides the [Folder API](https://apireference.groupdocs.cloud/comparison/#/Folder/) calls and lets you use GroupDocs for Cloud features in a native way for your preferred language.
|---|---|---|---|---|---

### SDK Examples ###





C# 




{{< gist groupdocscloud 622c78dd86e4c5ade7e870295b6db376 Comparison_CSharp_Create_Folder.cs >}}







Java  




{{< gist groupdocscloud fcf2013d068abf714662f99cba3c0d47 Comparison_Java_Create_Folder.Java  >}}







PHP 




{{< gist groupdocscloud 24ad96946345493cb230d7124f22c176 Comparison_Php_Create_Folder.php >}}







Ruby  




{{< gist groupdocscloud f830f503cb44c7aa38a757cb86b34f5d Comparison_Ruby_Create_Folder.rb >}}







 Node.js




{{< gist groupdocscloud 7999207c55ecfba6c2a125f5b77ca0d8 Comparison_Node_Create_Folder.js >}}







 Python




{{< gist groupdocscloud 5b471172e33a251d70b08127085d200e Comparison_Python_Create_Folder.py >}}









# Delete a Particular Folder #

This API allows you to delete a particular Folder in the specified Cloud Storage. If you do not pass storage name API will create new Folder in default Cloud Storage. To remove recursively inner folder/files you need to pass true value to recursive parameter in Request. If it is set to false and folder contains data then API throws the exception.

## API Explorer ##

[GroupDocs.Comparison Cloud API Reference](https://apireference.groupdocs.cloud/comparison/#/) lets you to try out [Delete a Particular Folder API](https://apireference.groupdocs.cloud/comparison/#/Folder/DeleteFolder) right away in your browser. It allows you to effortlessly interact and try out every single operation that our APIs exposes. 
|---|---|---|---


### Request parameters ###

|Parameter|Description
|---|---
|**path**|Folder path e.g. /Folder1

Required. Can be passed as query string parameter or as part of the URL
|storageName|Name of the storage. If not set, then default storage used


## cURL Example ##





 Request

```html
curl -X DELETE "https://api.groupdocs.cloud/v2.0/comparison/storage/folder/comparisondocs?storageName#MyStorage&#x26;recursive#true" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"

 ```




 Response

```html
{  
  "code": 200,
  "status": "OK"
}
 ```






## SDKs ##

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-comparison-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-comparison-cloud), it hides the [Delete Folder API](https://apireference.groupdocs.cloud/comparison/#/Folder/DeleteFolder) calls and lets you use GroupDocs for Cloud features in a native way for your preferred language.
|---|---|---|---|---|---

### SDK Examples ###





C# 




{{< gist groupdocscloud 622c78dd86e4c5ade7e870295b6db376 Comparison_CSharp_Delete_Folder.cs >}}







Java  




{{< gist groupdocscloud fcf2013d068abf714662f99cba3c0d47 Comparison_Java_Delete_Folder.Java  >}}







PHP 




{{< gist groupdocscloud 24ad96946345493cb230d7124f22c176 Comparison_Php_Delete_Folder.php >}}







Ruby  




{{< gist groupdocscloud f830f503cb44c7aa38a757cb86b34f5d Comparison_Ruby_Delete_Folder.rb >}}







 Node.js




{{< gist groupdocscloud 7999207c55ecfba6c2a125f5b77ca0d8 Comparison_Node_Delete_Folder.js >}}







 Python




{{< gist groupdocscloud 5b471172e33a251d70b08127085d200e Comparison_Python_Delete_Folder.py >}}









# Copy  Specific Folder #

This API allows you to copy a Folder to another location in the GroupDocs Cloud Storage. If you do not pass source and destination storage names API will copy Folder within default Cloud Storage.

## API Explorer ##

[GroupDocs.Comparison Cloud API Reference](https://apireference.groupdocs.cloud/comparison/#/) lets you to try out [Copy Folder API](https://apireference.groupdocs.cloud/comparison/#/Folder/CopyFolder) right away in your browser. It allows you to effortlessly interact and try out every single operation that our APIs exposes.
|---|---|---|---

### Request parameters ###

|Parameter|Description
|---|---
|**srcPath**|Source folder path e.g. /Folder1

Required. Can be passed as query string parameter or as part of the URL
|**destPath**|Destination folder path. Required
|srcStorageName|Name of the storage of source folder. If not set, then default storage used
|destStorageName|Name of the storage of destination folder. If not set, then default storage used


## cURL Example ##





 Request

```html
curl -X PUT "https://api.groupdocs.cloud/v2.0/comparison/storage/folder/copy/comparisondocs?destPath#comparisondocs&#x26;srcStorageName#MyStorage&#x26;destStorageName#MyStorage" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"

 ```




 Response

```html
{  
  "code": 200,
  "status": "OK"
}
 ```






## SDKs ##

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-comparison-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-comparison-cloud), it hides the [Copy Folder API](https://apireference.groupdocs.cloud/comparison/#/Folder/CopyFolder) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.
|---|---|---|---|---|---

### SDK Examples ###





C# 




{{< gist groupdocscloud 622c78dd86e4c5ade7e870295b6db376 Comparison_CSharp_Copy_Folder.cs >}}







Java  




{{< gist groupdocscloud fcf2013d068abf714662f99cba3c0d47 Comparison_Java_Copy_Folder.Java  >}}







PHP 




{{< gist groupdocscloud 24ad96946345493cb230d7124f22c176 Comparison_Php_Copy_Folder.php >}}







Ruby  




{{< gist groupdocscloud f830f503cb44c7aa38a757cb86b34f5d Comparison_Ruby_Copy_Folder.rb >}}







 Node.js




{{< gist groupdocscloud 7999207c55ecfba6c2a125f5b77ca0d8 Comparison_Node_Copy_Folder.js >}}







 Python




{{< gist groupdocscloud 5b471172e33a251d70b08127085d200e Comparison_Python_Copy_Folder.py >}}









# Move a Specific Folder #

This API allows you to move a Folder to another location in the GroupDocs Cloud Storage. If you do not pass source and destination storage names API will move Folder within default Cloud Storage.

## API Explorer ##

[GroupDocs.Comparison Cloud API Reference](https://apireference.groupdocs.cloud/comparison/#/) lets you to try out [Move a Folder API](https://apireference.groupdocs.cloud/comparison/#/Folder/MoveFolder) right away in your browser. It allows you to effortlessly interact and try out every single operation that our APIs exposes.
|---|---|---|---

### Request parameters ###

|Parameter|Description
|---|---
|**srcPath**|Source folder path e.g. /Folder1

Required. Can be passed as query string parameter or as part of the URL
|**destPath**|Destination folder path. Required
|srcStorageName|Name of the storage of source folder. If not set, then default storage used
|destStorageName|Name of the storage of destination folder. If not set, then default storage used


## cURL Example ##





 Request

```html
curl -X PUT "https://api.groupdocs.cloud/v2.0/comparison/storage/folder/move/comparisondocs?destPath#comparisondocs1&#x26;srcStorageName#MyStorage&#x26;destStorageName#MyStorage" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"  
 ```




 Response

```html
{  
  "code": 200,
  "status": "OK"
}
 ```






## SDKs ##

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-comparison-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-comparison-cloud), it hides the [Move Folder API](https://apireference.groupdocs.cloud/comparison/#/Folder/MoveFolder) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.
|---|---|---|---|---|---

### SDK Examples ###





C# 




{{< gist groupdocscloud 622c78dd86e4c5ade7e870295b6db376 Comparison_CSharp_Move_Folder.cs >}}







Java  




{{< gist groupdocscloud fcf2013d068abf714662f99cba3c0d47 Comparison_Java_Move_Folder.Java  >}}







PHP 




{{< gist groupdocscloud 24ad96946345493cb230d7124f22c176 Comparison_Php_Move_Folder.php >}}







Ruby  




{{< gist groupdocscloud f830f503cb44c7aa38a757cb86b34f5d Comparison_Ruby_Move_Folder.rb >}}







 Node.js




{{< gist groupdocscloud 7999207c55ecfba6c2a125f5b77ca0d8 Comparison_Node_Move_Folder.js >}}







 Python




{{< gist groupdocscloud 5b471172e33a251d70b08127085d200e Comparison_Python_Move_Folder.py >}}







