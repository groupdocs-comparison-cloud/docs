---
id: "working-with-storage-api"
url: "comparison/working-with-storage-api"
title: "Working with Storage API"
productName: "GroupDocs.Comparison Cloud"
description: ""
keywords: ""
weight: 4
toc: True
---

## Storage existance API

This API intended for checking existence of cloud storage with given name from [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud).

### API Explorer

[GroupDocs.Comparison Cloud API Reference](https://apireference.groupdocs.cloud/comparison/#/) lets you to try out [Storage existence API](https://apireference.groupdocs.cloud/comparison/#/Storage/StorageExists) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs exposes.

### Request parameters

|Parameter|Description
|---|---
|**storageName**|Storage name

### cURL example

{{< tabs "example1">}} {{< tab "Linux/MacOS/Bash" >}}
```bash
curl -X GET "https://api.groupdocs.cloud/v2.0/comparison/storage/MyStorage/exist" \
    -H "accept: application/json" \
    -H "authorization: Bearer $JWT_TOKEN"
```
{{< /tab >}}

{{< tab "Windows PowerShell" >}}
```powershell
curl.exe -X GET `
    "https://api.groupdocs.cloud/v2.0/comparison/storage/MyStorage/exist" `
    -H "accept: application/json" `
    -H "authorization: Bearer $env:JWT_TOKEN"
```
{{< /tab >}}

{{< tab "Windows CMD" >}}
```cmd
curl -X GET ^
    "https://api.groupdocs.cloud/v2.0/comparison/storage/MyStorage/exist" ^
    -H "accept: application/json" ^
    -H "authorization: Bearer %JWT_TOKEN%"
```
{{< /tab >}} {{< tab "Response" >}}

```json
{
  "exists": true
}
```
{{< /tab >}} {{< /tabs >}}

### SDK example

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-comparison-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-comparison-cloud), it hides the [Storage existence](https://apireference.groupdocs.cloud/comparison/#/Storage/StorageExists) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.


{{< tabs "example2">}} {{< tab "C#" >}}

```csharp
using System;
using GroupDocs.Comparison.Cloud.Sdk.Api;
using GroupDocs.Comparison.Cloud.Sdk.Client;
using GroupDocs.Comparison.Cloud.Sdk.Model.Requests;

namespace GroupDocs.Comparison.Cloud.Examples.CSharp
{
	// Is Storage Exist
	class Storage_Exist
	{
		public static void Run()
		{
			var configuration = new Configuration(Common.MyAppSid, Common.MyAppKey);
			var apiInstance = new StorageApi(configuration);

			try
			{
				var request = new StorageExistsRequest(Common.MyStorage);

				var response = apiInstance.StorageExists(request);
				Console.WriteLine("Expected response type is StorageExist: " + response.Exists.Value.ToString());
			}
			catch (Exception e)
			{
				Console.WriteLine("Exception while calling StorageApi: " + e.Message);
			}
		}
	}
}
```

{{< /tab >}} {{< tab "Java" >}}

```java
package examples.Working_With_Storage;

import com.groupdocs.cloud.comparison.api.*;
import com.groupdocs.cloud.comparison.client.ApiException;
import com.groupdocs.cloud.comparison.model.*;
import com.groupdocs.cloud.comparison.model.requests.*;
import examples.Utils;

public class Comparison_Java_Storage_Exist {

	public static void main(String[] args) {

		StorageApi apiInstance = new StorageApi(Utils.AppSID, Utils.AppKey);
		try {
			StorageExistsRequest request = new StorageExistsRequest(Utils.MYStorage);
			StorageExist response = apiInstance.storageExists(request);
			System.out.println("Expected response type is StorageExist: " + response.getExists());
		} catch (ApiException e) {
			System.err.println("Exception while calling StorageApi:");
			e.printStackTrace();
		}
	}
}
```

{{< /tab >}} {{< tab "PHP" >}}

```php
<?php

include(dirname(__DIR__) . '\CommonUtils.php');

try {
    $apiInstance = CommonUtils::GetStorageApiInstance();

	$request = new GroupDocs\Comparison\Model\Requests\StorageExistsRequest(CommonUtils::$MyStorage);
		$response = $apiInstance->storageExists($request);
		
		echo "Expected response type is StorageExist: ", $response;
} catch (Exception $e) {
    echo "Something went wrong: ", $e->getMessage(), "\n";
}
?>
```


{{< /tab >}} {{< tab "Node.js" >}}

```js
"use strict";
class Comparison_Node_Storage_Exist {
	static Run() {
		// retrieve supported file-formats
		var request = new groupdocs_comparison_cloud_1.StorageExistsRequest(myStorage);
		storageApi.storageExists(request)
			.then(function (response) {
				console.log("Expected response type is StorageExist: " + response.exists);
			})
			.catch(function (error) {
				console.log("Error: " + error.message);
			});
	}
}
module.exports = Comparison_Node_Storage_Exist;

```

{{< /tab >}} {{< tab "Python" >}}

```python
# Import modules
import groupdocs_comparison_cloud

from Common_Utilities.Utils import Common_Utilities


class Comparison_Python_Storage_Exist:
    
    @classmethod
    def Run(self):
        # Create instance of the API
        api = Common_Utilities.Get_StorageApi_Instance()
        
        try:
            request = groupdocs_comparison_cloud.StorageExistsRequest(Common_Utilities.myStorage)
            response = api.storage_exists(request)
            
            print("Expected response type is StorageExist: " + str(response))
        except groupdocs_comparison_cloud.ApiException as e:
            print("Exception while calling API: {0}".format(e.message))
```

{{< /tab >}} {{< tab "Ruby" >}}

```ruby
# Load the gem
require 'groupdocs_comparison_cloud'
require 'common_utilities/Utils.rb'

class Working_With_Storage
  def self.Comparison_Ruby_Storage_Exist()

    # Getting instance of the API
    $api = Common_Utilities.Get_StorageApi_Instance()
    
    $request = GroupDocsComparisonCloud::StorageExistsRequest.new($myStorage)
    $response = $api.storage_exists($request)

    puts("Expected response type is StorageExist: " + ($response).to_s)
  end
end
```

{{< /tab >}} {{< tab "Apex" >}}

```javascript
// Create config and API instances
Configuration config = new Configuration('YOUR_API_KEY', 'YOUR_API_SECRET'); // Replace with your credentials
StorageApi storageApi = new StorageApi(config);

try {
    // Prepare the storage exists request
    StorageExistsRequest storageExistsRequest = new StorageExistsRequest('MyStorageName'); // Replace 'MyStorageName' with your storage name

    // Check if the storage exists
    StorageExist response = storageApi.storageExists(storageExistsRequest);

    // Log the response
    System.debug('Expected response type is StorageExist: ' + response.Exists);
} catch (Exception e) {
    System.debug('Exception while calling StorageApi: ' + e.getMessage());
}
```

{{< /tab >}} {{< /tabs >}}

## Storage object existence API

This API intended for checking existence of file or folder in [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud).

### API Explorer

[GroupDocs.Comparison Cloud API Reference](https://apireference.groupdocs.cloud/comparison/#/) lets you to try out [Storage existence API](https://apireference.groupdocs.cloud/comparison/#/Storage/StorageExists) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs exposes.

### Request parameters

|Parameter|Description
|---|---
|**path**|Path of the file or folder

Required. Can be passed as query string parameter or as part of the URL
|storageName|Name of the storage. If not set, then default storage used
|versionId|File version id

### cURL example

{{< tabs "example3">}} {{< tab "Linux/MacOS/Bash" >}}
```bash
curl -X GET "https://api.groupdocs.cloud/v2.0/comparison/storage/exist/comparisondocs?storageName#MyStorage" \
    -H "accept: application/json" \
    -H "authorization: Bearer $JWT_TOKEN"
```
{{< /tab >}}

{{< tab "Windows PowerShell" >}}
```powershell
curl.exe -X GET `
    "https://api.groupdocs.cloud/v2.0/comparison/storage/exist/comparisondocs?storageName#MyStorage" `
    -H "accept: application/json" `
    -H "authorization: Bearer $env:JWT_TOKEN"
```
{{< /tab >}}

{{< tab "Windows CMD" >}}
```cmd
curl -X GET ^
    "https://api.groupdocs.cloud/v2.0/comparison/storage/exist/comparisondocs?storageName#MyStorage" ^
    -H "accept: application/json" ^
    -H "authorization: Bearer %JWT_TOKEN%"
```
{{< /tab >}} {{< tab "Response" >}}

```json
{
  "exists": true,
  "isFolder": true
}
```
{{< /tab >}} {{< /tabs >}}

### SDK example

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-comparison-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-comparison-cloud), it hides the [Storage Object existence](https://apireference.groupdocs.cloud/comparison/#/Storage/ObjectExists) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.

{{< tabs "example4">}} {{< tab "C#" >}}

```csharp
using System;
using GroupDocs.Comparison.Cloud.Sdk.Api;
using GroupDocs.Comparison.Cloud.Sdk.Client;
using GroupDocs.Comparison.Cloud.Sdk.Model.Requests;

namespace GroupDocs.Comparison.Cloud.Examples.CSharp
{
	// Is Object Exists
	class Object_Exists
	{
		public static void Run()
		{
			var configuration = new Configuration(Common.MyAppSid, Common.MyAppKey);
			var apiInstance = new StorageApi(configuration);

			try
			{
				var request = new ObjectExistsRequest("Comparisondocs/one-page.docx", Common.MyStorage);

				var response = apiInstance.ObjectExists(request);
				Console.WriteLine("Expected response type is ObjectExist: " + response.Exists.Value.ToString());
			}
			catch (Exception e)
			{
				Console.WriteLine("Exception while calling StorageApi: " + e.Message);
			}
		}
	}
}
```

{{< /tab >}} {{< tab "Java" >}}

```java
package examples.Working_With_Storage;

import com.groupdocs.cloud.comparison.api.*;
import com.groupdocs.cloud.comparison.client.ApiException;
import com.groupdocs.cloud.comparison.model.*;
import com.groupdocs.cloud.comparison.model.requests.*;
import examples.Utils;

public class Comparison_Java_Object_Exists {

	public static void main(String[] args) {

		StorageApi apiInstance = new StorageApi(Utils.AppSID, Utils.AppKey);
		try {
			ObjectExistsRequest request = new ObjectExistsRequest("Comparisondocs\\one-page.docx", Utils.MYStorage, null);
			ObjectExist response = apiInstance.objectExists(request);
			System.out.println("Expected response type is ObjectExist: " + response.getExists());
		} catch (ApiException e) {
			System.err.println("Exception while calling StorageApi:");
			e.printStackTrace();
		}
	}
}
```

{{< /tab >}} {{< tab "PHP" >}}

```php
<?php

include(dirname(__DIR__) . '\CommonUtils.php');

	try {
		$apiInstance = CommonUtils::GetStorageApiInstance();

		$request = new GroupDocs\Comparison\Model\Requests\ObjectExistsRequest("comparisondocs\one-page.docx", CommonUtils::$MyStorage);
		$response = $apiInstance->objectExists($request);
		
		echo "Expected response type is ObjectExist: ", $response;
	} catch (Exception $e) {
		echo "Something went wrong: ", $e->getMessage(), "\n";
	}
?>
```


{{< /tab >}} {{< tab "Node.js" >}}

```js
"use strict";
class Comparison_Node_Object_Exists {
	static Run() {
		// retrieve supported file-formats
		var request = new groupdocs_comparison_cloud_1.ObjectExistsRequest("Comparisondocs/one-page.docx", myStorage);
		storageApi.objectExists(request)
			.then(function (response) {
				console.log("Expected response type is ObjectExist: " + response.exists);
			})
			.catch(function (error) {
				console.log("Error: " + error.message);
			});
	}
}
module.exports = Comparison_Node_Object_Exists;

```

{{< /tab >}} {{< tab "Python" >}}

```python
# Import modules
import groupdocs_comparison_cloud

from Common_Utilities.Utils import Common_Utilities


class Comparison_Python_Object_Exists:
    
    @classmethod
    def Run(self):
        # Create instance of the API
        api = Common_Utilities.Get_StorageApi_Instance()
        
        try:
            request = groupdocs_comparison_cloud.ObjectExistsRequest("comparisondocs\\one-page.docx", Common_Utilities.myStorage)
            response = api.object_exists(request)
            
            print("Expected response type is ObjectExist: " + str(response))
        except groupdocs_comparison_cloud.ApiException as e:
            print("Exception while calling API: {0}".format(e.message))
```

{{< /tab >}} {{< tab "Ruby" >}}

```ruby
# Load the gem
require 'groupdocs_comparison_cloud'
require 'common_utilities/Utils.rb'

class Working_With_Storage
  def self.Comparison_Ruby_Object_Exists()

    # Getting instance of the API
    $api = Common_Utilities.Get_StorageApi_Instance()
    
    $request = GroupDocsComparisonCloud::ObjectExistsRequest.new("comparisondocs/one-page.docx", $myStorage)
    $response = $api.object_exists($request)

    puts("Expected response type is ObjectExist: " + ($response).to_s)
  end
end
```

{{< /tab >}} {{< tab "Apex" >}}

```javascript
// Create config and API instances
Configuration config = new Configuration('YOUR_API_KEY', 'YOUR_API_SECRET'); // Replace with your credentials
StorageApi storageApi = new StorageApi(config);

try {
    // Prepare the object exists request
    ObjectExistsRequest objectExistsRequest = new ObjectExistsRequest('Comparisondocs/one-page.docx', null);

    // Check if the object exists
    ObjectExist response = storageApi.objectExists(objectExistsRequest);

    // Log the response
    System.debug('Expected response type is ObjectExist: ' + response.Exists);
} catch (Exception e) {
    System.debug('Exception while calling StorageApi: ' + e.getMessage());
}
```

{{< /tab >}} {{< /tabs >}}

## Storage Space Usage API

This API intended for getting total and used space of the [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud)

### API Explorer

[GroupDocs.Comparison Cloud API Reference](https://apireference.groupdocs.cloud/conversion/#/) lets you to try out [storage space usage API](https://apireference.groupdocs.cloud/comparison/#/Storage/GetDiscUsage) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs exposes.

### Request parameters

|Parameter|Description
|---|---
|storageName|Name of the storage. If not set, then default storage used

### cURL example

{{< tabs "example5">}} {{< tab "Linux/MacOS/Bash" >}}
```bash
curl -X GET "https://api.groupdocs.cloud/v2.0/comparison/storage/disc?storageName#MyStorage" \
    -H "accept: application/json" \
    -H "authorization: Bearer $JWT_TOKEN"
```
{{< /tab >}}

{{< tab "Windows PowerShell" >}}
```powershell
curl.exe -X GET `
    "https://api.groupdocs.cloud/v2.0/comparison/storage/disc?storageName#MyStorage" `
    -H "accept: application/json" `
    -H "authorization: Bearer $env:JWT_TOKEN"
```
{{< /tab >}}

{{< tab "Windows CMD" >}}
```cmd
curl -X GET ^
    "https://api.groupdocs.cloud/v2.0/comparison/storage/disc?storageName#MyStorage" ^
    -H "accept: application/json" ^
    -H "authorization: Bearer %JWT_TOKEN%"
```
{{< /tab >}} {{< tab "Response" >}}

```json
{
  "usedSize": 31032368,
  "totalSize": 3221225472
}
```
{{< /tab >}} {{< /tabs >}}

### SDK example

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-comparison-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-comparison-cloud), it hides the [storage space usage API](https://apireference.groupdocs.cloud/comparison/#/Storage/GetDiscUsage) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.

{{< tabs "example6">}} {{< tab "C#" >}}

```csharp
using System;
using GroupDocs.Comparison.Cloud.Sdk.Api;
using GroupDocs.Comparison.Cloud.Sdk.Client;
using GroupDocs.Comparison.Cloud.Sdk.Model.Requests;

namespace GroupDocs.Comparison.Cloud.Examples.CSharp
{
	// Get Get Disc Usage
	class Get_Disc_Usage
	{
		public static void Run()
		{
			var configuration = new Configuration(Common.MyAppSid, Common.MyAppKey);
			var apiInstance = new StorageApi(configuration);

			try
			{
				var request = new GetDiscUsageRequest(Common.MyStorage);

				var response = apiInstance.GetDiscUsage(request);
				Console.WriteLine("Expected response type is DiscUsage: " + response.UsedSize.ToString());
			}
			catch (Exception e)
			{
				Console.WriteLine("Exception while calling StorageApi: " + e.Message);
			}
		}
	}
}
```

{{< /tab >}} {{< tab "Java" >}}

```java
package examples.Working_With_Storage;

import com.groupdocs.cloud.comparison.api.*;
import com.groupdocs.cloud.comparison.client.ApiException;
import com.groupdocs.cloud.comparison.model.*;
import com.groupdocs.cloud.comparison.model.requests.*;
import examples.Utils;

public class Comparison_Java_Get_Disc_Usage {

	public static void main(String[] args) {

		StorageApi apiInstance = new StorageApi(Utils.AppSID, Utils.AppKey);
		try {
			GetDiscUsageRequest request = new GetDiscUsageRequest(Utils.MYStorage);
			DiscUsage response = apiInstance.getDiscUsage(request);
			System.out.println("Expected response type is DiscUsage: " + response.getUsedSize());
		} catch (ApiException e) {
			System.err.println("Exception while calling StorageApi:");
			e.printStackTrace();
		}
	}
}
```

{{< /tab >}} {{< tab "PHP" >}}

```php
<?php

include(dirname(__DIR__) . '\CommonUtils.php');

	try {
		$apiInstance = CommonUtils::GetStorageApiInstance();

		$request = new GroupDocs\Comparison\Model\Requests\GetDiscUsageRequest(CommonUtils::$MyStorage);
		$response = $apiInstance->getDiscUsage($request);
			
		echo "Expected response type is DiscUsage: ", $response;
	} catch (Exception $e) {
		echo "Something went wrong: ", $e->getMessage(), "\n";
	}
?>
```


{{< /tab >}} {{< tab "Node.js" >}}

```js
"use strict";
class Comparison_Node_Get_Disc_Usage {
	static Run() {
		// retrieve supported file-formats
		var request = new groupdocs_comparison_cloud_1.GetDiscUsageRequest(myStorage);
		storageApi.getDiscUsage(request)
			.then(function (response) {
				console.log("Expected response type is DiscUsage: " + response.usedSize);
			})
			.catch(function (error) {
				console.log("Error: " + error.message);
			});
	}
}
module.exports = Comparison_Node_Get_Disc_Usage;

```

{{< /tab >}} {{< tab "Python" >}}

```python
# Import modules
import groupdocs_comparison_cloud

from Common_Utilities.Utils import Common_Utilities


class Comparison_Python_Get_Disc_Usage:
    
    @classmethod
    def Run(self):
        # Create instance of the API
        api = Common_Utilities.Get_StorageApi_Instance()
        
        try:
            request = groupdocs_comparison_cloud.GetDiscUsageRequest(Common_Utilities.myStorage)
            response = api.get_disc_usage(request)
            
            print("Expected response type is DiscUsage: " + str(response))
        except groupdocs_comparison_cloud.ApiException as e:
            print("Exception while calling API: {0}".format(e.message))
```

{{< /tab >}} {{< tab "Ruby" >}}

```ruby
# Load the gem
require 'groupdocs_comparison_cloud'
require 'common_utilities/Utils.rb'

class Working_With_Storage
  def self.Comparison_Ruby_Get_Disc_Usage()

    # Getting instance of the API
    $api = Common_Utilities.Get_StorageApi_Instance()
    
    $request = GroupDocsComparisonCloud::GetDiscUsageRequest.new($myStorage)
    $response = $api.get_disc_usage($request)

    puts("Expected response type is DiscUsage: " + ($response).to_s)
  end
end
```

{{< /tab >}} {{< tab "Apex" >}}

```javascript
// Create config and API instances
Configuration config = new Configuration('YOUR_API_KEY', 'YOUR_API_SECRET'); // Replace with your credentials
StorageApi storageApi = new StorageApi(config);

try {
    // Prepare the disk usage request
    GetDiscUsageRequest getDiscUsageRequest = new GetDiscUsageRequest(null);

    // Retrieve the disk usage
    DiscUsage response = storageApi.getDiscUsage(getDiscUsageRequest);

    // Log the used size
    System.debug('Expected response type is DiscUsage: ' + response.UsedSize);
} catch (Exception e) {
    System.debug('Exception while calling StorageApi: ' + e.getMessage());
}
```

{{< /tab >}} {{< /tabs >}}

## Storage File Versions API

This API intended for getting the list of file versions, stored in the [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud)

### API Explorer

[GroupDocs.Comparison Cloud API Reference](https://apireference.groupdocs.cloud/conversion/#/) lets you to try out [Storage File Versions API](https://apireference.groupdocs.cloud/comparison/#/Storage/GetFileVersions) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs exposes.

### Request parameters

|Parameter|Description
|---|---
|**path**|Path of the file including file name and extension e.g. /Folder1/file.ext

Required. Can be passed as query string parameter or as part of the URL
|storageName|Name of the storage. If not set, then default storage used

### cURL example

{{< tabs "example7">}} {{< tab "Linux/MacOS/Bash" >}}
```bash
curl -X GET "https://api.groupdocs.cloud/v2.0/comparison/storage/version/one-page.docx?storageName#MyStorage" \
    -H "accept: application/json" \
    -H "authorization: Bearer $JWT_TOKEN"
```
{{< /tab >}}

{{< tab "Windows PowerShell" >}}
```powershell
curl.exe -X GET `
    "https://api.groupdocs.cloud/v2.0/comparison/storage/version/one-page.docx?storageName#MyStorage" `
    -H "accept: application/json" `
    -H "authorization: Bearer $env:JWT_TOKEN"
```
{{< /tab >}}

{{< tab "Windows CMD" >}}
```cmd
curl -X GET ^
    "https://api.groupdocs.cloud/v2.0/comparison/storage/version/one-page.docx?storageName#MyStorage" ^
    -H "accept: application/json" ^
    -H "authorization: Bearer %JWT_TOKEN%"
```
{{< /tab >}} {{< tab "Response" >}}

```json
{
  "value": [
    {
      "versionId": "null",
      "isLatest": true,
      "name": "one-page.docx",
      "isFolder": false,
      "modifiedDate": "2018-08-16T19:45:05+00:00",
      "size": 347612,
      "path": "/one-page.docx"
    }
  ]
}
```
{{< /tab >}} {{< /tabs >}}

### SDK example

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-comparison-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-comparison-cloud), it hides the [Storage File Versions API](https://apireference.groupdocs.cloud/comparison/#/Storage/GetFileVersions) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.

{{< tabs "example8">}} {{< tab "C#" >}}

```csharp
using System;
using GroupDocs.Comparison.Cloud.Sdk.Api;
using GroupDocs.Comparison.Cloud.Sdk.Client;
using GroupDocs.Comparison.Cloud.Sdk.Model.Requests;

namespace GroupDocs.Comparison.Cloud.Examples.CSharp
{
	// Get File Versions
	class Get_File_Versions
	{
		public static void Run()
		{
			var configuration = new Configuration(Common.MyAppSid, Common.MyAppKey);
			var apiInstance = new StorageApi(configuration);

			try
			{
				var request = new GetFileVersionsRequest("one-page.docx", Common.MyStorage);

				var response = apiInstance.GetFileVersions(request);
				Console.WriteLine("Expected response type is FileVersions: " + response.Value.Count.ToString());
			}
			catch (Exception e)
			{
				Console.WriteLine("Exception while calling StorageApi: " + e.Message);
			}
		}
	}
}
```

{{< /tab >}} {{< tab "Java" >}}

```java
package examples.Working_With_Storage;

import com.groupdocs.cloud.comparison.api.*;
import com.groupdocs.cloud.comparison.client.ApiException;
import com.groupdocs.cloud.comparison.model.*;
import com.groupdocs.cloud.comparison.model.requests.*;
import examples.Utils;

public class Comparison_Java_Get_File_Versions {

	public static void main(String[] args) {

		StorageApi apiInstance = new StorageApi(Utils.AppSID, Utils.AppKey);
		try {
			GetFileVersionsRequest request = new GetFileVersionsRequest("Comparisondocs\\one-page.docx", Utils.MYStorage);
			FileVersions response = apiInstance.getFileVersions(request);
			System.out.println("Expected response type is FileVersions: " + response.getValue().size());
		} catch (ApiException e) {
			System.err.println("Exception while calling StorageApi:");
			e.printStackTrace();
		}
	}
}
```

{{< /tab >}} {{< tab "PHP" >}}

```php
<?php

include(dirname(__DIR__) . '\CommonUtils.php');

	try {
		$apiInstance = CommonUtils::GetStorageApiInstance();

		$request = new GroupDocs\Comparison\Model\Requests\GetFileVersionsRequest("comparisondocs\one-page.docx", CommonUtils::$MyStorage);
		$response = $apiInstance->getFileVersions($request);
		
		echo "Expected response type is FileVersions: ", $response;
	} catch (Exception $e) {
		echo "Something went wrong: ", $e->getMessage(), "\n";
	}
?>
```


{{< /tab >}} {{< tab "Node.js" >}}

```js
"use strict";
class Comparison_Node_Get_File_Versions {
	static Run() {
		// retrieve supported file-formats
		var request = new groupdocs_comparison_cloud_1.GetFileVersionsRequest("Comparisondocs/one-page.docx", myStorage);
		storageApi.getFileVersions(request)
			.then(function (response) {
				console.log("Expected response type is FileVersions: " + response.value.length);
			})
			.catch(function (error) {
				console.log("Error: " + error.message);
			});
	}
}
module.exports = Comparison_Node_Get_File_Versions;

```

{{< /tab >}} {{< tab "Python" >}}

```python
# Import modules
import groupdocs_comparison_cloud

from Common_Utilities.Utils import Common_Utilities


class Comparison_Python_Get_File_Versions:
    
    @classmethod
    def Run(self):
        # Create instance of the API
        api = Common_Utilities.Get_StorageApi_Instance()
        
        try:
            request = groupdocs_comparison_cloud.GetFileVersionsRequest("comparisondocs\\one-page.docx", Common_Utilities.myStorage)
            response = api.get_file_versions(request)
            
            print("Expected response type is FileVersions: " + str(response))
        except groupdocs_comparison_cloud.ApiException as e:
            print("Exception while calling API: {0}".format(e.message))
```

{{< /tab >}} {{< tab "Ruby" >}}

```ruby
# Load the gem
require 'groupdocs_comparison_cloud'
require 'common_utilities/Utils.rb'

class Working_With_Storage
  def self.Comparison_Ruby_Get_File_Versions()

    # Getting instance of the API
    $api = Common_Utilities.Get_StorageApi_Instance()
    
    $request = GroupDocsComparisonCloud::GetFileVersionsRequest.new("comparisondocs/one-page.docx", $myStorage)
    $response = $api.get_file_versions($request)

    puts("Expected response type is FileVersions: " + ($response).to_s)
  end
end
```

{{< /tab >}} {{< tab "Apex" >}}

```javascript
// Create config and API instances
Configuration config = new Configuration('YOUR_API_KEY', 'YOUR_API_SECRET'); // Replace with your credentials
StorageApi storageApi = new StorageApi(config);

try {
    // Prepare the file versions request
    GetFileVersionsRequest getFileVersionsRequest = new GetFileVersionsRequest('one-page.docx', null);

    // Retrieve the file versions
    FileVersions response = storageApi.getFileVersions(getFileVersionsRequest);

    // Log the count of file versions
    System.debug('Expected response type is FileVersions: ' + response.Value.size());
} catch (Exception e) {
    System.debug('Exception while calling StorageApi: ' + e.getMessage());
}
```

{{< /tab >}} {{< /tabs >}}
