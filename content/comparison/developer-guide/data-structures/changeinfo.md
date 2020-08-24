---
id: "changeinfo"
url: "comparison/changeinfo"
title: "ChangeInfo"
productName: "GroupDocs.Comparison Cloud"
weight: 7
description: ""
keywords: ""
---

## ChangeInfo ##

ChangeInfo data structure returned by /comparison/changes API as output result. Also used by /comparison/updates API as input.

ChangeInfo example:

```javascript

{
    "id": 0,
    "comparisonAction": "None",
    "type": "Inserted",
    "text": "lol",
    "targetText": "Latin (i/?læt?n/, /?læt?n/; Latin: lingua lat?na, IPA: [?l????a la?ti?na]) is a classical language, originally spoken inLatium, Italy, which belongs to the Italic branch of the Indo-European languages.[3] The Latin alphabet is derived from the Etruscan and Greek alphabetslol.",
    "authors": [
      "?GroupDocs"
    ],
    "styleChangeInfo": [],
    "pageInfo": {
      "width": 0,
      "height": 0,
      "pageNumber": 0
    },
    "box": {
      "height": 0,
      "width": 0,
      "x": 0,
      "y": 0
    }
  }

```



|Name|Description
|---|---
|Id|Id of change
|ComparisonAction|Action (accept or reject). This field shows comparison what to do with this change.  Used with 'updates' API method.
|Type|Type of change (Inserted, Deleted, StyleChanged, etc.)
|Text|Source text
|Targettext|Target text
|Authors|Array of authors who made this change (used for multi comparison)
|PageInfo|[Description ]({{< ref "comparison/developer-guide/data-structures/pageinfo.md" >}})of page on which change is found
|Box|[Description ]({{< ref "comparison/developer-guide/data-structures/rectangle.md" >}})of the place where change is found
|StyleChangeInfo|Array of style changes
|ChangedProperty|Name of changed style
|OldValue|Value of changed style from source document
|NewValue|Value of changed style from target document
