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

Use the **Client Id** and the **Client Secret** from the API app client you created in step one and replace in the corresponding code. Below is an example demonstrating using Formats API to get all supported file formats in GroupDocs.Comparison Cloud.

{{< alert style="info" >}}The GitHub repository for [GroupDocs.Comparison Cloud](https://github.com/groupdocs-comparison-cloud) has a complete set of examples, demonstrating our API capabilities.{{< /alert >}}

{{< tabs "example1">}} {{< tab "C#" >}}

```csharp
using System;
using GroupDocs.Comparison.Cloud.Sdk.Api;
using GroupDocs.Comparison.Cloud.Sdk.Client;

namespace GroupDocs.Comparison.Cloud.Examples.CSharp
{
	// Get All Supported Formats
	class Get_All_Supported_Formats
	{
		public static void Run()
		{
			var configuration = new Configuration(Common.MyAppSid, Common.MyAppKey);

			var apiInstance = new InfoApi(configuration);

			try
			{
				// Get supported file formats
				var response = apiInstance.GetSupportedFileFormats();

				foreach (var entry in response.Formats)
				{
					Console.WriteLine(string.Format("{0}: {1}", entry.FileFormat, string.Join(",", entry.Extension)));
				}
			}
			catch (Exception e)
			{
				Console.WriteLine("Exception while calling Comparison InfoApi: " + e.Message);
			}
		}
	}
}
```

{{< /tab >}} {{< tab "Java" >}}

```java
package examples.Supported_File_Formats;

import com.groupdocs.cloud.comparison.client.*;
import com.groupdocs.cloud.comparison.model.*;
import java.util.List;
import com.groupdocs.cloud.comparison.client.Configuration;
import com.groupdocs.cloud.comparison.api.*;
import examples.Utils;

public class Comparison_Java_Get_Supported_Formats {

	public static void main(String[] args) {

		Configuration configuration = new Configuration(Utils.AppSID, Utils.AppKey);
		InfoApi apiInstance = new InfoApi(configuration);

        try {
            FormatsResult response = apiInstance.getSupportedFileFormats();
            for (Format format : response.getFormats()) {
                System.out.println(format.getFileFormat());
            }
        } catch (ApiException e) {
            System.err.println("Exception while calling InfoApi:");
            e.printStackTrace();
        }
	}
}

```

{{< /tab >}} {{< tab "PHP" >}}

```php
<?php

include(dirname(__DIR__) . '\CommonUtils.php');

try {
    $apiInstance = CommonUtils::GetInfoApiInstance();

    $response = $apiInstance->getSupportedFileFormats();

    echo '<b>Supported file formats<br /></b>';
	foreach($response->getFormats() as $key => $format) {
	  echo $format->getFileFormat(), "(", $format->getExtension(), ")<br />";
	}
} catch (Exception $e) {
    echo "Something went wrong: ", $e->getMessage(), "\n";
}
```

{{< /tab >}} {{< tab "Ruby" >}}

```ruby
# Load the gem
require 'groupdocs_comparison_cloud'
require 'common_utilities/Utils.rb'

class File_Formats
  def self.Comparison_Ruby_Get_Supported_Formats()

    # Getting instance of the API
    api = Common_Utilities.Get_InfoApi_Instance()

    # Retrieve supported file-formats
    $response = api.get_supported_file_formats()

    # Print out supported file-formats
    puts("Supported file-formats:")
    $response.formats.each do |format|
      puts("#{format.file_format} (#{format.extension})")
    end
  end
end
```

{{< /tab >}} {{< tab "Node.js" >}}

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

{{< /tab >}} {{< tab "Python" >}}

```python
# Import modules
import groupdocs_comparison_cloud

from Common_Utilities.Utils import Common_Utilities;


class Comparison_Python_Get_Supported_Formats:
    
    @classmethod
    def Run(self):
        # Create instance of the API
        api = Common_Utilities.Get_InfoApi_Instance()
        
        try:
            # Retrieve supported file-formats
            response = api.get_supported_file_formats()
    
            # Print out supported file-formats
            print("Supported file-formats:")
            for fileformat in response.formats:
                print('{0} ({1})'.format(fileformat.file_format, fileformat.extension))
        except groupdocs_comparison_cloud.ApiException as e:
            print("Exception when calling get_supported_comparison_types: {0}".format(e.message))
```

{{< /tab >}} {{< /tabs >}}
