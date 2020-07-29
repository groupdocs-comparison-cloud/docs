---
id: "accept-or-reject-document-changes"
url: "comparison/accept-or-reject-document-changes"
title: "Accept or Reject document changes"
productName: "GroupDocs.Comparison Cloud"
weight: 2
description: ""
keywords: ""
---






# Introduction #

GroupDocs.Comparison Cloud provides an ability to apply or discard specific changes between source and target files and save result with (or without) selected changes. 

* **Changes** - List of changes that must be applied (or not) to the resulting document;

The following code sample shows how to accept/reject changes.

## API Usage ##

There are steps that usage of GroupDocs.Comparison Cloud consists of:

1. Upload input documents into cloud storage
1. Compare documents or get document info
1. Download comparison result document from storage

Steps 1 and 3 are storage operations, please refer to this [File API documentation>>path:/comparisoncloud/developer-guide/working-with-file-api/) for usage details.

[Swagger UI](https://apireference.groupdocs.cloud/comparison/) lets you call this REST API directly from the browser. 

## cURL REST Example ##



Curl example contains only 'updates' method call. For 'changes' method,  see other examples 



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
curl -v "https://api.groupdocs.cloud/v2.0/comparison/updates" \
-X PUT \
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
  'Changes':    
[
  {
    'id': 0,
    'comparisonAction': 'Accept'
  },
  {
    'id': 1,
    'comparisonAction': 'Reject'
  },
  {
    'id': 2,
    'comparisonAction': 'Reject'
  },
  {
    'id': 3,
    'comparisonAction': 'Reject'
  },
  {
    'id': 4,
    'comparisonAction': 'Reject'
  },
  {
    'id': 5,
    'comparisonAction': 'Reject'
  },
  {
    'id': 6,
    'comparisonAction': 'Reject'
  },
  {
    'id': 7,
    'comparisonAction': 'Reject'
  },
  {
    'id': 8,
    'comparisonAction': 'Reject'
  },
  {
    'id': 9,
    'comparisonAction': 'Reject'
  },
  {
    'id': 10,
    'comparisonAction': 'Reject'
  },
  {
    'id': 11,
    'comparisonAction': 'Reject'
  },
  {
    'id': 12,
    'comparisonAction': 'Reject'
  },
  {
    'id': 13,
    'comparisonAction': 'Reject'
  },
  {
    'id': 14,
    'comparisonAction': 'Reject'
  },
  {
    'id': 15,
    'comparisonAction': 'Reject'
  },
  {
    'id': 16,
    'comparisonAction': 'Reject'
  },
  {
    'id': 17,
    'comparisonAction': 'Reject'
  },
  {
    'id': 18,
    'comparisonAction': 'Reject'
  },
  {
    'id': 19,
    'comparisonAction': 'Reject'
  },
  {
    'id': 20,
    'comparisonAction': 'Reject'
  },
  {
    'id': 21,
    'comparisonAction': 'Reject'
  },
  {
    'id': 22,
    'comparisonAction': 'Reject'
  },
  {
    'id': 23,
    'comparisonAction': 'Reject'
  },
  {
    'id': 24,
    'comparisonAction': 'Reject'
  },
  {
    'id': 25,
    'comparisonAction': 'Reject'
  },
  {
    'id': 26,
    'comparisonAction': 'Reject'
  },
  {
    'id': 27,
    'comparisonAction': 'Reject'
  },
  {
    'id': 28,
    'comparisonAction': 'Reject'   
  },
  {
    'id': 29,
    'comparisonAction': 'Reject'
  }
]
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

Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/groupdocs-comparison-cloud) for a complete list of GroupDocs.Comparison Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs>>path:/comparisoncloud/getting-started/available-sdks/) article to learn how to add an SDK to your project.

### SDK Examples ###


 C#
```csharp 

* For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-dotnet-samples
string MyAppKey # ""; * Get AppKey and AppSID from https://dashboard.groupdocs.cloud
string MyAppSid # ""; * Get AppKey and AppSID from https://dashboard.groupdocs.cloud
  
var configuration # new Configuration(MyAppSid, MyAppKey);
  
var apiInstance # new CompareApi(configuration);
var options # new UpdatesOptions
{
    SourceFile # new FileInfo {FilePath # "source_files/word/source.docx"},
    TargetFiles # new List<FileInfo> {new FileInfo {FilePath # "target_files/word/target.docx"}},
    OutputPath # "output/result.docx"
};
 
var changes # apiInstance.PostChanges(new PostChangesRequest(options));
 
foreach (var change in changes)
    change.ComparisonAction # ChangeInfo.ComparisonActionEnum.Reject;
 
changes[0].ComparisonAction # ChangeInfo.ComparisonActionEnum.Accept;
 
options.Changes # changes;
 
var response # apiInstance.PutChangesDocument(new PutChangesDocumentRequest(options));

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
 
UpdatesOptions options # new UpdatesOptions();
options.setSourceFile(sourceFileInfo);
options.addTargetFilesItem(targetFileInfo);
options.setOutputPath("output/result.docx");
 
PostChangesRequest request # new PostChangesRequest(options);
 
List<ChangeInfo> changes # apiInstance.postChanges(request);
for (ChangeInfo change : changes) {
    change.setComparisonAction(ComparisonActionEnum.REJECT);
}
changes.get(0).setComparisonAction(ComparisonActionEnum.REJECT);
options.setChanges(changes);
Link response # apiInstance.putChangesDocument(new PutChangesDocumentRequest(options));

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
$options # new Model\UpdatesOptions();
$options->setSourceFile($sourceFile);
$options->setTargetFiles([$targetFile]);
$options->setOutputPath("output/result.docx");
 
$changes # $apiInstance->postChanges(new Requests\PostChangesRequest($options));
for ($i#0; $i < count($changes); $i++) { 
    $changes[$i]->setComparisonAction(Model\ChangeInfo::COMPARISON_ACTION_REJECT);
}
$changes[0]->setComparisonAction(Model\ChangeInfo::COMPARISON_ACTION_ACCEPT);
$options->setChanges($changes);
$request # new Requests\PutChangesDocumentRequest($options);
$response # $apiInstance->putChangesDocument($request);

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
 
let options # new comparison_cloud.UpdatesOptions();
options.sourceFile # source;
options.targetFiles # [target];
options.outputPath # "output/result.docx";
 
let changes # await compareApi.postChanges(new comparison_cloud.PostChangesRequest(options));
 
changes.forEach(change #> {
    change.comparisonAction # comparison_cloud.ChangeInfo.ComparisonActionEnum.Reject;
}); 
changes[0].comparisonAction # comparison_cloud.ChangeInfo.ComparisonActionEnum.Accept;
options.changes # changes;
 
let response # await compareApi.putChangesDocument(new comparison_cloud.PutChangesDocumentRequest(options));

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
options # groupdocs_comparison_cloud.UpdatesOptions()
options.source_file # source
options.target_files # [target] 
options.output_path # "output/result.docx"
 
changes # api_instance.post_changes(groupdocs_comparison_cloud.PostChangesRequest(options))
 
for change in changes:
    change.comparison_action # "Reject"
changes[0].comparison_action # "Accept"
 
options.changes # changes
 
response # api_instance.put_changes_document(groupdocs_comparison_cloud.PutChangesDocumentRequest(options))

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
options # GroupDocsComparisonCloud::UpdatesOptions.new
options.source_file # source
options.target_files # [target]
options.output_path # "output/result.docx"
 
changes # apiInstance.post_changes(GroupDocsComparisonCloud::PostChangesRequest.new(options))
for change in changes do
    change.comparison_action # "Reject"
end
changes[0].comparison_action # "Accept"
 
options.changes # changes
 
response # apiInstance.put_changes_document(GroupDocsComparisonCloud::PutChangesDocumentRequest.new(options))

 ```

