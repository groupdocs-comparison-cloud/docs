---
id: "get-document-information"
url: "comparison/get-document-information"
title: "Get Document Information"
productName: "GroupDocs.Comparison Cloud"
description: ""
keywords: ""
toc: True
---

This REST API allows to obtain basic information about the document and it's properties.

It returns [InfoResult]({{< ref "comparison/developer-guide/data-structures/inforesult.md" >}}) data structure, which contains the list of properties:

* Document file format
* File extension
* File size
* Pages count

## Resource

The following GroupDocs.Viewer Cloud REST API resource has been used to get [document information](https://apireference.groupdocs.cloud/comparison/#/Info/GetDocumentInfo).

## cURL example

{{< tabs "example1">}} {{< tab "Request" >}}
```bash
* First get JSON Web Token
* Please get your Client Id and Client Secret from <https://dashboard.groupdocs.cloud/applications>. Kindly place Client Id in "client_id" and Client Secret in "client_secret" argument.
curl -v "https://api.groupdocs.cloud/connect/token" \
-X POST \
-d "grant_type=client_credentials&client_id=xxxx&client_secret=xxxx" \
-H "Content-Type: application/x-www-form-urlencoded" \
-H "Accept: application/json"

* cURL example to get document information
curl -v "https://api.groupdocs.cloud/v2.0/comparison/info" \
-X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-H "Authorization: Bearer <jwt token>"
-d "{
         'FilePath': 'source_files/word/source.docx'
    }"
```
{{< /tab >}} {{< tab "Response" >}}

```json
{
  "format": "Microsoft Word Document",
  "extension": ".docx",
  "size": 23059,
  "pageCount": 1
}
```
{{< /tab >}} {{< /tabs >}}

## SDK example

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-comparison-cloud).



{{< tabs "example2">}} {{< tab "C#" >}}

```csharp

// For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-dotnet-samples
string MyClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
string MyClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

var configuration = new Configuration(MyClientId, MyClientSecret);

var apiInstance = new InfoApi(configuration);
var fileInfo = new FileInfo
{
    FilePath = "source_files/word/source.docx"
};
var request = new GetDocumentInfoRequest(fileInfo);

var response = apiInstance.GetDocumentInfo(request);

```

{{< /tab >}} {{< tab "Java" >}}

```Java

// For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-java-samples
String MyClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
String MyClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

Configuration configuration = new Configuration(MyClientId, MyClientSecret);

InfoApi apiInstance = new InfoApi(configuration);
FileInfo fileInfo = new FileInfo();
fileInfo.setFilePath("source_files/word/source.docx");
GetDocumentInfoRequest request = new GetDocumentInfoRequest(fileInfo);
InfoResult response = apiInstance.getDocumentInfo(request);

```

{{< /tab >}} {{< tab "PHP" >}}

```php

// For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-php-samples
use GroupDocs\Comparison\Model;
use GroupDocs\Comparison\Model\Requests;

$ClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
$ClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

$configuration = new GroupDocs\Comparison\Configuration();
$configuration->setAppSid($ClientId);
$configuration->setAppKey($ClientSecret);

$apiInstance# new GroupDocs\Comparison\InfoApi($configuration);

$fileInfo = new Model\FileInfo();
$fileInfo->setFilePath("source_files/word/source.docx");

$request = new Requests\GetDocumentInfoRequest($fileInfo);
$response = $apiInstance->getDocumentInfo($request);

```

{{< /tab >}} {{< tab "Node.js" >}}

```javascript

// For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-node-samples
global.comparison_cloud = require("groupdocs-comparison-cloud");

global.clientId = "XXXX-XXXX-XXXX-XXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
global.clientSecret = "XXXXXXXXXXXXXXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

global.infoApi = comparison_cloud.InfoApi.fromKeys(clientId, clientSecret);

try {
 let fileInfo = new comparison_cloud.FileInfo();
 fileInfo.filePath = "source_files/word/source.docx";

 let request = new comparison_cloud.GetDocumentInfoRequest(fileInfo);  

 let response = await infoApi.getDocumentInfo(request);
 console.log("GetDocumentInformation completed: " + response.pageCount);   
} catch (error) {
 console.log(error.message);   
}

```

{{< /tab >}} {{< tab "Python" >}}

```python

# For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-python-samples
import groupdocs_comparison_cloud

client_id = "XXXX-XXXX-XXXX-XXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
client_secret = "XXXXXXXXXXXXXXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

infoApi = groupdocs_comparison_cloud.InfoApi.from_keys(client_id, client_secret)

file_info = groupdocs_comparison_cloud.FileInfo()
file_info.file_path = "source_files/word/source.docx"
request = groupdocs_comparison_cloud.GetDocumentInfoRequest(file_info)
result = infoApi.get_document_info(request)

```

{{< /tab >}} {{< tab "Ruby" >}}

```ruby

# For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-ruby-samples
require 'groupdocs_comparison_cloud'

$client_id = "XXXX-XXXX-XXXX-XXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
$client_secret = "XXXXXXXXXXXXXXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

infoApi = GroupDocsComparisonCloud::InfoApi.from_keys($client_id, $client_secret)

file_info = GroupDocsComparisonCloud::FileInfo.new
file_info.file_path = "source_files/word/source.docx"
request = GroupDocsComparisonCloud::GetDocumentInfoRequest.new(file_info)
response = infoApi.get_document_info(request)

```

{{< /tab >}} {{< /tabs >}}
