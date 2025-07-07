---
id: "quick-start"
url: "comparison/quick-start"
title: "Quick Start"
productName: "GroupDocs.Comparison Cloud"
weight: 3
description: ""
keywords: ""
toc: True
---

## Create an account

Creating an account is very simple. Go to [Dashboard](https://dashboard.groupdocs.cloud) to create a free account.\
We're using Single Sign On across our websites, therefore, if you already have an account with our services, you can use it to also acccess the [Dashboard](https://dashboard.groupdocs.cloud).

## Create an API client app

Before you can make any requests to GroupDocs Cloud API you need to get a **Client Id** and a **Client Secret**.
This will will be used to invoke GroupDocs Cloud API. You can get it by creating a new [Application](https://dashboard.groupdocs.cloud/applications).

## Install the SDK of your choice

GroupDocs Cloud SDK is written in different languages, all you need to get started is adding our [SDK]({{< ref "comparison/getting-started/available-sdks.md" >}}) to your existing project.

## Make an API request from the SDK of your choice

Use the **Client Id** and the **Client Secret** from the API app client you created in step one and replace in the corresponding code. Below is an example demonstrating how to compare two docx documents using GroupDocs.Comparison Cloud.

{{< alert style="info" >}}The GitHub repository for [GroupDocs.Comparison Cloud](https://github.com/groupdocs-comparison-cloud) has a complete set of examples, demonstrating our API capabilities.{{< /alert >}}

{{< tabs "example2">}} {{< tab "C#" >}}

```csharp

// For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-dotnet-samples
string MyClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
string MyClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

var configuration = new Configuration(MyClientId, MyClientSecret);

var apiInstance = new CompareApi(configuration);
var options = new ComparisonOptions
{
    SourceFile = new FileInfo {FilePath = "source_files/word/source.docx"},
    TargetFiles = new List<FileInfo> {new FileInfo {FilePath = "target_files/word/target.docx"}},
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
FileInfo targetFileInfo = new FileInfo();
targetFileInfo.setFilePath("target_files/word/target.docx");

ComparisonOptions options = new ComparisonOptions();
options.setSourceFile(sourceFileInfo);
options.addTargetFilesItem(targetFileInfo);
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
$options = new Model\ComparisonOptions();
$options->setSourceFile($sourceFile);
$options->setTargetFiles([$targetFile]);
$options->setOutputPath("output/result.docx");

$request = new Requests\ComparisonsRequest($options);
$response = $apiInstance->comparisons($request);

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
 let options = new comparison_cloud.ComparisonOptions();
 options.sourceFile = source;
 options.targetFiles = [target];
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
options = groupdocs_comparison_cloud.ComparisonOptions()
options.source_file = source
options.target_files = [target]
options.output_path = "output/result.docx"

request = groupdocs_comparison_cloud.ComparisonsRequest(options)
response = api_instance.comparisons(request)

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
options = GroupDocsComparisonCloud::ComparisonOptions.new
options.source_file = source
options.target_files = [target]
options.output_path = "output/result.docx"

request = GroupDocsComparisonCloud::ComparisonsRequest.new(options)
response = apiInstance.comparisons(request)

```
{{< /tab >}} {{< tab "Apex" >}}

```javascript
// Create configuration and API instances
Configuration config = new Configuration('YOUR_API_KEY', 'YOUR_API_SECRET'); // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
FileApi fileApi = new FileApi(config);
CompareApi compareApi = new CompareApi(config);

// Upload source Word file to cloud storage
List<ContentVersion> sourceVersions = [SELECT Id, Title, VersionData FROM ContentVersion WHERE Title = 'source.docx' LIMIT 1];
if (sourceVersions.size() > 0) {
    fileApi.uploadFile(new UploadFileRequest('source_files/word/source.docx', sourceVersions[0].VersionData, null));
}

// Upload target Word file to cloud storage
List<ContentVersion> targetVersions = [SELECT Id, Title, VersionData FROM ContentVersion WHERE Title = 'target.docx' LIMIT 1];
if (targetVersions.size() > 0) {
    fileApi.uploadFile(new UploadFileRequest('target_files/word/target.docx', targetVersions[0].VersionData, null));
}

// Set up comparison options
ComparisonOptions options = new ComparisonOptions();
options.SourceFile = new FileInfo();
options.SourceFile.FilePath = 'source_files/word/source.docx';

options.TargetFiles = new List<FileInfo>();
FileInfo targetFile = new FileInfo();
targetFile.FilePath = 'target_files/word/target.docx';
options.TargetFiles.add(targetFile);

options.OutputPath = 'output/result.docx';

// Execute comparison
ComparisonsRequest request = new ComparisonsRequest(options);
Link response = compareApi.comparisons(request);

// Debug the result
System.debug('Comparison complete. Output file link: ' + response.href);

```
{{< /tab >}} {{< /tabs >}}

