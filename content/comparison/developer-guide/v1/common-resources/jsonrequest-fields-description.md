---
id: "jsonrequest-fields-description"
url: "comparison/jsonrequest-fields-description"
title: "JsonRequest Fields Description"
productName: "GroupDocs.Comparison Cloud"
weight: 1
description: ""
keywords: ""
---

{{< alert style="info" >}}
Note:  The features listed in this page are working only with GroupDocs.Comparison Cloud V1
{{< /alert >}}










# JsonRequest Fields Description #

 

|**Name**|**Type**|**Description**
|---|---|---
|sourceFile|File Object|Information about source file
|targetFiles|File Object[]|Information about target file(s)
|settings|ComparisonSettings Object|Comparison settings
|changes|ChangeInfo Object[]|Changes for apply or discard. Used only for Changes resource.


 

## File Object fields ##

|**Name**|**Type**|**Description**
|---|---|---
|folder|string|Path to the folder with file
|name|string|File name
|password|string|Password for encrypted documents


 

## ComparisonSettings Object fields ##

|**Name**|**Type**|**Description**
|---|---|---
|generateSummaryPage|bool|Add summary page to result document
|showDeletedContent|bool|Show deleted components in result document
|styleChangeDetection|bool|Detect style changes
|insertedItemsStyle|ItemsStyle Object|Style for inserted components
|deletedItemsStyle|ItemsStyle Object|Style for deleted components
|styleChangedItemsStyle|ItemsStyle Object|Style for style changed components
|wordsSeparatorChars|string[]|Array of separators for dividing text on words
|detailLevel|DetailLevelenum|Set the level for detail of comparison
|useFramesForDelInsElements|bool|Use frames for shapes in Comparison.Words and for rectangles in Comparison.Imaging
|calculateComponentCoordinates|bool|Calculate coordinates for changed components
|markDeletedInsertedContentDeep|bool|Accept inserted/deleted styles for all children of inserted/deleted components
|cloneMetadata|CloneMetadata enum|Set type of metadata to clone
|metaData|MetaData Object|Set user metadata
|PasswordSaveOption|PasswordSaveOption enum|Set type of password save
|Password|string|Set user Password to result document


 

## ItemsStyle Object fields ##

|**Name**|**Type**|**Description**
|---|---|---
|color|string|Color for changed components
|beginSeparatorString|string|Start tag for changed components
|endSeparatorString|string|End tag for changed components
|bold|bool|Bold style for changed components
|italic|bool|Italic style for changed components
|strikeThrough|bool|Strike through style for changed components


 

## ChangeInfo Object fields ##

|**Name**|**Type**|**Description**
|---|---|---
|Id|int|Id of change
|action|Action enum|Action (accept or reject). This field shows comparison what to do with this change (required for request)
|type|TypeChanged enum|Type of change (Inserted, Deleted or StyleChanged) (required for request)
|text|string|Text of changed element
|authors|string[]|Array of authors who made this change (used for multi comparison)
|styleChanges|styleChangeInfo Object[]|Array of style changes


 

## ComparisonChangesCategoryObject fields ##

|**Name**|**Type**|**Description**
|---|---|---
|Category|string|Name of category
|Changes|ChangeInfo[]|Array of ChangeInfo objects


 

## StyleChangeInfo Object fields ##

|**Name**|**Type**|**Description**
|---|---|---
|changedProperty|string|Name of changed style
|oldValue|string|Value of changed style from source document
|newValue|string|Value of changed style from target document


 

## MetaData Object field ##

|**Name**|**Type**|**Description**
|---|---|---
|Author|string|Value of document Author
|LastSaveBy|string|Value of last save by author of document
|Company|string|Value of Company of document


**
**

 

## DetailLevel enum: ##

```html 

Low, Middle, Hight

 ```

 

## Action enum: ##

```html 

Accept, Reject

 ```

 

## TypeChanged enum ##

```html 

Inserted, Deleted, StyleChanged

 ```
