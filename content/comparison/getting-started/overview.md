---
id: "overview"
url: "comparison/overview"
title: "Overview"
productName: "GroupDocs.Comparison Cloud"
weight: 1
description: ""
keywords: ""
toc: True
---

GroupDocs.Comparison Cloud is a REST API that provides an ability to detect differences between source and target files for changes at paragraphs, words and characters levels. Can identify styling and formatting changes - like bold, italic, underlines, strike-troughs, font types, etc.
Every particular difference between compared document can be applied or rejected and the exported to a final document.
GroupDocs.Comparison Cloud allows to obtain basic information about source document - file type, size, pages count etc.
Once comparison process is complete, you can save a differences summary report which lists all changes found between compared documents.

## API Endpoint Groups Overview

|Endpoint Group|Description
|---|---
|Info|Contains endpoints for obtaining list of formats supported by GroupDocs.Comparison Cloud, and getting basic information about document and its pages
|Compare|Contains main product endpoint for document comparison
|File|Contains endpoints for upload, download, copy, move, delete files in the storage
|Folder|Contains endpoints for create, copy, move, delete folders in the storage
|Storage|Contains endpoints for obtaining storage information and file information

## Security and Authentication

The GroupDocs.Comparison Cloud API is secured and requires authentication. Developers can [generate]({{< ref "total/ui-topics/creating-and-managing-application.md" >}}) a new application with an unique Client Id and Client Secret combination after [registering]({{< ref "total/ui-topics/creating-and-managing-account.md" >}}) to our [dashboard](https://dashboard.groupdocs.cloud). Authenticated requests require a Bearer authorization header with a JWT Token obtained by using the previously specified Cliend Id + Client Secret credentials. You can check complete details about authenticating your calls to our API [here]({{< ref "total/overview-rest-api/authenticating-api-requests.md" >}}).

## SDK example

Checkout our GitHub [repository](https://github.com/groupdocs-comparison-cloud) for a complete list of GroupDocs.Comparison Cloud SDKs along with working examples, to get you started in no time.

At the moment following SDKs are provided:

* .NET ([Sources](https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-dotnet), [NuGet Package](https://www.nuget.org/packages/GroupDocs.Comparison-Cloud), [samples](https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-dotnet-samples))
* Java ([Sources](https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-java), [Jar](https://repository.groupdocs.cloud/webapp/#/artifacts/browse/tree/General/repo/com/groupdocs/groupdocs-comparison-cloud), [samples](https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-java-samples))
* PHP ([Sources](https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-php), [samples](https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-php-samples))
* Node.js ([Sources](https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-node), [samples](https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-node-samples))
* Python ([Sources](https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-python), [samples](https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-python-samples))
* Ruby ([Sources](https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-ruby), [samples](https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-ruby-samples))

## API Explorer

The easiest way to try out our API right away in your browser! With the [GroupDocs Cloud Web API explorer](https://apireference.groupdocs.cloud/comparison/). This is a collection of Swagger documentation for the GroupDocs for Cloud APIs. You can get information about all the resources in the API. It also provides testing and interactivity to our API endpoint documentation.
