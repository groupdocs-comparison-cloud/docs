---
id: "get-changes-without-cloud-storage"
url: "comparison/get-changes-without-cloud-storage"
title: "Get list of changes without cloud storage"
productName: "GroupDocs.Comparison Cloud"
weight: 11
description: ""
keywords: ""
toc: True
---

GroupDocs.Comparison Cloud allows you to get a list of changes between source and target documents by sending the files **directly in the request body** as multipart/form-data. No prior upload to cloud storage is required.

This is especially useful when you already have the document bytes in memory or on disk and prefer a single round-trip call instead of a separate upload step.

## API usage

The `PUT /comparison/changes` endpoint accepts files as multipart/form-data form fields:

| Field | Required | Description |
|---|---|---|
| `sourceFile` | Yes | Source document file |
| `targetFiles` | Yes | One or more target document files |
| `settings` | No | Comparison settings serialized as JSON |
| `changeType` | No | Change type filter (e.g. `Inserted`, `Deleted`) |

The endpoint returns an array of `ChangeInfo` objects describing every detected change.

[Swagger UI](https://apireference.groupdocs.cloud/comparison/) lets you call this REST API directly from the browser.

## cURL example

{{< tabs "example1">}} {{< tab "Linux/MacOS/Bash" >}}

```bash
# Get JSON Web Token
curl -v "https://api.groupdocs.cloud/connect/token" \
  -X POST \
  -d "grant_type=client_credentials&client_id=$CLIENT_ID&client_secret=$CLIENT_SECRET" \
  -H "Content-Type: application/x-www-form-urlencoded" \
  -H "Accept: application/json"

# Get list of changes — files sent directly, no pre-upload needed
curl -v "https://api.groupdocs.cloud/v2.0/comparison/changes" \
  -X PUT \
  -H "Authorization: Bearer $JWT_TOKEN" \
  -F "sourceFile=@source.docx" \
  -F "targetFiles=@target.docx"
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

# Get list of changes — files sent directly, no pre-upload needed
curl.exe -v "https://api.groupdocs.cloud/v2.0/comparison/changes" `
  -X PUT `
  -H "Authorization: Bearer $env:JWT_TOKEN" `
  -F "sourceFile=@source.docx" `
  -F "targetFiles=@target.docx"
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

:: Get list of changes — files sent directly, no pre-upload needed
curl -v "https://api.groupdocs.cloud/v2.0/comparison/changes" ^
  -X PUT ^
  -H "Authorization: Bearer %JWT_TOKEN%" ^
  -F "sourceFile=@source.docx" ^
  -F "targetFiles=@target.docx"
```

{{< /tab >}} {{< tab "Response" >}}

```json
[
  {
    "id": 0,
    "comparisonAction": "None",
    "type": "Inserted",
    "text": "lol",
    "targetText": "Latin (i/?læt?n/, /?læt?n/; Latin: lingua lat?na, IPA: [?l????a la?ti?na]) is a classical language, originally spoken inLatium, Italy, which belongs to the Italic branch of the Indo-European languages.[3] The Latin alphabet is derived from the Etruscan and Greek alphabetslol.",
    "authors": [
      "?GroupDocs"
    ],
    "styleChangeInfo": [],
    "pageInfo": {
      "width": 0,
      "height": 0,
      "pageNumber": 0
    },
    "box": {
      "height": 0,
      "width": 0,
      "x": 0,
      "y": 0
    }
  },
...
```
{{< /tab >}} {{< /tabs >}}

## SDK example

Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/groupdocs-comparison-cloud) for a complete list of GroupDocs.Comparison Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs]({{< ref "comparison/getting-started/available-sdks.md" >}}) article to learn how to add an SDK to your project.

{{< tabs "example2">}} {{< tab "C#" >}}

```csharp

// For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-dotnet-samples
string MyClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
string MyClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

var configuration = new Configuration(MyClientId, MyClientSecret);
var apiInstance = new CompareApi(configuration);

var sourceFile = new System.IO.FileInfo("source_files/word/source.docx");
var targetFile = new System.IO.FileInfo("target_files/word/target.docx");

var request = new PutChangesRequest(sourceFile, targetFile);
List<ChangeInfo> changes = apiInstance.PutChanges(request);

Console.WriteLine($"Changes count: {changes.Count}");

```

{{< /tab >}} {{< tab "Java" >}}

```Java

// For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-java-samples
String MyClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
String MyClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

Configuration configuration = new Configuration(MyClientId, MyClientSecret);
CompareApi apiInstance = new CompareApi(configuration);

File sourceFile = new File("source_files/word/source.docx");
File targetFile = new File("target_files/word/target.docx");

PutChangesRequest request = new PutChangesRequest(sourceFile, Arrays.asList(targetFile));
List<ChangeInfo> changes = apiInstance.putChanges(request);

System.out.println("Changes count: " + changes.size());

```

{{< /tab >}} {{< tab "PHP" >}}

```php

// For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-php-samples
use GroupDocs\Comparison\Model\Requests;

$ClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
$ClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

$configuration = new GroupDocs\Comparison\Configuration();
$configuration->setAppSid($ClientId);
$configuration->setAppKey($ClientSecret);

$apiInstance = new GroupDocs\Comparison\CompareApi($configuration);

$sourcePath = "source_files/word/source.docx";
$targetPath = "target_files/word/target.docx";

$request = new Requests\putChangesRequest($sourcePath, [$targetPath]);
$changes = $apiInstance->putChanges($request);

echo "Changes count: " . count($changes);

```

{{< /tab >}} {{< tab "Node.js" >}}

```javascript

// For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-node-samples
global.comparison_cloud = require("groupdocs-comparison-cloud");

global.clientId = "XXXX-XXXX-XXXX-XXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
global.clientSecret = "XXXXXXXXXXXXXXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

global.compareApi = comparison_cloud.CompareApi.fromKeys(clientId, clientSecret);

try {
  let sourceFile = fs.readFileSync("source_files/word/source.docx");
  let targetFile = fs.readFileSync("target_files/word/target.docx");

  let request = new comparison_cloud.PutChangesRequest(
    sourceFile,
    [targetFile],
    "source.docx",
    ["target.docx"]
  );
  let changes = await compareApi.putChanges(request);

  console.log("Changes count: " + changes.length);
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

source_path = "source_files/word/source.docx"
target_path = "target_files/word/target.docx"

request = groupdocs_comparison_cloud.PutChangesRequest(source_path, [target_path])
changes = api_instance.put_changes(request)

print("Changes count: " + str(len(changes)))

```

{{< /tab >}} {{< tab "Ruby" >}}

```ruby

# For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-ruby-samples
require 'groupdocs_comparison_cloud'

$client_id = "XXXX-XXXX-XXXX-XXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
$client_secret = "XXXXXXXXXXXXXXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

api_instance = GroupDocsComparisonCloud::CompareApi.from_keys($client_id, $client_secret)

source_file = File.open("source_files/word/source.docx", "rb")
target_file = File.open("target_files/word/target.docx", "rb")

request = GroupDocsComparisonCloud::PutChangesRequest.new(source_file, [target_file])
changes = api_instance.put_changes(request)

puts("Changes count: " + changes.length.to_s)

source_file.close
target_file.close

```
{{< /tab >}} {{< /tabs >}}
