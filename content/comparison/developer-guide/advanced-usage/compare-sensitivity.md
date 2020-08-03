---
id: "compare-sensitivity"
url: "comparison/compare-sensitivity"
title: "Compare sensitivity"
productName: "GroupDocs.Comparison Cloud"
weight: 10
description: ""
keywords: ""
---

 






# Introduction #

GroupDocs.Comparison Cloud allows to adjust comparison sensitivity to achieve the necessary balance between file comparison speed and accuracy. Possible comparison sensitivity values range is from 0 to 100.

* Minimal value - the minimal value is 0. Setting sensitivity to a minimal value provides the fastest comparison speed, but it may produce worst comparison quality. If there is at least one common letter in two compared words then these words will not be treated as fully inserted and deleted
* Value by default  - the default value is 75. Comparison occurs when the percentage of deleted or inserted elements in relation to all elements does not exceed 75%.
* Maximum value - the maximum values is 100. Comparison occurs at any length of a common sub-sequence of two compared objects. This option provides the best quality, but slowest comparison speed.

For better understanding about how comparison algorithms work let's suppose we have two strings:

##1. It is our equity poetry
2. Jack is a glad calf##


We will highlight removed text parts with red and inserted parts with blue color. So, these strings have two common sub-sequences: "is" word and 4 space symbols. 

Common sub-sequence is - " is   " and its length is 6 symbols (there are 4 space symbols in it).
Length of inserted sub-sequence is 13 symbols - Jackagladcalf
Removed sub-sequence length is 17 symbols - Itourequitypoetry
Lets calculate percent of removed and inserted symbols: (17 + 13) / (17 + 13 + 6) * 100 # 83%

Case 1. If SensitivityOfComparison # 80% comparison of these two strings will produce the next result:
Jack is a glad calfIt is our equity poetry

Because calculated percent of removed and inserted symbols equals 83% and it is bigger than value of SensitivityOfComparison (equals 80%) then this common sub-sequence will be not taken into account.
The first string considered completely removed and the second string considered completely inserted. The same results will be produced for any calculated percent less than 83%.

Case 2. If SensitivityOfComparison # 85%, comparison of these two strings will produce the next result:
JackIt is aour gladequity calfpoetry

Common sub-sequence was found, because 85% > 83%. The same results will be produced for any calculated percent bigger than 83%.

The following code snippet demonstrates how compare files with specific sensitivity: 

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
    'SensitivityOfComparison': 100
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
        SensitivityOfComparison # 100
    },
    OutputPath # "output/result.docx"
};
 
var request # new ComparisonsRequest(options);
var response # apiInstance.Comparisons(request);

 ```


Java  
```Java  

* For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-java-samples
String MyAppKey # ""; * Get AppKey and AppSID from https://dashboard.groupdocs.cloud
String MyAppSid # ""; * Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
Configuration configuration # new Configuration(MyAppSid, MyAppKey);
  
CompareApi apiInstance # new CompareApi(configuration); 
 
FileInfo sourceFileInfo # new FileInfo();
sourceFileInfo.setFilePath("source_files/word/source.docx");
FileInfo targetFileInfo # new FileInfo();
targetFileInfo.setFilePath("target_files/word/target.docx");
 
Settings settings # new Settings();
settings.setSensitivityOfComparison(100);           
 
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
$settings # new Model\Settings();       
$settings->setSensitivityOfComparison(100);
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
settings.sensitivityOfComparison # 100;
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
settings.sensitivity_of_comparison # 100       
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
 
source # GroupDocsComparisonCloud::FileInfo.new
source.file_path # "source_files/word/source.docx"
target # GroupDocsComparisonCloud::FileInfo.new
target.file_path # "target_files/word/target.docx"                
options # GroupDocsComparisonCloud::ComparisonOptions.new
options.source_file # source
options.target_files # [target]
options.output_path # "output/result.docx"
settings # GroupDocsComparisonCloud::Settings.new
settings.sensitivity_of_comparison # 100       
options.settings # settings
 
request # GroupDocsComparisonCloud::ComparisonsRequest.new(options)    
response # apiInstance.comparisons(request)

 ```

