---
id: "accept-all-revisions"
url: "comparison/accept-all-revisions"
title: "Accept all revisions"
productName: "GroupDocs.Comparison Cloud"
weight: 3
description: ""
keywords: ""
---

# Introduction #

GroupDocs.Comparison Cloud allows to accept all revisions in Word document and save the result.

The following code sample demonstrates how to accept all revisions without getting them.

## API Usage ##

There are steps that usage of GroupDocs.Comparison Cloud consists of:

1. Upload input documents into cloud storage
1. Call API method with options
1. Download comparison result document from storage (if any)

Steps 1 and 3 are storage operations, please refer to this [File API documentation]({{< ref "comparison/developer-guide/working-with-file-api.md" >}}) for usage details.

[Swagger UI](https://apireference.groupdocs.cloud/comparison/) lets you call this REST API directly from the browser.

## cURL REST Example ##

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}} {{< tab tabNum="1" >}}

```html

// First get JSON Web Token
// Please get your Client Id and Client Secret from https://dashboard.groupdocs.cloud/applications. Kindly place Client Id in "client_id" and Client Secret in "client_secret" argument.
curl -v "https://api.groupdocs.cloud/connect/token" \
-X POST \
-d "grant_type=client_credentials&client_id=xxxx&client_secret=xxxx" \
-H "Content-Type: application/x-www-form-urlencoded" \
-H "Accept: application/json"
  
// cURL example to get document information
curl -v "https://api.groupdocs.cloud/v2.0/comparison/revisions" \
-X PUT \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-H "Authorization: Bearer <jwt token>"
-d "{
  'SourceFile': {
    'FilePath': 'source_files/word/source_with_revs.docx'
  },
  'AcceptAll': true,
  'OutputPath': 'output/result.docx'
}"

```

{{< /tab >}} {{< tab tabNum="2" >}}

```javascript
{
  "href": "https://api.groupdocs.cloud/v2.0/comparison/storage/file/output/result.docx",
  "rel": "output/result.docx",
  "type": "file",
  "title": "result.docx"
}
```

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
  
var apiInstance = new ReviewApi(configuration);

var options = new ApplyRevisionsOptions
{
    SourceFile = new FileInfo {FilePath = "source_files/word/source_with_revs.docx" },
    AcceptAll = true,
    OutputPath = "output/result.docx"
};

var response = apiInstance.ApplyRevisions(new ApplyRevisionsRequest(options));

Console.WriteLine("ApplyRevisions: Output file link: " + response.Href);

```

{{< /tab >}} {{< tab tabNum="2" >}}

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
options.setAcceptAll(true);
options.setOutputPath("output/result.docx");

Link response = apiInstance.applyRevisions(new ApplyRevisionsRequest(options));

System.out.println("Output file link: " + response.getHref());

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

$apiInstance= new GroupDocs\Comparison\ReviewApi($configuration);

$sourceFile = new Model\FileInfo();
$sourceFile->setFilePath("source_files/word/source_with_revs.docx");
$options = new Model\ApplyRevisionsOptions();
$options->setSourceFile($sourceFile);
$options->setAcceptAll(true);
$options->setOutputPath("output/result.docx");

$request = new Requests\ApplyRevisionsRequest($options);
$response = $apiInstance->applyRevisions($request);

echo "Output file link: ", $response->getHref();

```

{{< /tab >}} {{< tab tabNum="4" >}}

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
 options.acceptAll = true;
 options.outputPath = "output/result.docx";
 
 let response = await reviewApi.applyRevisions(new comparison_cloud.ApplyRevisionsRequest(options));
 console.log("Output file link: " + response.href);
} catch (error) {
 console.log(error.message);
}

```

{{< /tab >}} {{< tab tabNum="5" >}}

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
options.accept_all = True
options.output_path = "output/result.docx"

response = api_instance.apply_revisions(groupdocs_comparison_cloud.ApplyRevisionsRequest(options))

print("Output file link: " + response.href)

```

{{< /tab >}} {{< tab tabNum="6" >}}

```ruby

# For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-ruby-samples
require 'groupdocs_comparison_cloud'

$client_id = "XXXX-XXXX-XXXX-XXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
$client_secret = "XXXXXXXXXXXXXXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

api_instance = GroupDocsComparisonCloud::ReviewApi.from_keys($client_id, $client_secret)

source = GroupDocsComparisonCloud::FileInfo.new
source.file_path = "source_files/word/source_with_revs.docx"
 
source = GroupDocsComparisonCloud::FileInfo.new
source.file_path = "source_files/word/source_with_revs.docx"
 
options = GroupDocsComparisonCloud::ApplyRevisionsOptions.new
options.source_file = source
options.accept_all = true
options.output_path = "output/result.docx"

response = apiInstance.apply_revisions(GroupDocsComparisonCloud::ApplyRevisionsRequest.new(options))

puts("Output file link: " + response.href)

```

{{< /tab >}} {{< /tabs >}}
