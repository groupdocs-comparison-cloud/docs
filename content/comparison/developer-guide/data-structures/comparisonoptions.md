---
id: "comparisonoptions"
url: "comparison/comparisonoptions"
title: "ComparisonOptions"
productName: "GroupDocs.Comparison Cloud"
weight: 7
description: ""
keywords: ""
---

## ComparisonOptions ##

ComparisonOptions data structure defines comparison options

ComparisonOptions example:

```javascript

{
  "SourceFile": {
    "FilePath": "string",
    "VersionId": "string",
    "StorageName": "string",
    "Password": "string"
  },
  "TargetFiles": [
    {
      "FilePath": "string",
      "VersionId": "string",
      "StorageName": "string",
      "Password": "string"
    }
  ],
  "Settings": {
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
  },
  "OutputPath": "string"
}

```



|Name|Description
|---|---
|SourceFile|[Information ]({{< ref "comparison/developer-guide/data-structures/fileinfo.md" >}})about source file
|TargetFiles|An array of [Information ]({{< ref "comparison/developer-guide/data-structures/fileinfo.md" >}})about target file(s)
|Settings|Comparison [settings]({{< ref "comparison/developer-guide/data-structures/settings.md" >}})
|ChangeType|Changes type. Used only for Changes resource(/comparison/changes) (None, Modified, Inserted, Deleted, Added, NotModified, StyleChanged, Resized, Moved, MovedAndResized, ShiftedAndResized)
|OutputPath|Path to the resultant document (if not specified the document will not be saved)
