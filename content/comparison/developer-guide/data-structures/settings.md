---
id: "settings"
url: "comparison/settings"
title: "Settings"
productName: "GroupDocs.Comparison Cloud"
weight: 7
description: ""
keywords: ""
---

Settings  data structure defines comparison process additional settings

Settings example:

```javascript

{
    "GenerateSummaryPage": true,
    "ShowDeletedContent": true,
    "ShowInsertedContent": true,
    "StyleChangeDetection": true,
    "InsertedItemsStyle": {
      "FontColor": "string",
      "HighlightColor": "string",
      "BeginSeparatorString": "string",
      "EndSeparatorString": "string",
      "Bold": true,
      "Italic": true,
      "StrikeThrough": true,
      "Underline": true
    },
    "DeletedItemsStyle": {
      "FontColor": "string",
      "HighlightColor": "string",
      "BeginSeparatorString": "string",
      "EndSeparatorString": "string",
      "Bold": true,
      "Italic": true,
      "StrikeThrough": true,
      "Underline": true
    },
    "ChangedItemsStyle": {
      "FontColor": "string",
      "HighlightColor": "string",
      "BeginSeparatorString": "string",
      "EndSeparatorString": "string",
      "Bold": true,
      "Italic": true,
      "StrikeThrough": true,
      "Underline": true
    },
    "WordsSeparatorChars": [
      "string"
    ],
    "UseFramesForDelInsElements": true,
    "CalculateComponentCoordinates": true,
    "MarkChangedContent": true,
    "MarkNestedContent": true,
    "MetaData": {
      "Author": "string",
      "LastSaveBy": "string",
      "Company": "string"
    },
    "Password": "string",
    "DiagramMasterSetting": {
      "MasterPath": "string",
      "UseSourceMaster": true
    },
    "OriginalSize": {
      "Width": 0,
      "Height": 0
    },
    "HeaderFootersComparison": true,
    "SensitivityOfComparison": 0
}

```

|Name|Description
|---|---
|GenerateSummaryPage|Indicates whether to add summary page to resultant document or not
|ShowDeletedContent|Indicates whether to show deleted components in resultant document or not
|ShowInsertedContent|Indicates whether to show inserted components in resultant document or not
|StyleChangeDetection|Indicates whether to detect style changes or not
|InsertedItemsStyle|[Style ]({{< ref "comparison/developer-guide/data-structures/itemsstyle.md" >}})for inserted components
|DeletedItemsStyle|[Style ]({{< ref "comparison/developer-guide/data-structures/itemsstyle.md" >}})for deleted components
|ChangedItemsStyle|[Style]({{< ref "comparison/developer-guide/data-structures/itemsstyle.md" >}}) for components with changed style
|WordsSeparatorChars|An array of delimiters to split text into words
|DetailsLevel|The comparison details level  (Low, Middle, High)
|UseFramesForDelInsElements|Indicates whether to use frames for shapes in Word Processing and for rectangles in Image documents
|CalculateComponentCoordinates|Indicates whether to calculate coordinates for changed components
|MarkChangedContent|Indicates whether to use frames for shapes in Word Processing and for rectangles in Image documents
|MarkNestedContent|Gets or sets a value indicating whether to mark the children of the deleted or inserted element as deleted or inserted
|CloneMetadata|Type of metadata to clone (Default, Source, Target, FileAuthor)
|MetaData|User [metadata]({{< ref "comparison/developer-guide/data-structures/metadata.md" >}})
|PasswordSaveOption|Type of password saving (None, Source, Target, User)
|Password|User password to resultant document
|DiagramMasterSetting|[Master ]({{< ref "comparison/developer-guide/data-structures/diagrammastersetting.md" >}})for Diagram document
|OriginalSize|Original document [size ]({{< ref "comparison/developer-guide/data-structures/size.md" >}})when picture is compared with other different formats
|HeaderFootersComparison|Control to turn on comparison of header/footer contents
|PaperSize|The result document paper size (Default, A0, A1, ... A8)
|SensitivityOfComparison|A sensitivity of comparison (1..100). Default is 75
