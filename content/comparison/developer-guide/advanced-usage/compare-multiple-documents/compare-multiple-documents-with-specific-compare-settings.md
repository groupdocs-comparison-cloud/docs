---
id: "compare-multiple-documents-with-specific-compare-settings"
url: "comparison/compare-multiple-documents-with-specific-compare-settings"
title: "Compare multiple documents with specific compare settings"
productName: "GroupDocs.Comparison Cloud"
weight: 10
description: ""
keywords: ""
---

# Introduction #

GroupDocs.Comparison Cloud allows to compare more that 2 documents and specify some specific comparison options like styling for detected changes, comparison details level etc.

The following code sample shows how to compare multiple documents with specific options.

## API Usage ##

There are steps that usage of GroupDocs.Comparison Cloud consists of:

1. Upload input documents into cloud storage
1. Compare documents or get document info
1. Download comparison result document from storage

Steps 1 and 3 are storage operations, please refer to this [File API documentation]({{< ref "comparison/developer-guide/working-with-file-api.md" >}}) for usage details.

[Swagger UI](https://apireference.groupdocs.cloud/comparison/) lets you call this REST API directly from the browser.

## cURL REST Example ##

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}} {{< tab tabNum="1" >}}

```html

* First get JSON Web Token
* Please get your Client Id and Client Secret from https://dashboard.groupdocs.cloud/applications. Kindly place Client Id in "client_id" and Client Secret in "client_secret" argument.
curl -v "https://api.groupdocs.cloud/connect/token" \
-X POST \
-d "grant_type#client_credentials&client_id#xxxx&client_secret#xxxx" \
-H "Content-Type: application/x-www-form-urlencoded" \
-H "Accept: application/json"

* cURL example to get document information
curl -v "https://api.groupdocs.cloud/v2.0/comparison/comparisons" \
-X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-H "Authorization: Bearer <jwt token>"
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

{{< /tab >}} {{< tab tabNum="2" >}}

```html

{
  "href": "https://api.groupdocs.cloud/v2.0/comparison/storage/file/output/result.docx",
  "rel": "output/result.docx",
  "type": "file",
  "title": "result.docx"
}

{{< /tab >}} {{< /tabs >}}

## SDKs ##

Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/groupdocs-comparison-cloud) for a complete list of GroupDocs.Comparison Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs]({{< ref "comparison/getting-started/available-sdks.md" >}}) article to learn how to add an SDK to your project.

### SDK Examples ###

{{< tabs tabTotal="6" tabID="10" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Node.js" tabName5="Python" tabName6="Ruby" >}} {{< tab tabNum="1" >}}

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

{{< /tab >}} {{< tab tabNum="2" >}}

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

{{< /tab >}} {{< tab tabNum="3" >}}

```php

// For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-php-samples
use GroupDocs\Comparison\Model;
use GroupDocs\Comparison\Model\Requests;

$ClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
$ClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

$configuration = new GroupDocs\Comparison\Configuration();
$configuration->setAppSid($ClientId);
$configuration->setAppKey($ClientSecret);

$apiInstance# new GroupDocs\Comparison\CompareApi($configuration);

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

{{< /tab >}} {{< tab tabNum="4" >}}

```javascript

// For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-node-samples
global.comparison_cloud = require("groupdocs-comparison-cloud");

global.clientId = "XXXX-XXXX-XXXX-XXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
global.clientSecret = "XXXXXXXXXXXXXXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

global.compareApi# comparison_cloud.CompareApi.fromKeys(clientId, clientSecret);

let source = new comparison_cloud.FileInfo();
source.filePath = "source_files/word/source.docx";
let target = new comparison_cloud.FileInfo();
target.filePath = "target_files/word/target.docx";
let target1 = new comparison_cloud.FileInfo();
target1.filePath = "target_files/word/target_1.docx";
let target2 = new comparison_cloud.FileInfo();
target2.filePath = "target_files/word/target_2.docx";
let settings = new comparison_cloud.Settings();
settings.insertedItemsStyle = new comparison_cloud.ItemsStyle();
settings.insertedItemsStyle.fontColor = "16711680";
let options = new comparison_cloud.ComparisonOptions();
options.sourceFile = source;
options.targetFiles = [target, target1, target2];
options.outputPath = "output/result.docx";
options.settings = settings;

let request = new comparison_cloud.ComparisonsRequest(options);
let response = await compareApi.comparisons(request);

```

{{< /tab >}} {{< tab tabNum="5" >}}

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

{{< /tab >}} {{< tab tabNum="6" >}}

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

{{< /tab >}} {{< /tabs >}}
