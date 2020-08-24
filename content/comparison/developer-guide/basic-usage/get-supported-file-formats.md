---
id: "get-supported-file-formats"
url: "comparison/get-supported-file-formats"
title: "Get Supported File Formats"
productName: "GroupDocs.Comparison Cloud"
weight: 9
description: ""
keywords: ""
---

GroupDocs.Comparison Cloud REST APIs support document compare tools to compare source and destination files of supported formats to get high-quality output in quickly and reliably. To get a list of supported formats, You can use the below API.

## Resource ##

The following GroupDocs.Comparison Cloud REST API resource has been used in the [Supported File Formats](https://apireference.groupdocs.cloud/comparison/#/Info/GetSupportedFileFormats) example.

## cURL Example ##

 Request

```html
curl -X GET "https://api.groupdocs.cloud/v2.0/comparison/formats" -H  "accept: application/json" -H  "authorization: Bearer [Access Token]"

```

 Response

```html
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

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-comparison-cloud).

### Get List of Supported File Formats ###

C#

{{< gist groupdocscloud 622c78dd86e4c5ade7e870295b6db376 Comparison_CSharp_Get_Supported_Formats.cs >}}

Java

{{< gist groupdocscloud fcf2013d068abf714662f99cba3c0d47 Comparison_Java_Get_Supported_Formats.java >}}

PHP

{{< gist groupdocscloud 24ad96946345493cb230d7124f22c176 Comparison_Php_Get_Supported_Formats.php >}}

Ruby

{{< gist groupdocscloud f830f503cb44c7aa38a757cb86b34f5d Comparison_Ruby_Get_Supported_Formats.rb >}}

 Node.js

{{< gist groupdocscloud 7999207c55ecfba6c2a125f5b77ca0d8 Comparison_Node_Get_Supported_Formats.js >}}

 Python

{{< gist groupdocscloud 5b471172e33a251d70b08127085d200e Comparison_Python_Get_Supported_Formats.py >}}
