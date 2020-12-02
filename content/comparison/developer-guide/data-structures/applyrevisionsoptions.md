---
id: "applyrevisionsoptions"
url: "comparison/applyrevisionsoptions"
title: "ApplyRevisionsOptions"
productName: "GroupDocs.Comparison Cloud"
weight: 7
description: ""
keywords: ""
---

ApplyRevisionsOptions data structure defines options for applying revisions using "PUT" /comparison/revisions API method

ApplyRevisionsOptions example:

```javascript

{
  'SourceFile': {
    'FilePath': 'source_files/word/source_with_revs.docx'
  },
  'Revisions': [
    {
      'Id': 0,
      'action': 'Accept'
    },
    {
      'Id': 1,
      'action': 'Accept'
    },
  ],
  'OutputPath': 'output/result.docx'
}

```

|Name|Description
|---|---
|SourceFile|[Information ]({{< ref "comparison/developer-guide/data-structures/fileinfo.md" >}})about source file
|Revisions|Array of revision [settings]({{< ref "comparison/developer-guide/data-structures/revisioninfo.md" >}})
|OutputPath|Path to the output document
