---
id: "quick-start"
url: "comparison/quick-start"
title: "Quick Start"
productName: "GroupDocs.Comparison Cloud"
weight: 3
description: ""
keywords: ""
---
## Create an account ##

Creating an account is very simple. Go to [Dashboard](https://dashboard.groupdocs.cloud) to create a free account.\
We're using Single Sign On across our websites, therefore, if you already have an account with our services, you can use it to also acccess the [Dashboard](https://dashboard.groupdocs.cloud).

## Create an API client app ##

Before you can make any requests to GroupDocs Cloud API you need to get a **Client Id** and a **Client Secret**.
This will will be used to invoke GroupDocs Cloud API. You can get it by creating a new [Application](https://dashboard.groupdocs.cloud/applications).

## Install the SDK of your choice ##

GroupDocs Cloud SDK is written in different languages, all you need to get started is adding our [SDK]({{< ref "comparison/getting-started/available-sdks.md" >}}) to your existing project.

## Make an API request from the SDK of your choice ##

Use the **Client Id** and the **Client Secret** from the API app client you created in step one and replace in the corresponding code. Below is an example demonstrating using Formats API to get all supported file formats in GroupDocs.Comparison Cloud.

{{< alert style="info" >}}The GitHub repository for [GroupDocs.Comparison Cloud](https://github.com/groupdocs-comparison-cloud) has a complete set of examples, demonstrating our API capabilities.{{< /alert >}}

{{< tabs tabTotal="6" tabID="10" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Node.js" tabName5="Python" tabName6="Ruby" >}} {{< tab tabNum="1" >}}

{{< gist groupdocscloud 622c78dd86e4c5ade7e870295b6db376 Comparison_CSharp_Get_Supported_Formats.cs >}}

{{< /tab >}} {{< tab tabNum="2" >}}

{{< gist groupdocscloud fcf2013d068abf714662f99cba3c0d47 Comparison_Java_Get_Supported_Formats.java >}}

{{< /tab >}} {{< tab tabNum="3" >}}

{{< gist groupdocscloud 24ad96946345493cb230d7124f22c176 Comparison_Php_Get_Supported_Formats.php >}}

{{< /tab >}} {{< tab tabNum="6" >}}

{{< gist groupdocscloud f830f503cb44c7aa38a757cb86b34f5d Comparison_Ruby_Get_Supported_Formats.rb >}}

{{< /tab >}} {{< tab tabNum="4" >}}

```javascript

// For complete examples and data files, please go to https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-node-samples
global.comparison_cloud = require("groupdocs-comparison-cloud");

global.clientId = "XXXX-XXXX-XXXX-XXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
global.clientSecret = "XXXXXXXXXXXXXXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

global.infoApi = comparison_cloud.InfoApi.fromKeys(clientId, clientSecret);

try {
 let response = await infoApi.getSupportedFileFormats();
 console.log("Formats count: " + response.formats.length); 
} catch (error) {
 console.log(error.message);
}

```

{{< /tab >}} {{< tab tabNum="5" >}}

{{< gist groupdocscloud 5b471172e33a251d70b08127085d200e Comparison_Python_Get_Supported_Formats.py >}}

{{< /tab >}} {{< /tabs >}}
