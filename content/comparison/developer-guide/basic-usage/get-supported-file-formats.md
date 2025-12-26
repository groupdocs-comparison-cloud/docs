---
id: "get-supported-file-formats"
url: "comparison/get-supported-file-formats"
title: "Get Supported File Formats"
productName: "GroupDocs.Comparison Cloud"
weight: 9
description: ""
keywords: ""
toc: True
---

GroupDocs.Comparison Cloud REST APIs support document compare tools to compare source and destination files of supported formats to get high-quality output in quickly and reliably. To get a list of supported formats, You can use the below API.

## Resource

The following GroupDocs.Comparison Cloud REST API resource has been used in the [Supported File Formats](https://apireference.groupdocs.cloud/comparison/#/Info/GetSupportedFileFormats) example.

## cURL example

{{< tabs "example1">}} {{< tab "Linux/MacOS/Bash" >}}

```bash
curl -X GET "https://api.groupdocs.cloud/v2.0/comparison/formats" \
  -H "accept: application/json" \
  -H "authorization: Bearer $JWT_TOKEN"
```

{{< /tab >}}

{{< tab "Windows PowerShell" >}}

```powershell
curl.exe -X GET "https://api.groupdocs.cloud/v2.0/comparison/formats" `
  -H "accept: application/json" `
  -H "authorization: Bearer $env:JWT_TOKEN"
```

{{< /tab >}}

{{< tab "Windows CMD" >}}

```cmd
curl -X GET "https://api.groupdocs.cloud/v2.0/comparison/formats" ^
  -H "accept: application/json" ^
  -H "authorization: Bearer %JWT_TOKEN%"
```

{{< /tab >}} {{< tab "Response" >}}

```json
{
  "formats": [
    {
      "extension": ".pdf",
      "fileFormat": "Portable Document Format"
    },
    {
      "extension": ".doc",
      "fileFormat": "Microsoft Word"
    },
    {
      "extension": ".docx",
      "fileFormat": "Microsoft Word"
    },
    {
      "extension": ".mobi",
      "fileFormat": "Mobipocket"
    },
    {
      "extension": ".xls",
      "fileFormat": "Microsoft Excel"
    },
    {
      "extension": ".xlsx",
      "fileFormat": "Microsoft Excel"
    },
    {
      "extension": ".ppt",
      "fileFormat": "Microsoft PowerPoint"
    },
    {
      "extension": ".pptx",
      "fileFormat": "Microsoft PowerPoint"
    },
    {
      "extension": ".vsd",
      "fileFormat": "Microsoft Visio"
    },
    {
      "extension": ".vsdx",
      "fileFormat": "Microsoft Visio"
    },
    {
      "extension": ".msg",
      "fileFormat": "Microsoft Outlook Mail Message"
    },
    {
      "extension": ".eml",
      "fileFormat": "Microsoft Outlook Mail Message"
    },
    {
      "extension": ".one",
      "fileFormat": "Microsoft OneNote"
    },
    {
      "extension": ".emlx",
      "fileFormat": "Apple Mail"
    },
    {
      "extension": ".ods",
      "fileFormat": "OpenDocument Formats"
    },
    {
      "extension": ".odp",
      "fileFormat": "OpenDocument Formats"
    },
    {
      "extension": ".otp",
      "fileFormat": "OpenDocument Formats"
    },
    {
      "extension": ".ots",
      "fileFormat": "OpenDocument Formats"
    },
    {
      "extension": ".odg",
      "fileFormat": "OpenDocument Formats"
    },
    {
      "extension": ".txt",
      "fileFormat": "Plain Text File"
    },
    {
      "extension": ".html",
      "fileFormat": "HyperText Markup Language"
    },
    {
      "extension": ".mhtml",
      "fileFormat": "HyperText Markup Language"
    },
    {
      "extension": ".dxf",
      "fileFormat": "CAD Drawing File Format"
    },
    {
      "extension": ".dwg",
      "fileFormat": "CAD Drawing File Format"
    },
    {
      "extension": ".bmp",
      "fileFormat": "Image files"
    },
    {
      "extension": ".jpg",
      "fileFormat": "Image files"
    },
    {
      "extension": ".jpeg",
      "fileFormat": "Image files"
    },
    {
      "extension": ".png",
      "fileFormat": "Image files"
    },
    {
      "extension": ".tiff",
      "fileFormat": "Image files"
    },
    {
      "extension": ".djvu",
      "fileFormat": "Image files"
    },
    {
      "extension": ".dcm",
      "fileFormat": "Digital Imaging and Communications in Medicine"
    },
    {
      "extension": ".epub",
      "fileFormat": "Electronic publication"
    }
  ]
}
```

{{< /tab >}} {{< /tabs >}}

## SDK example

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-comparison-cloud).

### Get List of Supported File Formats

{{< tabs "example2">}} {{< tab "C#" >}}

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
{{< /tab >}} {{< tab "Apex" >}}

```javascript
// Create configuration and API instances
Configuration config = new Configuration('YOUR_API_KEY', 'YOUR_API_SECRET'); // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
InfoApi infoApi = new InfoApi(config);

try {
    // Get supported file formats
    FormatsResult response = infoApi.getSupportedFileFormats();

    // Log supported file formats and their extensions
    for (Format format : response.Formats) {
        System.debug('File Format: ' + format.FileFormat + ', Extensions: ' + String.join(format.Extension, ', '));
    }
} catch (Exception e) {
    System.debug('Error occurred while fetching supported file formats: ' + e.getMessage());
}

```
{{< /tab >}} {{< /tabs >}}
