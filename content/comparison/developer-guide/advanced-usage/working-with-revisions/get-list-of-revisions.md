---
id: "get-list-of-revisions"
url: "comparison/get-list-of-revisions"
title: "Get list of revisions"
productName: "GroupDocs.Comparison Cloud"
weight: 1
description: ""
keywords: ""
toc: True
---



GroupDocs.Comparison Cloud allows to obtain list of revisions from Word document.

The following code sample demonstrates how to get list of all revisions.

## API usage

There are steps that usage of GroupDocs.Comparison Cloud consists of:

1. Upload input documents into cloud storage
1. Call API method
1. Download comparison result document from storage (if any)

Steps 1 and 3 are storage operations, please refer to this [File API documentation]({{< ref "comparison/developer-guide/working-with-file-api.md" >}}) for usage details.

[Swagger UI](https://apireference.groupdocs.cloud/comparison/) lets you call this REST API directly from the browser.

## cURL example

{{< tabs "example1">}} {{< tab "Request" >}}

```bash

// First get JSON Web Token
// Please get your Client Id and Client Secret from https://dashboard.groupdocs.cloud/applications. Kindly place Client Id in "client_id" and Client Secret in "client_secret" argument.
curl -v "https://api.groupdocs.cloud/connect/token" \
-X POST \
-d "grant_type=client_credentials&client_id=xxxx&client_secret=xxxx" \
-H "Content-Type: application/x-www-form-urlencoded" \
-H "Accept: application/json"
  
// cURL example to get document information
curl -v "https://api.groupdocs.cloud/v2.0/comparison/revisions" \
-X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-H "Authorization: Bearer <jwt token>"
-d "{
    'FilePath': 'source_files/word/source_with_revs.docx'
  }"

```

{{< /tab >}} {{< tab "Response" >}}

```javascript
[
  {
    "id": 0,
    "action": "None",
    "text": "\rsssssssss",
    "author": "GroupDpcs",
    "type": "Insertion"
  },
  {
    "id": 1,
    "action": "None",
    "text": "Many students, scholars and members of the \u0013 HYPERLINK \"https://en.wikipedia.org/wiki/Minister_(Christianity)\" \\o \"Minister (Christianity)\" \u0014Christian clergy\u0015 speak Latin fluently, and it is taught in primary, secondary and post-secondary educational institutions around the world.\u0013 HYPERLINK \"https://en.wikipedia.org/wiki/Latin\" \\l \"cite_note-4\" \u0014[4]\u0015\u0013 HYPERLINK \"https://en.wikipedia.org/wiki/Latin\" \\l \"cite_note-5\" \u0014[5]\u0015\r",
    "author": "GroupDocs",
    "type": "Deletion"
  }
]
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

var sourceFile = new FileInfo
    {
        FilePath = "source_files/word/source_with_revs.docx"
    };

var request = new GetRevisionsRequest(sourceFile);

var revisions = apiInstance.GetRevisions(request);
Console.WriteLine("GetListOfRevisions: Revisions count: " + revisions.Count);

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

GetRevisionsRequest request = new GetRevisionsRequest(sourceFileInfo);

List<RevisionInfo> rInfos = apiInstance.getRevisions(request);

System.out.println("Revisions count: " + rInfos.size());

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

$revisions = $apiInstance->getRevisions(new Requests\GetRevisionsRequest($sourceFile));
echo "Revisions count: ", count($revisions);
echo "\n";

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

 let request = new comparison_cloud.GetRevisionsRequest(source);  
 let revisions = await reviewApi.getRevisions(request);

 console.log("Revisions count: " + revisions.length);
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

revisions = api_instance.get_revisions(groupdocs_comparison_cloud.GetRevisionsRequest(source))

print("Revisions count: " + str(len(revisions)))

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

request = GroupDocsComparisonCloud::GetRevisionsRequest.new(source)
revisions = apiInstance.get_revisions(request)

puts("Revisions count: " + revisions.length.to_s)

```

{{< /tab >}} {{< /tabs >}}
