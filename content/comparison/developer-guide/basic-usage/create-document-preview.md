---
id: "create-document-preview"
url: "comparison/create-document-preview"
title: "Create Document Preview"
productName: "GroupDocs.Comparison Cloud"
description: ""
keywords: ""
toc: True
---


GroupDocs.Comparison Cloud allows to create document preview images, one per page. Image size and format can be set as options.

## API Usage ##

There are steps that usage of GroupDocs.Comparison Cloud consists of:

1. Upload input document into cloud storage
1. Create preview images
1. Download images

For storage operations, like uploading or downloading documents, please refer to the corresponding articles of this manual.

[Swagger UI](https://apireference.groupdocs.cloud/comparison/) lets you call this REST API directly from the browser.

## cURL REST Example ##

{{< tabs "example1">}} {{< tab "Request" >}}

```javascript

// First get JSON Web Token
// Please get your Client Id and Client Secret from https://dashboard.groupdocs.cloud/applications. Kindly place Client Id in "client_id" and Client Secret in "client_secret" argument.
curl -v "https://api.groupdocs.cloud/connect/token" \
-X POST \
-d "grant_type#client_credentials&client_id#xxxx&client_secret#xxxx" \
-H "Content-Type: application/x-www-form-urlencoded" \
-H "Accept: application/json"

// cURL example to get document information
curl -v "https://api.groupdocs.cloud/v2.0/comparison/preview" \
-X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-H "Authorization: Bearer <jwt token>"
-d "{
  'FileInfo': {
    'FilePath': 'sample2.pdf'
  },
  'Format': 'jpeg'
}"

```

{{< /tab >}} {{< tab "Response" >}}

```javascript
[
  {
    "href": "http://api.groupdocs.cloud/v2.0/comparison/storage/file/Output/sample2_1.jpeg",
    "rel": "Output/sample2_1.jpeg",
    "type": "file",
    "title": "sample2_1.jpeg"
  },
  {
    "href": "http://api.groupdocs.cloud/v2.0/comparison/storage/file/Output/sample2_2.jpeg",
    "rel": "Output/sample2_2.jpeg",
    "type": "file",
    "title": "sample2_2.jpeg"
  }
]
```

{{< /tab >}} {{< /tabs >}}

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](comparison/available-sdks).

### SDK Examples ###

{{< tabs "example2">}} {{< tab "C#" >}}

```csharp

// For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-dotnet-samples
string MyClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
string MyClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

var configuration = new Configuration(MyClientId, MyClientSecret);
var apiInstance = new PreviewApi(configuration);

try
{
    var options = new PreviewOptions
    {
        FileInfo = new FileInfo {FilePath = "source_files/word/source.docx"},
        Format = PreviewOptions.FormatEnum.Png,
        OutputFolder = "output"
    };

    var request = new PreviewRequest(options);

    var response = apiInstance.Preview(request);
    Console.WriteLine("Output pages num: " + response.Count);
}
catch (Exception e)
{
    Console.WriteLine("Exception while calling api: " + e.Message);
}

```

{{< /tab >}} {{< tab "Java" >}}

```java

// For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-java-samples
String MyClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
String MyClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

Configuration configuration = new Configuration(MyClientId, MyClientSecret);
PreviewApi apiInstance = new PreviewApi(configuration);
try {
  FileInfo fileInfo = new FileInfo();
  fileInfo.setFilePath("source_files/word/source.docx");

  PreviewOptions options = new PreviewOptions();
  options.setFileInfo(fileInfo);
  options.setFormat(FormatEnum.JPEG);
  options.setOutputFolder("output");

  PreviewRequest request = new PreviewRequest(options);

  List<Link> response = apiInstance.preview(request);

  System.out.println("Output pages count: " + response.size());
} catch (ApiException e) {
  System.err.println("Exception while calling PreviewApi:");
  e.printStackTrace();
}

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

$apiInstance = new GroupDocs\Comparison\PreviewApi($configuration);

$fileInfo = new Model\FileInfo();
$fileInfo->setFilePath("source_files/word/source.docx");
$options = new Model\PreviewOptions();
$options->setFileInfo($fileInfo);
$options->setFormat(Model\PreviewOptions::FORMAT_PNG);		
$options->setOutputFolder("output");

$request = new Requests\PreviewRequest($options);
$response = $apiInstance->preview($request);

echo "Output file count: ", count($response);
echo "\n";                            

```

{{< /tab >}} {{< tab "Node.js" >}}

```javascript

// For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-node-samples
global.comparison_cloud = require("groupdocs-comparison-cloud");

global.clientId = "XXXX-XXXX-XXXX-XXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
global.clientSecret = "XXXXXXXXXXXXXXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

global.previewApi = comparison_cloud.PreviewApi.fromKeys(clientId, clientSecret);

let source = new comparison_cloud.FileInfo();
source.filePath = "source_files/word/source.docx";
let options = new comparison_cloud.PreviewOptions();
options.fileInfo = source;
options.format = "png";
options.outputFolder = "output";

let request = new comparison_cloud.PreviewRequest(options);		

let response = await previewApi.preview(request);
console.log("Output file count: " + response.length);

```

{{< /tab >}} {{< tab "Python" >}}

```python

# For complete examples and data files, please go to https://github.com/groupdocs-comparison_cloud-cloud/groupdocs-comparison_cloud-cloud-python-samples
from groupdocs_comparison_cloud import *
import groupdocs_comparison_cloud

client_id = "XXXX-XXXX-XXXX-XXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
client_secret = "XXXXXXXXXXXXXXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

api_instance = groupdocs_comparison_cloud.PreviewApi.from_keys(client_id, client_secret)

source = groupdocs_comparison_cloud.FileInfo()
source.file_path = "source_files/word/source.docx"
options = groupdocs_comparison_cloud.PreviewOptions()
options.file_info = source
options.format = "jpg" 
options.output_folder = "output"

request = groupdocs_comparison_cloud.PreviewRequest(options)
response = api_instance.preview(request)
print("Output file count: " + str(len(response)))

```

{{< /tab >}} {{< tab "Ruby" >}}

```ruby

# For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-ruby-samples
require 'groupdocs_comparison_cloud'

$client_id = "XXXX-XXXX-XXXX-XXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
$client_secret = "XXXXXXXXXXXXXXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

apiInstance = GroupDocsComparisonCloud::PreviewApi.from_keys($client_id, $client_secret)

source = GroupDocsComparisonCloud::FileInfo.new
source.file_path = "source_files/word/source.docx"
options = GroupDocsComparisonCloud::PreviewOptions.new
options.file_info = source
options.format = "png"
options.output_folder = "output"

request = GroupDocsComparisonCloud::PreviewRequest.new(options)    
response = apiInstance.preview(request)

puts("Output file count: " + response.length.to_s)

```

{{< /tab >}} {{< tab "Apex" >}}

```javascript
// Create configuration and API instances
Configuration config = new Configuration('YOUR_API_KEY', 'YOUR_API_SECRET'); // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
FileApi fileApi = new FileApi(config);
PreviewApi previewApi = new PreviewApi(config);

// Upload source Word file to cloud storage
List<ContentVersion> sourceVersions = [SELECT Id, Title, VersionData FROM ContentVersion WHERE Title = 'source.docx' LIMIT 1];
if (sourceVersions.size() > 0) {
    fileApi.uploadFile(new UploadFileRequest('source_files/word/source.docx', sourceVersions[0].VersionData, null));
}

// Set up comparison options
ComparisonOptions options = new PreviewOptions();
options.FileInfo = new FileInfo();
options.FileInfo.FilePath = 'source_files/word/source.docx';
options.Format = 'JPEG';

// Execute preview
PreviewRequest request = new PreviewRequest(options);
List<Link> response = previewApi.preview(request);

// Debug the result
System.debug('The num of pages: ' + response.size());

```

{{< /tab >}} {{< /tabs >}}
