---
id: "compare-multiple-documents-with-specific-compare-settings"
url: "comparison/compare-multiple-documents-with-specific-compare-settings"
title: "Compare multiple documents with specific compare settings"
productName: "GroupDocs.Comparison Cloud"
weight: 10
description: ""
keywords: ""
toc: True
---



GroupDocs.Comparison Cloud allows to compare more that 2 documents and specify some specific comparison options like styling for detected changes, comparison details level etc.

The following code sample shows how to compare multiple documents with specific options.

## API usage

There are steps that usage of GroupDocs.Comparison Cloud consists of:

1. Upload input documents into cloud storage
1. Compare documents or get document info
1. Download comparison result document from storage

Steps 1 and 3 are storage operations, please refer to this [File API documentation]({{< ref "comparison/developer-guide/working-with-file-api.md" >}}) for usage details.

[Swagger UI](https://apireference.groupdocs.cloud/comparison/) lets you call this REST API directly from the browser.

## cURL example

{{< tabs "example1">}} {{< tab "Linux/MacOS/Bash" >}}

```bash
# Retrieve JSON Web Token
curl -v "https://api.groupdocs.cloud/connect/token" \
  -X POST \
  -d "grant_type=client_credentials&client_id=$CLIENT_ID&client_secret=$CLIENT_SECRET" \
  -H "Content-Type: application/x-www-form-urlencoded" \
  -H "Accept: application/json"

# Get document comparison information
curl -v "https://api.groupdocs.cloud/v2.0/comparison/comparisons" \
  -X POST \
  -H "Content-Type: application/json" \
  -H "Accept: application/json" \
  -H "Authorization: Bearer $JWT_TOKEN" \
  -d '{
    "SourceFile": {
      "FilePath": "source_files/word/source.docx"
    },
    "TargetFiles": [
      {
        "FilePath": "target_files/word/target.docx"
      },
      {
        "FilePath": "target_files/word/target_1.docx"
      },
      {
        "FilePath": "target_files/word/target_2.docx"
      }
    ],
    "OutputPath": "output/result.docx",
    "Settings": {
      "InsertedItemsStyle": {
        "FontColor": "16711680"
      }
    }
  }'
```

{{< /tab >}}

{{< tab "Windows PowerShell" >}}

```powershell
# Retrieve JSON Web Token
curl.exe -v "https://api.groupdocs.cloud/connect/token" `
  -X POST `
  -d "grant_type=client_credentials&client_id=$env:CLIENT_ID&client_secret=$env:CLIENT_SECRET" `
  -H "Content-Type: application/x-www-form-urlencoded" `
  -H "Accept: application/json"

# Get document comparison information
curl.exe -v "https://api.groupdocs.cloud/v2.0/comparison/comparisons" `
  -X POST `
  -H "Content-Type: application/json" `
  -H "Accept: application/json" `
  -H "Authorization: Bearer $env:JWT_TOKEN" `
  -d "{
    'SourceFile': {
      'FilePath': 'source_files\\word\\source.docx'
    },
    'TargetFiles': [
      {
        'FilePath': 'target_files\\word\\target.docx'
      },
      {
        'FilePath': 'target_files\\word\\target_1.docx'
      },
      {
        'FilePath': 'target_files\\word\\target_2.docx'
      }
    ],
    'OutputPath': 'output/result.docx',
    'Settings': {
      'InsertedItemsStyle': {
        'FontColor': '16711680'
      }
    }
  }"
```

{{< /tab >}}

{{< tab "Windows CMD" >}}

```cmd
rem Retrieve JSON Web Token
curl -v "https://api.groupdocs.cloud/connect/token" ^
  -X POST ^
  -d "grant_type=client_credentials&client_id=%CLIENT_ID%&client_secret=%CLIENT_SECRET%" ^
  -H "Content-Type: application/x-www-form-urlencoded" ^
  -H "Accept: application/json"

rem Get document comparison information
curl -v "https://api.groupdocs.cloud/v2.0/comparison/comparisons" ^
  -X POST ^
  -H "Content-Type: application/json" ^
  -H "Accept: application/json" ^
  -H "Authorization: Bearer %JWT_TOKEN%" ^
  -d "{\"SourceFile\":{\"FilePath\":\"source_files/word/source.docx\"},\"TargetFiles\":[{\"FilePath\":\"target_files/word/target.docx\"},{\"FilePath\":\"target_files/word/target_1.docx\"},{\"FilePath\":\"target_files/word/target_2.docx\"}],\"OutputPath\":\"output/result.docx\",\"Settings\":{\"InsertedItemsStyle\":{\"FontColor\":\"16711680\"}}}"
```

{{< /tab >}} {{< tab "Response" >}}

```json

{
  "href": "https://api.groupdocs.cloud/v2.0/comparison/storage/file/output/result.docx",
  "rel": "output/result.docx",
  "type": "file",
  "title": "result.docx"
}
```
{{< /tab >}} {{< /tabs >}}

## SDK example

Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/groupdocs-comparison-cloud) for a complete list of GroupDocs.Comparison Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs]({{< ref "comparison/getting-started/available-sdks.md" >}}) article to learn how to add an SDK to your project.



{{< tabs "example2">}} {{< tab "C#" >}}

```csharp

// For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-dotnet-samples
string MyClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
string MyClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

var configuration = new Configuration(MyClientId, MyClientSecret);

var apiInstance = new CompareApi(configuration);
var options = new ComparisonOptions
{
    SourceFile = new FileInfo
    {
        FilePath = "source_files/word/source.docx"
    },
    TargetFiles = new List<FileInfo> {
        new FileInfo {
            FilePath = "target_files/word/target.docx"
        },
        new FileInfo {
            FilePath = "target_files/word/target_1.docx"
        },
        new FileInfo {
            FilePath = "target_files/word/target_2.docx"
        }
    },
    Settings = new Settings {
        InsertedItemsStyle = new ItemsStyle
        {
            FontColor = "16711680"
        }
    },
    OutputPath = "output/result.docx"
};
var request = new ComparisonsRequest(options);
var response = apiInstance.Comparisons(request);

```

{{< /tab >}} {{< tab "Java" >}}

```Java

// For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-java-samples
String MyClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
String MyClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

Configuration configuration = new Configuration(MyClientId, MyClientSecret);

CompareApi apiInstance = new CompareApi(configuration);
FileInfo sourceFileInfo = new FileInfo();
sourceFileInfo.setFilePath("source_files/word/source.docx");
FileInfo targetFileInfo1 = new FileInfo();
targetFileInfo1.setFilePath("target_files/word/target.docx");
FileInfo targetFileInfo2 = new FileInfo();
targetFileInfo2.setFilePath("target_files/word/target_1.docx");
FileInfo targetFileInfo3 = new FileInfo();
targetFileInfo3.setFilePath("target_files/word/target_2.docx");

ItemsStyle insertedItemsStyle = new ItemsStyle();
insertedItemsStyle.setFontColor("16711680");
Settings settings = new Settings();
settings.setInsertedItemsStyle(insertedItemsStyle);

ComparisonOptions options = new ComparisonOptions();
options.setSourceFile(sourceFileInfo);
options.addTargetFilesItem(targetFileInfo1);
options.addTargetFilesItem(targetFileInfo2);
options.addTargetFilesItem(targetFileInfo3);
options.setSettings(settings);
options.setOutputPath("output/result.docx");

ComparisonsRequest request = new ComparisonsRequest(options);
Link response = apiInstance.comparisons(request);

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

$apiInstance = new GroupDocs\Comparison\CompareApi($configuration);

$sourceFile = new Model\FileInfo();
$sourceFile->setFilePath("source_files/word/source.docx");
$targetFile = new Model\FileInfo();
$targetFile->setFilePath("target_files/word/target.docx");
$targetFile1 = new Model\FileInfo();
$targetFile1->setFilePath("target_files/word/target_1.docx");
$targetFile2 = new Model\FileInfo();
$targetFile2->setFilePath("target_files/word/target_2.docx");
$options = new Model\ComparisonOptions();
$options->setSourceFile($sourceFile);
$options->setTargetFiles([$targetFile, $targetFile1, $targetFile2]);
$options->setOutputPath("output/result.docx");
$insertedItemsStyle = new Model\ItemsStyle();
$insertedItemsStyle->setFontColor("16711680");
$settings = new Model\Settings();
$settings->setInsertedItemsStyle($insertedItemsStyle);
$options->setSettings($settings);
$request = new Requests\ComparisonsRequest($options);
$response = $apiInstance->comparisons($request);

```

{{< /tab >}} {{< tab "Node.js" >}}

```javascript

// For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-node-samples
global.comparison_cloud = require("groupdocs-comparison-cloud");

global.clientId = "XXXX-XXXX-XXXX-XXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
global.clientSecret = "XXXXXXXXXXXXXXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

global.compareApi# comparison_cloud.CompareApi.fromKeys(clientId, clientSecret);

try {
 let source = new comparison_cloud.FileInfo();
 source.filePath = "source_files/word/source_protected.docx";
 source.password = "1231";
 let target = new comparison_cloud.FileInfo();
 target.filePath = "target_files/word/target_protected.docx";
 target.password = "5784";
 let target1 = new comparison_cloud.FileInfo();
 target1.filePath = "target_files/word/target_1_protected.docx";
 target1.password = "5784";
 let target2 = new comparison_cloud.FileInfo();
 target2.filePath = "target_files/word/target_2_protected.docx";
 target2.password = "5784";
 let options = new comparison_cloud.ComparisonOptions();
 options.sourceFile = source;
 options.targetFiles = [target, target1, target2];
 options.outputPath = "output/result.docx";

 let request = new comparison_cloud.ComparisonsRequest(options);  

 let response = await compareApi.comparisons(request);
 console.log("Output file link: " + response.href);
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

api_instance = groupdocs_comparison_cloud.CompareApi.from_keys(client_id, client_secret)

source = groupdocs_comparison_cloud.FileInfo()
source.file_path = "source_files/word/source.docx"
target = groupdocs_comparison_cloud.FileInfo()
target.file_path = "target_files/word/target.docx"
target1 = groupdocs_comparison_cloud.FileInfo()
target1.file_path = "target_files/word/target_1.docx"
target2 = groupdocs_comparison_cloud.FileInfo()
target2.file_path = "target_files/word/target_2.docx"
options = groupdocs_comparison_cloud.ComparisonOptions()
options.source_file = source
options.target_files = [target, target1, target2]
options.output_path = "output/result.docx"
settings = groupdocs_comparison_cloud.Settings()
settings.inserted_items_style = groupdocs_comparison_cloud.ItemsStyle()
settings.inserted_items_style.font_color = "16711680"
options.settings = settings

request = groupdocs_comparison_cloud.ComparisonsRequest(options)
response = api_instance.comparisons(request)

```

{{< /tab >}} {{< tab "Ruby" >}}

```ruby

# For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-ruby-samples
require 'groupdocs_comparison_cloud'

$client_id = "XXXX-XXXX-XXXX-XXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
$client_secret = "XXXXXXXXXXXXXXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

apiInstance = GroupDocsComparisonCloud::CompareApi.from_config($config)

source = GroupDocsComparisonCloud::FileInfo.new
source.file_path = "source_files/word/source.docx"
target = GroupDocsComparisonCloud::FileInfo.new
target.file_path = "target_files/word/target.docx"
target1 = GroupDocsComparisonCloud::FileInfo.new
target1.file_path = "target_files/word/target_1.docx"
target2 = GroupDocsComparisonCloud::FileInfo.new
target2.file_path = "target_files/word/target_2.docx"
options = GroupDocsComparisonCloud::ComparisonOptions.new
options.source_file = source
options.target_files = [target, target1, target2]
options.output_path = "output/result.docx"
settings = GroupDocsComparisonCloud::Settings.new
settings.inserted_items_style = GroupDocsComparisonCloud::ItemsStyle.new
settings.inserted_items_style.font_color = "16711680"
options.settings = settings

request = GroupDocsComparisonCloud::ComparisonsRequest.new(options)
response = apiInstance.comparisons(request)

```
{{< /tab >}} {{< tab "Apex" >}}

```javascript
// Create configuration and API instances
Configuration config = new Configuration('YOUR_API_KEY', 'YOUR_API_SECRET'); // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
FileApi fileApi = new FileApi(config);
CompareApi compareApi = new CompareApi(config);

// Upload source file to cloud storage
List<ContentVersion> sourceVersions = [SELECT Id, Title, VersionData FROM ContentVersion WHERE Title = 'source.docx' LIMIT 1];
if (sourceVersions.size() > 0) {
    fileApi.uploadFile(new UploadFileRequest('source_files/word/source.docx', sourceVersions[0].VersionData, null));
}

// Upload target files to cloud storage
List<ContentVersion> targetVersions = [SELECT Id, Title, VersionData FROM ContentVersion WHERE Title IN ('target.docx', 'target_1.docx', 'target_2.docx')];
for (ContentVersion targetVersion : targetVersions) {
    String filePath = 'target_files/word/' + targetVersion.Title;
    fileApi.uploadFile(new UploadFileRequest(filePath, targetVersion.VersionData, null));
}

// Set up comparison options
ComparisonOptions options = new ComparisonOptions();
options.SourceFile = new FileInfo();
options.SourceFile.FilePath = 'source_files/word/source.docx';

options.TargetFiles = new List<FileInfo>();

FileInfo targetFile1 = new FileInfo();
targetFile1.FilePath = 'target_files/word/target.docx';
options.TargetFiles.add(targetFile1);

FileInfo targetFile2 = new FileInfo();
targetFile2.FilePath = 'target_files/word/target_1.docx';
options.TargetFiles.add(targetFile2);

FileInfo targetFile3 = new FileInfo();
targetFile3.FilePath = 'target_files/word/target_2.docx';
options.TargetFiles.add(targetFile3);

options.Settings = new Settings();
options.Settings.InsertedItemsStyle = new ItemsStyle();
options.Settings.InsertedItemsStyle.FontColor = '16711680'; // Red

options.OutputPath = 'output/result.docx';

// Execute comparison
ComparisonsRequest request = new ComparisonsRequest(options);
Link response = compareApi.comparisons(request);

// Debug the result
System.debug('Comparison complete. Output file link: ' + response.href);

```
{{< /tab >}} {{< /tabs >}}
