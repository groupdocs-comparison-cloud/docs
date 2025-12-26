---
id: "accept-or-reject-document-changes"
url: "comparison/accept-or-reject-document-changes"
title: "Accept or Reject document changes"
productName: "GroupDocs.Comparison Cloud"
weight: 2
description: ""
keywords: ""
toc: True
---

GroupDocs.Comparison Cloud provides an ability to apply or discard specific changes between source and target files and save result with (or without) selected changes.

* **Changes** - List of changes that must be applied (or not) to the resulting document;

The following code sample shows how to accept/reject changes.

## API usage

There are steps that usage of GroupDocs.Comparison Cloud consists of:

1. Upload input documents into cloud storage
1. Compare documents or get document info
1. Download comparison result document from storage

Steps 1 and 3 are storage operations, please refer to this [File API documentation]({{< ref "comparison/developer-guide/working-with-file-api.md" >}}) for usage details.

[Swagger UI](https://apireference.groupdocs.cloud/comparison/) lets you call this REST API directly from the browser.

## cURL example

Curl example contains only 'updates' method call. For 'changes' method,  see other examples

{{< tabs "example1">}} {{< tab "Linux/MacOS/Bash" >}}

```bash
# Get JSON Web Token
curl -v "https://api.groupdocs.cloud/connect/token" \
  -X POST \
  -d "grant_type=client_credentials&client_id=$CLIENT_ID&client_secret=$CLIENT_SECRET" \
  -H "Content-Type: application/x-www-form-urlencoded" \
  -H "Accept: application/json"

# Get document comparison information
curl -v "https://api.groupdocs.cloud/v2.0/comparison/updates" \
  -X PUT \
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
      }
    ],
    "OutputPath": "output/result.docx",
    "Changes": [
      {"id": 0, "comparisonAction": "Accept"},
      {"id": 1, "comparisonAction": "Reject"},
      {"id": 2, "comparisonAction": "Reject"},
      {"id": 3, "comparisonAction": "Reject"},
      {"id": 4, "comparisonAction": "Reject"},
      {"id": 5, "comparisonAction": "Reject"},
      {"id": 6, "comparisonAction": "Reject"},
      {"id": 7, "comparisonAction": "Reject"},
      {"id": 8, "comparisonAction": "Reject"},
      {"id": 9, "comparisonAction": "Reject"},
      {"id": 10, "comparisonAction": "Reject"},
      {"id": 11, "comparisonAction": "Reject"},
      {"id": 12, "comparisonAction": "Reject"},
      {"id": 13, "comparisonAction": "Reject"},
      {"id": 14, "comparisonAction": "Reject"},
      {"id": 15, "comparisonAction": "Reject"},
      {"id": 16, "comparisonAction": "Reject"},
      {"id": 17, "comparisonAction": "Reject"},
      {"id": 18, "comparisonAction": "Reject"},
      {"id": 19, "comparisonAction": "Reject"},
      {"id": 20, "comparisonAction": "Reject"},
      {"id": 21, "comparisonAction": "Reject"},
      {"id": 22, "comparisonAction": "Reject"},
      {"id": 23, "comparisonAction": "Reject"},
      {"id": 24, "comparisonAction": "Reject"},
      {"id": 25, "comparisonAction": "Reject"},
      {"id": 26, "comparisonAction": "Reject"},
      {"id": 27, "comparisonAction": "Reject"},
      {"id": 28, "comparisonAction": "Reject"},
      {"id": 29, "comparisonAction": "Reject"}
    ]
  }'
```

{{< /tab >}}

{{< tab "Windows PowerShell" >}}

```powershell
# Get JSON Web Token
curl.exe -v "https://api.groupdocs.cloud/connect/token" `
  -X POST `
  -d "grant_type=client_credentials&client_id=$env:CLIENT_ID&client_secret=$env:CLIENT_SECRET" `
  -H "Content-Type: application/x-www-form-urlencoded" `
  -H "Accept: application/json"

# Get document comparison information
curl.exe -v "https://api.groupdocs.cloud/v2.0/comparison/updates" `
  -X PUT `
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
      }
    ],
    'OutputPath': 'output/result.docx',
    'Changes': [
      {'id': 0, 'comparisonAction': 'Accept'},
      {'id': 1, 'comparisonAction': 'Reject'},
      {'id': 2, 'comparisonAction': 'Reject'},
      {'id': 3, 'comparisonAction': 'Reject'},
      {'id': 4, 'comparisonAction': 'Reject'},
      {'id': 5, 'comparisonAction': 'Reject'},
      {'id': 6, 'comparisonAction': 'Reject'},
      {'id': 7, 'comparisonAction': 'Reject'},
      {'id': 8, 'comparisonAction': 'Reject'},
      {'id': 9, 'comparisonAction': 'Reject'},
      {'id': 10, 'comparisonAction': 'Reject'},
      {'id': 11, 'comparisonAction': 'Reject'},
      {'id': 12, 'comparisonAction': 'Reject'},
      {'id': 13, 'comparisonAction': 'Reject'},
      {'id': 14, 'comparisonAction': 'Reject'},
      {'id': 15, 'comparisonAction': 'Reject'},
      {'id': 16, 'comparisonAction': 'Reject'},
      {'id': 17, 'comparisonAction': 'Reject'},
      {'id': 18, 'comparisonAction': 'Reject'},
      {'id': 19, 'comparisonAction': 'Reject'},
      {'id': 20, 'comparisonAction': 'Reject'},
      {'id': 21, 'comparisonAction': 'Reject'},
      {'id': 22, 'comparisonAction': 'Reject'},
      {'id': 23, 'comparisonAction': 'Reject'},
      {'id': 24, 'comparisonAction': 'Reject'},
      {'id': 25, 'comparisonAction': 'Reject'},
      {'id': 26, 'comparisonAction': 'Reject'},
      {'id': 27, 'comparisonAction': 'Reject'},
      {'id': 28, 'comparisonAction': 'Reject'},
      {'id': 29, 'comparisonAction': 'Reject'}
    ]
  }"
```

{{< /tab >}}

{{< tab "Windows CMD" >}}

```cmd
:: Get JSON Web Token
curl -v "https://api.groupdocs.cloud/connect/token" ^
  -X POST ^
  -d "grant_type=client_credentials&client_id=%CLIENT_ID%&client_secret=%CLIENT_SECRET%" ^
  -H "Content-Type: application/x-www-form-urlencoded" ^
  -H "Accept: application/json"

:: Get document comparison information
curl -v "https://api.groupdocs.cloud/v2.0/comparison/updates" ^
  -X PUT ^
  -H "Content-Type: application/json" ^
  -H "Accept: application/json" ^
  -H "Authorization: Bearer %JWT_TOKEN%" ^
  -d "{\"SourceFile\":{\"FilePath\":\"source_files\\word\\source.docx\"},\"TargetFiles\":[{\"FilePath\":\"target_files\\word\\target.docx\"}],\"OutputPath\":\"output/result.docx\",\"Changes\":[{\"id\":0,\"comparisonAction\":\"Accept\"},{\"id\":1,\"comparisonAction\":\"Reject\"},{\"id\":2,\"comparisonAction\":\"Reject\"},{\"id\":3,\"comparisonAction\":\"Reject\"},{\"id\":4,\"comparisonAction\":\"Reject\"},{\"id\":5,\"comparisonAction\":\"Reject\"},{\"id\":6,\"comparisonAction\":\"Reject\"},{\"id\":7,\"comparisonAction\":\"Reject\"},{\"id\":8,\"comparisonAction\":\"Reject\"},{\"id\":9,\"comparisonAction\":\"Reject\"},{\"id\":10,\"comparisonAction\":\"Reject\"},{\"id\":11,\"comparisonAction\":\"Reject\"},{\"id\":12,\"comparisonAction\":\"Reject\"},{\"id\":13,\"comparisonAction\":\"Reject\"},{\"id\":14,\"comparisonAction\":\"Reject\"},{\"id\":15,\"comparisonAction\":\"Reject\"},{\"id\":16,\"comparisonAction\":\"Reject\"},{\"id\":17,\"comparisonAction\":\"Reject\"},{\"id\":18,\"comparisonAction\":\"Reject\"},{\"id\":19,\"comparisonAction\":\"Reject\"},{\"id\":20,\"comparisonAction\":\"Reject\"},{\"id\":21,\"comparisonAction\":\"Reject\"},{\"id\":22,\"comparisonAction\":\"Reject\"},{\"id\":23,\"comparisonAction\":\"Reject\"},{\"id\":24,\"comparisonAction\":\"Reject\"},{\"id\":25,\"comparisonAction\":\"Reject\"},{\"id\":26,\"comparisonAction\":\"Reject\"},{\"id\":27,\"comparisonAction\":\"Reject\"},{\"id\":28,\"comparisonAction\":\"Reject\"},{\"id\":29,\"comparisonAction\":\"Reject\"}]}"
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
var options = new UpdatesOptions
{
    SourceFile = new FileInfo {FilePath = "source_files/word/source.docx"},
    TargetFiles = new List<FileInfo> {new FileInfo {FilePath = "target_files/word/target.docx"}},
    OutputPath = "output/result.docx"
};

var changes = apiInstance.PostChanges(new PostChangesRequest(options));

foreach (var change in changes)
    change.ComparisonAction = ChangeInfo.ComparisonActionEnum.Reject;

changes[0].ComparisonAction = ChangeInfo.ComparisonActionEnum.Accept;

options.Changes = changes;

var response = apiInstance.PutChangesDocument(new PutChangesDocumentRequest(options));

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
FileInfo targetFileInfo = new FileInfo();
targetFileInfo.setFilePath("target_files/word/target.docx");

UpdatesOptions options = new UpdatesOptions();
options.setSourceFile(sourceFileInfo);
options.addTargetFilesItem(targetFileInfo);
options.setOutputPath("output/result.docx");

PostChangesRequest request = new PostChangesRequest(options);

List<ChangeInfo> changes = apiInstance.postChanges(request);
for (ChangeInfo change : changes) {
    change.setComparisonAction(ComparisonActionEnum.REJECT);
}
changes.get(0).setComparisonAction(ComparisonActionEnum.REJECT);
options.setChanges(changes);
Link response = apiInstance.putChangesDocument(new PutChangesDocumentRequest(options));

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
$options = new Model\UpdatesOptions();
$options->setSourceFile($sourceFile);
$options->setTargetFiles([$targetFile]);
$options->setOutputPath("output/result.docx");

$changes = $apiInstance->postChanges(new Requests\PostChangesRequest($options));
for ($i=0; $i < count($changes); $i++) {
    $changes[$i]->setComparisonAction(Model\ChangeInfo::COMPARISON_ACTION_REJECT);
}
$changes[0]->setComparisonAction(Model\ChangeInfo::COMPARISON_ACTION_ACCEPT);
$options->setChanges($changes);
$request = new Requests\PutChangesDocumentRequest($options);
$response = $apiInstance->putChangesDocument($request);

```

{{< /tab >}} {{< tab "Node.js" >}}

```javascript

// For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-node-samples
global.comparison_cloud = require("groupdocs-comparison-cloud");

global.clientId = "XXXX-XXXX-XXXX-XXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
global.clientSecret = "XXXXXXXXXXXXXXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

global.compareApi = comparison_cloud.CompareApi.fromKeys(clientId, clientSecret);

try {
 let source = new comparison_cloud.FileInfo();
 source.filePath = "source_files/word/source.docx";
 let target = new comparison_cloud.FileInfo();
 target.filePath = "target_files/word/target.docx";  
 
 let options = new comparison_cloud.UpdatesOptions();
 options.sourceFile = source;
 options.targetFiles = [target];
 options.outputPath = "output/result.docx";
 
 let changes = await compareApi.postChanges(new comparison_cloud.PostChangesRequest(options));

 changes.forEach(change => {
  change.comparisonAction = comparison_cloud.ChangeInfo.ComparisonActionEnum.Reject;
 }); 
 changes[0].comparisonAction = comparison_cloud.ChangeInfo.ComparisonActionEnum.Accept;
 options.changes = changes;

 let response = await compareApi.putChangesDocument(new comparison_cloud.PutChangesDocumentRequest(options));
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
options = groupdocs_comparison_cloud.UpdatesOptions()
options.source_file = source
options.target_files = [target]
options.output_path = "output/result.docx"

changes = api_instance.post_changes(groupdocs_comparison_cloud.PostChangesRequest(options))

for change in changes:
    change.comparison_action = "Reject"
changes[0].comparison_action = "Accept"

options.changes = changes

response = api_instance.put_changes_document(groupdocs_comparison_cloud.PutChangesDocumentRequest(options))

```

{{< /tab >}} {{< tab "Ruby" >}}

```ruby

# For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-ruby-samples
require 'groupdocs_comparison_cloud'

$client_id = "XXXX-XXXX-XXXX-XXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
$client_secret = "XXXXXXXXXXXXXXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

api_instance = GroupDocsComparisonCloud::CompareApi.from_keys($client_id, $client_secret)

source = GroupDocsComparisonCloud::FileInfo.new
source.file_path = "source_files/word/source.docx"
target = GroupDocsComparisonCloud::FileInfo.new
target.file_path = "target_files/word/target.docx"
options = GroupDocsComparisonCloud::UpdatesOptions.new
options.source_file = source
options.target_files = [target]
options.output_path = "output/result.docx"

changes = apiInstance.post_changes(GroupDocsComparisonCloud::PostChangesRequest.new(options))
for change in changes do
    change.comparison_action = "Reject"
end
changes[0].comparison_action = "Accept"

options.changes = changes

response = apiInstance.put_changes_document(GroupDocsComparisonCloud::PutChangesDocumentRequest.new(options))

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

// Upload target file to cloud storage
List<ContentVersion> targetVersions = [SELECT Id, Title, VersionData FROM ContentVersion WHERE Title = 'target.docx' LIMIT 1];
if (targetVersions.size() > 0) {
    fileApi.uploadFile(new UploadFileRequest('target_files/word/target.docx', targetVersions[0].VersionData, null));
}

// Set up update options
UpdatesOptions options = new UpdatesOptions();
options.SourceFile = new FileInfo();
options.SourceFile.FilePath = 'source_files/word/source.docx';

options.TargetFiles = new List<FileInfo>();
FileInfo targetFileInfo = new FileInfo();
targetFileInfo.FilePath = 'target_files/word/target.docx';
options.TargetFiles.add(targetFileInfo);

options.OutputPath = 'output/result.docx';

// Get changes from comparison
List<ChangeInfo> changes = compareApi.postChanges(new PostChangesRequest(options));

// Modify changes: reject all by default
for (ChangeInfo change : changes) {
    change.ComparisonAction = 'Reject';
}

// Accept the first change
if (!changes.isEmpty()) {
    changes[0].ComparisonAction = 'Accept';
}

// Apply changes to the document
options.Changes = changes;
CompareResult result = compareApi.putChangesDocument(new PutChangesDocumentRequest(options));

// Debug the result
System.debug('Changes applied. Output file path: ' + result.href);

```
{{< /tab >}} {{< /tabs >}}
