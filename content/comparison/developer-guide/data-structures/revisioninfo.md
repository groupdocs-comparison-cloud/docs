---
id: "revisioninfo"
url: "comparison/revisioninfo"
title: "RevisionInfo"
productName: "GroupDocs.Comparison Cloud"
weight: 7
description: ""
keywords: ""
---

RevisionInfo data structure returned by "POST" /comparison/revisions API as output result. Also used by "PUT" /comparison/revisions API as input.

RevisionInfo example:

```javascript

{
  "id": 0,
  "action": "None",
  "text": "\rsssssssss",
  "author": "GroupDpcs",
  "type": "Insertion"
}

```

|Name|Description
|---|---
|id|Id of revision (index)
|action|Action (Accept, Reject, None). This field shows what to do with this revision.
|type|Type of revision (Insertion, Deletion,, etc.)
|text|Revision text
|author|Revision author
