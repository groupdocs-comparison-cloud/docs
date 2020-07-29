---
id: "updatesoptions"
url: "comparison/updatesoptions"
title: "UpdatesOptions"
productName: "GroupDocs.Comparison Cloud"
weight: 7
description: ""
keywords: ""
---

## UpdatesOptions ##

UpdatesOptions data structure defines comparison options

UpdatesOptions example:


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
  "OutputPath": "string",
  "Changes": [
    {
      "Id": 0,
      "Text": "string",
      "TargetText": "string",
      "Authors": [
        "string"
      ],
      "StyleChangeInfo": [
        {
          "ChangedProperty": "string",
          "OldValue": "string",
          "NewValue": "string"
        }
      ],
      "PageInfo": {
        "Width": 0,
        "Height": 0,
        "PageNumber": 0
      },
      "Box": {
        "Height": 0,
        "Width": 0,
        "X": 0,
        "Y": 0
      }
    }
  ]
}

 ```



 

|Name|Description
|---|---
|SourceFile|[Information ]({{< ref "comparison/developer-guide/data-structures/fileinfo.md" >}})about source file
|TargetFiles|An array of [Information ]({{< ref "comparison/developer-guide/data-structures/fileinfo.md" >}})about target file(s)
|Settings|Comparison [settings]({{< ref "comparison/developer-guide/data-structures/settings.md" >}})
|ChangeType|Changes type. Used only for Changes resource(/comparison/changes) (None, Modified, Inserted, Deleted, Added, NotModified, StyleChanged, Resized, Moved, MovedAndResized, ShiftedAndResized)
|OutputPath|Path to the resultant document (if not specified the document will not be saved)
|Changes|Changes to apply or reject. Used only for updates resource (/comparison/updates)

 


