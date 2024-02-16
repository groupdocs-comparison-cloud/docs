---
id: "available-sdks"
url: "comparison/available-sdks"
title: "GroupDocs.Comparison Cloud SDKs"
productName: "GroupDocs.Comparison Cloud"
weight: 4
description: ""
keywords: ""
toc: True
---
GroupDocs.Comparison Cloud is a modern REST oriented API, that allows easy integration into existing systems.

## Why use an SDK?

Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project.

## SDK benefits

Our supported SDKs are 100% tested and out of the box running. These SDKs are open source and have an MIT license. You can use them, and even customize them for absolutely free of charge.

### Supported SDKs

**GroupDocs.Comparison Cloud SDK for .NET** allows you to incorporate GroupDocs.Comparison Cloud services in your .NET applications quickly and easily.

Install [GroupDocs.Comparison-Cloud](https://www.nuget.org/packages/GroupDocs.comparison-Cloud/) via NuGet from Package Manager:

```html
PM> Install-Package GroupDocs.Comparison-Cloud
```

{{< alert style="info" >}}
Complete source code of GroupDocs.Comparison Cloud SDK for .Net is freely available on the [GitHub](https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-dotnet). Please see the GroupDocs.Comparison Cloud SDK for .NET [Examples here](https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-dotnet/tree/master/GroupDocs.Comparison.Cloud.Sdk.Test).{{< /alert >}}

**GroupDocs.Comparison for Cloud SDK forPHP** allows you to incorporate GroupDocs.Comparison Cloud services in yourPHP  applications quickly and easily.

groupdocs-comparison-cloud is available on Packagist as the [groupdocs-comparison-cloud](https://packagist.org/packages/groupdocscloud/groupdocs-comparison-cloud) package. Run the following command:

```html
composer require groupdocscloud/groupdocs-comparison-cloud
```

To use the SDK, use Composer's [autoload](https://getcomposer.org/doc/00-intro.md#autoloading):

```html
require_once('vendor/autoload.php');
```

{{< alert style="info" >}}
Complete source code of GroupDocs.Comparison Cloud SDK forPHP  is freely available on [GitHub](https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-php). Please see the GroupDocs.Comparison Cloud SDK for PHP [Examples here](https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-php/tree/master/tests/GroupDocs/Comparison/ApiTests).{{< /alert >}}

**GroupDocs.Comparison Cloud SDK forJava** allows you to incorporate GroupDocs.Comparison Cloud services in yourJava  applications quickly and easily.

You can directly include the source code of GroupDocs.Comparison Cloud SDK forJava  in your own project, the source code is available from [here](https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-java).

Alternatively, you can use [**Maven**](https://releases.groupdocs.cloud/java/repo/com/groupdocs/groupdocs-comparison-cloud/) to include in yourJava  project. Below are the steps for Maven.

#### GroupDocs Maven Repository

```xml
<repository>
    <id>groupdocs-artifact-repository</id>
    <name>GroupDocs Artifact Repository</name>
    <url>https://releases.groupdocs.cloud/java/repo/</url>
</repository>
```

#### Maven Dependency

```xml
<dependency>
    <groupId>com.groupdocs</groupId>
    <artifactId>groupdocs-comparison-cloud</artifactId>
    <version>18.4</version>
    <scope>compile</scope>
</dependency>
```

#### Get Sources and Javadocs

#### Maven

```bash
$ mvn dependency:sources
$ mvn dependency:resolve -Dclassifier#javadoc
```

#### Eclipse IDE

```bash
$ mvn eclipse:eclipse -DdownloadSources#true
$ mvn eclipse:eclipse -DdownloadSources#true -DdownloadJavadocs#false
```

**pom.xml**

```xml
<build>
    <plugins>
        <plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-eclipse-plugin</artifactId>
            <configuration>
                <downloadSources>true</downloadSources>
                <downloadJavadocs>false</downloadJavadocs>
            </configuration>
        </plugin>
    </plugins>
</build>
```

**Direct Download**

{{< alert style="info" >}}
Complete source code of GroupDocs.Comparison Cloud SDK forJava  is freely available on the [GitHub](https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-java). Please see the GroupDocs.Comparison Cloud SDK forJava  [Examples here](https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-java/tree/master/src/test/java/com/groupdocs/cloud/comparison/api).
{{< /alert >}}

**GroupDocs.Comparison Cloud SDK forRuby** allows you to incorporate GroupDocs.Comparison Cloud services in yourRuby   applications quickly and easily. It is available on [RubyGem distribution](https://rubygems.org/gems/groupdocs_comparison_cloud) package. Run the following command::

```html
gem install groupdocs_cloud_comparison
```

{{< alert style="info" >}}
Complete source code of GroupDocs.Comparison Cloud SDK forRuby   is freely available on the [GitHub](https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-ruby).
{{< /alert >}}

{{< alert style="info" >}}Please see the GroupDocs.Comparison Cloud SDK forRuby   [Examples here](https://github.com/groupdocs-comparison-cloud/groupdocs-comparison-cloud-ruby/tree/master/test/api).{{< /alert >}}
