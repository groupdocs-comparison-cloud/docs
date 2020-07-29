---
id: "quick-start"
url: "comparison/quick-start"
title: "Quick Start"
productName: "GroupDocs.Comparison Cloud"
weight: 3
description: ""
keywords: ""
---






# Create an account #

Creating an account is very simple. Go to [https://dashboard.groupdocs.cloud](https://dashboard.groupdocs.cloud/#/) to create a free account. 

# Create an API client app #

Before you can make any requests to GroupDocs Cloud API you need to get APP SID and APP key (secret key). This will be used to invoke GroupDocs Cloud API. 

You can get it from default Application or create new Application from [My Apps tab of GroupDocs for Cloud Dashboard]({{< ref "total/getting-started/ui-topics/create-new-app-and-get-app-key-and-sid.md" >}}).

# Install the SDK of your choice #

GroupDocs for Cloud SDK is written in different languages, all you need to get started is adding our [SDK]({{< ref "comparison/getting-started/available-sdks.md" >}}) to your existing project.

# Make an API request from the SDK of your choice #

Use the **App SID** and **App key (secret key)** from the API app client you created in step one and replace in the corresponding code. Below is an example demonstrating how to compare and get document changes using GroupDocs.Comparison Cloud.

{{< alert style="info" >}}The GitHub repository for [GroupDocs.Comparison Cloud](https://github.com/groupdocs-comparison-cloud) has a complete set of examples, demonstrating our API capabilities.{{< /alert >}}



 C#



 
{{< gist groupdocscloud 33ad9afbf76ac035c8552d2efe0ec895 Comparison_CSharp_Get_Changes.cs >}}







 PHP



 
{{< gist groupdocscloud fb9d531a4ea5f0755dfd0e079b7801b5 Comparison_Php_Get_Changes.php >}}







 Java




{{< gist groupdocscloud dde5dbd092bef3a3ac74848342ee4f64 Comparison_Java_Get_Changes.java >}}







 Ruby




{{< gist groupdocscloud 4e15a0a5e68b0d2755592a552488d1ec Comparison_Ruby_get_changes.rb >}}







