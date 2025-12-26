---
id: "accept-reject-revisions"
url: "comparison/accept-reject-revisions"
title: "Accept or reject revisions"
productName: "GroupDocs.Comparison Cloud"
weight: 2
description: ""
keywords: ""
toc: True
---



GroupDocs.Comparison Cloud allows to accept or reject revisions from Word document and save the result.

The following code sample demonstrates how to accept all revisions.

## API usage

There are steps that usage of GroupDocs.Comparison Cloud consists of:

1. Upload input documents into cloud storage
1. Call API method with options
1. Download comparison result document from storage (if any)

Steps 1 and 3 are storage operations, please refer to this [File API documentation]({{< ref "comparison/developer-guide/working-with-file-api.md" >}}) for usage details.

[Swagger UI](https://apireference.groupdocs.cloud/comparison/) lets you call this REST API directly from the browser.

## cURL example

{{< tabs "example1">}} {{< tab "Linux/MacOS/Bash" >}}

```bash
# First get JSON Web Token
# Please get your Client Id and Client Secret from https://dashboard.groupdocs.cloud/applications.
curl -v "https://api.groupdocs.cloud/connect/token" \
  -X POST \
  -d "grant_type=client_credentials&client_id=$CLIENT_ID&client_secret=$CLIENT_SECRET" \
  -H "Content-Type: application/x-www-form-urlencoded" \
  -H "Accept: application/json"

# cURL example to get document information
curl -v "https://api.groupdocs.cloud/v2.0/comparison/revisions" \
  -X PUT \
  -H "Content-Type: application/json" \
  -H "Accept: application/json" \
  -H "Authorization: Bearer $JWT_TOKEN" \
  -d '{
    "SourceFile": {
      "FilePath": "source_files/word/source_with_revs.docx"
    },
    "Revisions": [
      {
        "Id": 0,
        "action": "Accept"
      },
      {
        "Id": 1,
        "action": "Accept"
      }
    ],
    "OutputPath": "output/result.docx"
  }'
```

{{< /tab >}}

{{< tab "Windows PowerShell" >}}

```powershell
# First get JSON Web Token
# Please get your Client Id and Client Secret from https://dashboard.groupdocs.cloud/applications.
curl.exe -v "https://api.groupdocs.cloud/connect/token" `
  -X POST `
  -d "grant_type=client_credentials&client_id=$env:CLIENT_ID&client_secret=$env:CLIENT_SECRET" `
  -H "Content-Type: application/x-www-form-urlencoded" `
  -H "Accept: application/json"

# cURL example to get document information
curl.exe -v "https://api.groupdocs.cloud/v2.0/comparison/revisions" `
  -X PUT `
  -H "Content-Type: application/json" `
  -H "Accept: application/json" `
  -H "Authorization: Bearer $env:JWT_TOKEN" `
  -d "{
    'SourceFile': {
      'FilePath': 'source_files/word/source_with_revs.docx'
    },
    'Revisions': [
      {
        'Id': 0,
        'action': 'Accept'
      },
      {
        'Id': 1,
        'action': 'Accept'
      }
    ],
    'OutputPath': 'output/result.docx'
  }"
```

{{< /tab >}}

{{< tab "Windows CMD" >}}

```cmd
:: First get JSON Web Token
:: Please get your Client Id and Client Secret from https://dashboard.groupdocs.cloud/applications.
curl -v "https://api.groupdocs.cloud/connect/token" ^
  -X POST ^
  -d "grant_type=client_credentials&client_id=%CLIENT_ID%&client_secret=%CLIENT_SECRET%" ^
  -H "Content-Type: application/x-www-form-urlencoded" ^
  -H "Accept: application/json"

:: cURL example to get document information
curl -v "https://api.groupdocs.cloud/v2.0/comparison/revisions" ^
  -X PUT ^
  -H "Content-Type: application/json" ^
  -H "Accept: application/json" ^
  -H "Authorization: Bearer %JWT_TOKEN%" ^
  -d "{\"SourceFile\":{\"FilePath\":\"source_files/word/source_with_revs.docx\"},\"Revisions\":[{\"Id\":0,\"action\":\"Accept\"},{\"Id\":1,\"action\":\"Accept\"}],\"OutputPath\":\"output/result.docx\"}"
```

{{< /tab >}} {{< tab "Response" >}}

```javascript
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
  
var apiInstance = new ReviewApi(configuration);

var options = new ApplyRevisionsOptions
{
    SourceFile = new FileInfo {FilePath = "source_files/word/source_with_revs.docx" },
    OutputPath = "output/result.docx"
};

var revisions = apiInstance.GetRevisions(new GetRevisionsRequest(options.SourceFile));

foreach (var revision in revisions)
    revision.Action = RevisionInfo.ActionEnum.Accept;

options.Revisions = revisions;

var response = apiInstance.ApplyRevisions(new ApplyRevisionsRequest(options));

Console.WriteLine("ApplyRevisions: Output file link: " + response.Href);

```

{{< /tab >}} {{< tab "Java" >}}

```Java

// For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-java-samples
String MyClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
String MyClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

Configuration configuration = new Configuration(MyClientId, MyClientSecret);
  
ReviewApi apiInstance = new ReviewApi(configuration);

FileInfo sourceFileInfo = new FileInfo();
sourceFileInfo.setFilePath("source_files/word/source_with_revs.docx");

ApplyRevisionsOptions options = new ApplyRevisionsOptions();
options.setSourceFile(sourceFileInfo);
options.setOutputPath("output/result.docx");

GetRevisionsRequest request = new GetRevisionsRequest(sourceFileInfo);
List<RevisionInfo> rInfos = apiInstance.getRevisions(request);

for (RevisionInfo rInfo : rInfos) {
    rInfo.setAction(ActionEnum.ACCEPT);
}
options.setRevisions(rInfos);
Link response = apiInstance.applyRevisions(new ApplyRevisionsRequest(options));

System.out.println("Output file link: " + response.getHref());

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

$apiInstance= new GroupDocs\Comparison\ReviewApi($configuration);

$sourceFile = new Model\FileInfo();
$sourceFile->setFilePath("source_files/word/source_with_revs.docx");
$options = new Model\ApplyRevisionsOptions();
$options->setSourceFile($sourceFile);
$options->setOutputPath("output/result.docx");

$revisions = $apiInstance->getRevisions(new Requests\GetRevisionsRequest($sourceFile));
for ($i=0; $i < count($revisions); $i++) { 
    $revisions[$i]->setAction(Model\RevisionInfo::ACTION_ACCEPT);
}
$options->setRevisions($revisions);
$request = new Requests\ApplyRevisionsRequest($options);
$response = $apiInstance->applyRevisions($request);

echo "Output file link: ", $response->getHref();

```

{{< /tab >}} {{< tab "Node.js" >}}

```javascript

// For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-node-samples
global.comparison_cloud = require("groupdocs-comparison-cloud");

global.clientId = "XXXX-XXXX-XXXX-XXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
global.clientSecret = "XXXXXXXXXXXXXXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

global.reviewApi = comparison_cloud.ReviewApi.fromKeys(clientId, clientSecret);

try {
 let source = new comparison_cloud.FileInfo();
 source.filePath = "source_files/word/source_with_revs.docx";

 let options = new comparison_cloud.ApplyRevisionsOptions();
 options.sourceFile = source;
 options.outputPath = "output/result.docx";
 
 let request = new comparison_cloud.GetRevisionsRequest(source);  
 let revisions = await reviewApi.getRevisions(request);

 revisions.forEach(revision => {
  revision.action = comparison_cloud.RevisionInfo.ActionEnum.Accept;
 }); 
 options.revisions = revisions;

 let response = await reviewApi.applyRevisions(new comparison_cloud.ApplyRevisionsRequest(options));
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

api_instance = groupdocs_comparison_cloud.ReviewApi.from_keys(client_id, client_secret)

source = groupdocs_comparison_cloud.FileInfo()
source.file_path = "source_files/word/source_with_revs.docx"
options = groupdocs_comparison_cloud.ApplyRevisionsOptions()
options.source_file = source
options.output_path = "output/result.docx"

revisions = api_instance.get_revisions(groupdocs_comparison_cloud.GetRevisionsRequest(source))

for revision in revisions:
    revision.action = "Accept"

options.revisions = revisions

response = api_instance.apply_revisions(groupdocs_comparison_cloud.ApplyRevisionsRequest(options))

print("Output file link: " + response.href)

```

{{< /tab >}} {{< tab "Ruby" >}}

```ruby

# For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-ruby-samples
require 'groupdocs_comparison_cloud'

$client_id = "XXXX-XXXX-XXXX-XXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
$client_secret = "XXXXXXXXXXXXXXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

api_instance = GroupDocsComparisonCloud::ReviewApi.from_keys($client_id, $client_secret)

source = GroupDocsComparisonCloud::FileInfo.new
source.file_path = "source_files/word/source_with_revs.docx"

options = GroupDocsComparisonCloud::ApplyRevisionsOptions.new
options.source_file = source
options.output_path = "output/result.docx"

request = GroupDocsComparisonCloud::GetRevisionsRequest.new(source)    
revisions = apiInstance.get_revisions(request)

for revision in revisions do
    revision.action = "Accept"
end

options.revisions = revisions

response = apiInstance.apply_revisions(GroupDocsComparisonCloud::ApplyRevisionsRequest.new(options))

puts("Output file link: " + response.href)

```
{{< /tab >}} {{< tab "Apex" >}}

```javascript
// Create configuration and API instances
Configuration config = new Configuration('YOUR_API_KEY', 'YOUR_API_SECRET'); // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
FileApi fileApi = new FileApi(config);
ReviewApi reviewApi = new ReviewApi(config);

// Upload source file with revisions to cloud storage
List<ContentVersion> sourceVersions = [SELECT Id, Title, VersionData FROM ContentVersion WHERE Title = 'source_with_revs.docx' LIMIT 1];
if (sourceVersions.size() > 0) {
    fileApi.uploadFile(new UploadFileRequest('source_files/word/source_with_revs.docx', sourceVersions[0].VersionData, null));
}

// Set up options for retrieving and applying revisions
ApplyRevisionsOptions options = new ApplyRevisionsOptions();
options.SourceFile = new FileInfo();
options.SourceFile.FilePath = 'source_files/word/source_with_revs.docx';
options.OutputPath = 'output/result.docx';

// Retrieve revisions from the document
GetRevisionsRequest getRevisionsRequest = new GetRevisionsRequest(options.SourceFile);
List<RevisionInfo> revisions = reviewApi.getRevisions(getRevisionsRequest);

// Accept all revisions
for (RevisionInfo revision : revisions) {
    revision.Action = 'Accept'; // Set action to 'Accept' for each revision
}

// Apply revisions
options.Revisions = revisions;
ApplyRevisionsRequest applyRevisionsRequest = new ApplyRevisionsRequest(options);
ApplyRevisionsResult result = reviewApi.applyRevisions(applyRevisionsRequest);

// Debug the result
System.debug('ApplyRevisions: Output file link: ' + result.href);

```
{{< /tab >}} {{< /tabs >}}
