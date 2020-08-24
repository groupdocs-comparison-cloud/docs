---
id: "get-changes-categories"
url: "comparison/get-changes-categories"
title: "Get Changes Categories"
productName: "GroupDocs.Comparison Cloud"
weight: 1
description: ""
keywords: ""
---

{{< alert style="info" >}}
Note:  The features listed in this page are working only with GroupDocs.Comparison Cloud V1
{{< /alert >}}

You can compare documents and get list of changes categories by providing the [JsonRequest Object]({{< ref "comparison/developer-guide/v1/common-resources/jsonrequest-fields-description.md" >}}) data in request body.

## Resource ##

The following GroupDocs.Comparison Cloud REST API resource has been used to [get compared documents changes categories](https://apireference.groupdocs.cloud/comparison/#!/Changes/PostCategoriesChanges).

### Enumeration of categories of changes ###

```bash

enum ComparisonCategoriesType
{
  ByTypeChanged, * "take categories by TypeChanged"
  ByNodeType, * "take categories by nodes Types"
  ContainsNumbers, * "take categories with changes which contains numbers"
  OnlyNumbers * "take categories with changes which contains only numbers"
}

```

## cURL REST Example ##

 Request

```html
curl -v "https:~/~/api.groupdocs.cloud/v1.0/comparison/compareDocuments/changes/categories?categoriesType#ByTypeChanged&appsid#XXXX&signature#XXX-XX"

-H "content-type: application/json"

 -X POST -d "{'sourceFile':{'folder':'comparisons','name':'source.docx','password':''},'targetFiles':[{'folder':'comparisons','name':'target.docx','password':''}]}"
```

 Response

```html
[
 {
 "category": "Deleted",
 "changes": [
 {
 "id": 0,
 "type": "Deleted",
 "text": "digital ",
 "authors": [
 "Rizwan"
 ],
 "action": "None",
 "styleChanges": []
 },
 {
 "id": 1,
 "type": "Deleted",
 "text": "Executive ",
 "authors": [
 "Rizwan"
 ],
 "action": "None",
 "styleChanges": []
 },
 {
 "id": 3,
 "type": "Deleted",
 "text": "",
 "authors": [
 "Rizwan"
 ],
 "action": "None",
 "styleChanges": []
 }
 ]
 },
 {
 "category": "Inserted",
 "changes": [
 {
 "id": 2,
 "type": "Inserted",
 "text": "",
 "authors": [
 "Rizwan"
 ],
 "action": "None",
 "styleChanges": []
 }
 ]
 }
]
```

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-comparison-cloud).

### Get Changes Categories from Compared Documents ###

C#

 
{{< gist groupdocscloud 33ad9afbf76ac035c8552d2efe0ec895 Comparison_CSharp_Get_Changes_Categories.cs >}}

PHP

 
{{< gist groupdocscloud fb9d531a4ea5f0755dfd0e079b7801b5 Comparison_Php_Get_Changes_Categories.php >}}

Java

{{< gist groupdocscloud dde5dbd092bef3a3ac74848342ee4f64 Comparison_Java_Get_Changes_Categories.java >}}

Ruby

{{< gist groupdocscloud 4e15a0a5e68b0d2755592a552488d1ec Comparison_Ruby_get_changes_categories.rb >}}
