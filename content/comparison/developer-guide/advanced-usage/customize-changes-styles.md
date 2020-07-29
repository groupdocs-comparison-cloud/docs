---
id: "customize-changes-styles"
url: "comparison/customize-changes-styles"
title: "Customize changes styles"
productName: "GroupDocs.Comparison Cloud"
weight: 10
description: ""
keywords: ""
---

 






# Introduction #

GroupDocs.Comparison Cloud provides compare options set with some default values that provides both - appropriate comparison speed and quality.

Example below demonstrates how to change different changes types styling.

## API Usage ##

There are steps that usage of GroupDocs.Comparison Cloud consists of:

1. Upload input documents into cloud storage
1. Compare documents or get document info
1. Download comparison result document from storage

Steps 1 and 3 are storage operations, please refer to this [File API documentation]({{< ref "comparison/developer-guide/working-with-file-api.md" >}}) for usage details.

[Swagger UI](https://apireference.groupdocs.cloud/comparison/) lets you call this REST API directly from the browser. 

## cURL REST Example ##


 Request
```html 

* First get JSON Web Token
* Please get your App Key and App SID from https://dashboard.groupdocs.cloud/#/apps. Kindly place App Key in "client_secret" and App SID in "client_id" argument.
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
    }
  ],
  'OutputPath': 'output/result.docx',
  'Settings': {
    'InsertedItemsStyle': {
      'HighlightColor': '14297642',
      'FontColor': '5102122',
      'Underline': true
    },
    'DeletedItemsStyle': {
      'FontColor': '14166746',
      'Bold': true
    },
    'ChangedItemsStyle': {
      'FontColor': '14320170',
      'Italic': true
    }
  }
}"

 ```


 Response
```html 

{
  "href": "https://api.groupdocs.cloud/v2.0/comparison/storage/file/output/result.docx",
  "rel": "output/result.docx",
  "type": "file",
  "title": "result.docx"
}

 ```




## SDKs ##

Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/groupdocs-comparison-cloud) for a complete list of GroupDocs.Comparison Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs]({{< ref "comparison/getting-started/available-sdks.md" >}}) article to learn how to add an SDK to your project.

### SDK Examples ###


 C#
```csharp 

* For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-dotnet-samples
string MyAppKey # ""; * Get AppKey and AppSID from https://dashboard.groupdocs.cloud
string MyAppSid # ""; * Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
var configuration # new Configuration(MyAppSid, MyAppKey);
  
var apiInstance # new CompareApi(configuration);
 
var options # new ComparisonOptions
{
    SourceFile # new FileInfo
    {
        FilePath # "source_files/word/source.docx"
    },
    TargetFiles # new List<FileInfo> {
        new FileInfo {
            FilePath # "target_files/word/target.docx"
        }
    },
    Settings # new Settings { 
        InsertedItemsStyle # new ItemsStyle
        {
            HighlightColor # "14297642", * Red
            FontColor # "5102122", * Green
            Underline # true,
        },
        DeletedItemsStyle # new ItemsStyle
        {
            FontColor # "14166746",
            Bold # true,
        },
        ChangedItemsStyle # new ItemsStyle
        {
            FontColor # "14320170",
            Italic # true,
        },
    },
    OutputPath # "output/result.docx"
};
 
var request # new ComparisonsRequest(options);
var response # apiInstance.Comparisons(request);

 ```


 Java
```java 

* For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-java-samples
String MyAppKey # ""; * Get AppKey and AppSID from https://dashboard.groupdocs.cloud
String MyAppSid # ""; * Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
Configuration configuration # new Configuration(MyAppSid, MyAppKey);
  
CompareApi apiInstance # new CompareApi(configuration); 
 
FileInfo sourceFileInfo # new FileInfo();
sourceFileInfo.setFilePath("source_files/word/source.docx");
FileInfo targetFileInfo # new FileInfo();
targetFileInfo.setFilePath("target_files/word/target.docx");
 
ItemsStyle insertedItemsStyle # new ItemsStyle();
insertedItemsStyle.setFontColor("5102122");
insertedItemsStyle.setHighlightColor("14297642");
insertedItemsStyle.setUnderline(true);
 
ItemsStyle deletedItemsStyle # new ItemsStyle();
deletedItemsStyle.setFontColor("14166746");
deletedItemsStyle.setBold(true);
 
ItemsStyle changedItemsStyle # new ItemsStyle();
changedItemsStyle.setFontColor("14320170");
changedItemsStyle.setItalic(true);
 
Settings settings # new Settings();
settings.setInsertedItemsStyle(insertedItemsStyle);
settings.setDeletedItemsStyle(deletedItemsStyle);
settings.setChangedItemsStyle(changedItemsStyle);
 
ComparisonOptions options # new ComparisonOptions();
options.setSourceFile(sourceFileInfo);
options.addTargetFilesItem(targetFileInfo);
options.setSettings(settings);
options.setOutputPath("output/result.docx");
 
ComparisonsRequest request # new ComparisonsRequest(options);
Link response # apiInstance.comparisons(request);

 ```


 PHP
```php 

* For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-php-samples
use GroupDocs\Comparison\Model;
use GroupDocs\Comparison\Model\Requests;
 
$AppSid # ""; * Get AppKey and AppSID from https://dashboard.groupdocs.cloud
$AppKey # ""; * Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
$configuration # new GroupDocs\Comparison\Configuration();
$configuration->setAppSid($AppSid);
$configuration->setAppKey($AppKey);
 
$apiInstance# new GroupDocs\Comparison\CompareApi($configuration);
 
$sourceFile # new Model\FileInfo();
$sourceFile->setFilePath("source_files/word/source.docx");
$targetFile # new Model\FileInfo();
$targetFile->setFilePath("target_files/word/target.docx");      
$options # new Model\ComparisonOptions();
$options->setSourceFile($sourceFile);
$options->setTargetFiles([$targetFile]);
$options->setOutputPath("output/result.docx");
 
$insertedItemsStyle # new Model\ItemsStyle();
$insertedItemsStyle->setHighlightColor("14297642");
$insertedItemsStyle->setFontColor("16711680");
$insertedItemsStyle->setUnderline(true);
 
$deletedItemsStyle # new Model\ItemsStyle();
$deletedItemsStyle->setFontColor("14166746");
$deletedItemsStyle->setBold(true);
 
$changedItemsStyle # new Model\ItemsStyle();
$changedItemsStyle->setFontColor("14320170");
$changedItemsStyle->setItalic(true);
 
$settings # new Model\Settings();
$settings->setInsertedItemsStyle($insertedItemsStyle);
$settings->setDeletedItemsStyle($deletedItemsStyle);
$settings->setChangedItemsStyle($changedItemsStyle);
$options->setSettings($settings);
 
$request # new Requests\ComparisonsRequest($options);
$response # $apiInstance->comparisons($request);

 ```


 Node
```html 

* For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-node-samples
global.comparison_cloud # require("groupdocs-comparison-cloud");
 
global.appSid # "XXXX-XXXX-XXXX-XXXX"; * Get AppKey and AppSID from https://dashboard.groupdocs.cloud
global.appKey # "XXXXXXXXXXXXXXXX"; * Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
global.compareApi # comparison_cloud.CompareApi.fromKeys(appSid, appKey);
 
let source # new comparison_cloud.FileInfo();
source.filePath # "source_files/word/source.docx";
let target # new comparison_cloud.FileInfo();
target.filePath # "target_files/word/target.docx";
 
let settings # new comparison_cloud.Settings();
settings.insertedItemsStyle # new comparison_cloud.ItemsStyle();
settings.insertedItemsStyle.highlightColor # "14297642";
settings.insertedItemsStyle.fontColor # "16711680";
settings.insertedItemsStyle.underline # true;
settings.deletedItemsStyle # new comparison_cloud.ItemsStyle();     
settings.deletedItemsStyle.fontColor # "14166746";
settings.deletedItemsStyle.bold # true;
settings.changedItemsStyle # new comparison_cloud.ItemsStyle();     
settings.changedItemsStyle.fontColor # "14320170";
settings.changedItemsStyle.italic # true;
 
let options # new comparison_cloud.ComparisonOptions();
options.sourceFile # source;
options.targetFiles # [target];
options.outputPath # "output/result.docx";
options.settings # settings;
 
let request # new comparison_cloud.ComparisonsRequest(options);     
let response # await compareApi.comparisons(request);

 ```


 Python
```python 

# For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-python-samples
import groupdocs_comparison_cloud
 
app_sid # "XXXX-XXXX-XXXX-XXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
app_key # "XXXXXXXXXXXXXXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
api_instance # groupdocs_comparison_cloud.CompareApi.from_keys(app_sid, app_key)
 
source # groupdocs_comparison_cloud.FileInfo()
source.file_path # "source_files/word/source.docx"
target # groupdocs_comparison_cloud.FileInfo()
target.file_path # "target_files/word/target.docx"             
options # groupdocs_comparison_cloud.ComparisonOptions()
options.source_file # source
options.target_files # [target] 
options.output_path # "output/result.docx"
settings # groupdocs_comparison_cloud.Settings()
settings.inserted_items_style # groupdocs_comparison_cloud.ItemsStyle()
settings.inserted_items_style.highlight_color # "14297642"
settings.inserted_items_style.font_color # "16711680"
settings.inserted_items_style.underline # True
settings.deleted_items_style # groupdocs_comparison_cloud.ItemsStyle()        
settings.deleted_items_style.font_color # "14166746"
settings.deleted_items_style.bold # True
settings.changed_items_style # groupdocs_comparison_cloud.ItemsStyle()        
settings.changed_items_style.font_color # "14320170"
settings.changed_items_style.italic # True       
options.settings # settings
 
request # groupdocs_comparison_cloud.ComparisonsRequest(options)
response # api_instance.comparisons(request)

 ```


 Ruby
```ruby 

# For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-ruby-samples
require 'groupdocs_comparison_cloud'
 
$app_sid # "XXXX-XXXX-XXXX-XXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
$app_key # "XXXXXXXXXXXXXXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
api_instance # GroupDocsComparisonCloud::CompareApi.from_keys($app_sid, $app_key)
 
ssource # GroupDocsComparisonCloud::FileInfo.new
source.file_path # "source_files/word/source.docx"
target # GroupDocsComparisonCloud::FileInfo.new
target.file_path # "target_files/word/target.docx"             
options # GroupDocsComparisonCloud::ComparisonOptions.new
options.source_file # source
options.target_files # [target]
options.output_path # "output/result.docx"
settings # GroupDocsComparisonCloud::Settings.new
settings.inserted_items_style # GroupDocsComparisonCloud::ItemsStyle.new
settings.inserted_items_style.highlight_color # "14297642"
settings.inserted_items_style.font_color # "16711680"
settings.inserted_items_style.underline # true
settings.deleted_items_style # GroupDocsComparisonCloud::ItemsStyle.new       
settings.deleted_items_style.font_color # "14166746"
settings.deleted_items_style.bold # true
settings.changed_items_style # GroupDocsComparisonCloud::ItemsStyle.new       
settings.changed_items_style.font_color # "14320170"
settings.changed_items_style.italic # true       
options.settings # settings
 
request # GroupDocsComparisonCloud::ComparisonsRequest.new(options)    
response # apiInstance.comparisons(request)

 ```

