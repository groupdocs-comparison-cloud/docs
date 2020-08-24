---
id: "get-stream-of-result-document-changes"
url: "comparison/get-stream-of-result-document-changes"
title: "Get Stream of Result Document - Changes"
productName: "GroupDocs.Comparison Cloud"
weight: 1
description: ""
keywords: ""
---

{{< alert style="info" >}}
Note:  The features listed in this page are working only with GroupDocs.Comparison Cloud V1
{{< /alert >}}

You can compare documents,  update the changes (accept/reject), saves the result document to streams as a set of images and returns the array of streams of images by providing the [JsonRequest Object]({{< ref "comparison/developer-guide/v1/common-resources/jsonrequest-fields-description.md" >}}) data in the request body.

## Resource ##

The following GroupDocs.Comparison Cloud REST API resource has been used to [get stream of result document (changes)](https://apireference.groupdocs.cloud/comparison/#!/Changes/PutChangesDocumentStream).

## cURL REST Example ##

 Request

```html
curl -v  "https://api.groupdocs.cloud/v1.0/comparison/compareDocuments/changes/stream?appsid#XXXX&#x26;signature#XXX-XX"
-H "Content-Type: application/json"
-X POST -d "{'sourceFile':{'folder':'comparisons','name':'source.docx','password':''},'targetFiles':[{'folder':'comparisons','name':'target.docx','password':''}],'settings':'generateSummaryPage':true,'showDeletedContent':true,'styleChangeDetection':true,'insertedItemsStyle':{'color':'Blue','beginSeparatorString':'','endSeparatorString':'','bold':false,'italic':false,'strikeThrough':false},'deletedItemsStyle':{'color':'Red','beginSeparatorString':'','endSeparatorString':'','bold':false,'italic':false,'strikeThrough':false},'styleChangedItemsStyle':{'color':'Green','beginSeparatorString':'','endSeparatorString':'','bold':false,'italic':false,'strikeThrough':false},'wordsSeparatorChars':[],'detailLevel':'Low','useFramesForDelInsElements':false,'calculateComponentCoordinates':false,'markDeletedInsertedContentDeep':false},'changes':[{'id':0,'action':'Accept'},{'id':1,'action':'Reject'}]}"
```

 Response

```html
Array of streams of images of document.
```

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-comparison-cloud).

### Get Stream of Result Document (Changes) ###

C#

{{< gist groupdocscloud 33ad9afbf76ac035c8552d2efe0ec895 Comparison_CSharp_Update_Changes_And_Get_Document_Stream.cs >}}

PHP

{{< gist groupdocscloud fb9d531a4ea5f0755dfd0e079b7801b5 Comparison_Php_Update_Changes_And_Get_Document_Stream.php >}}

Java

{{< gist groupdocscloud dde5dbd092bef3a3ac74848342ee4f64 Comparison_Java_Get_Changes_Document_Stream.java >}}

Ruby

{{< gist groupdocscloud 4e15a0a5e68b0d2755592a552488d1ec Comparison_Ruby_get_changes_document_stream.rb >}}
