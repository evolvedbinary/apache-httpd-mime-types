# Apache HTTP Server mime.types for use with Java's [MimetypesFileTypeMap](https://docs.oracle.com/javase/8/docs/api/javax/activation/MimetypesFileTypeMap.html)

[![CircleCI](https://circleci.com/gh/evolvedbinary/apache-httpd-mime-types/tree/main.svg?style=svg)](https://circleci.com/gh/evolvedbinary/apache-httpd-mime-types/tree/main)
[![Java 8](https://img.shields.io/badge/java-8+-blue.svg)](https://adoptopenjdk.net/)
[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Maven Central](https://img.shields.io/maven-central/v/com.evolvedbinary.thirdparty.org.apache.httpd/apache-httpd-mime-types?logo=apachemaven&label=maven+central&color=green)](https://central.sonatype.com/search?namespace=com.evolvedbinary.thirdparty.org.apache.httpd)

This Maven project simply downloads a `mime.types` file from the Apache HTTP Server project
and creates a Jar file containing the file `META-INF/mime.types`.

This makes the `mime.types` file usable from Java's [MimetypesFileTypeMap](https://docs.oracle.com/javase/8/docs/api/javax/activation/MimetypesFileTypeMap.html)
just by placing the resultant Jar file on the classpath.

## Why?
The Java Runtime ships with a built-in [`mimetypes.default`](https://github.com/openjdk/jdk/blob/jdk8-b120/jaxws/src/share/jaf_classes/META-INF/mimetypes.default)
which is very limited and contains only ~20 definitions.

As we could not find an existing and comprehensive source of MIME Types that were suitable for use with the
Java Activation Framework, we decided to publish our own based on the list provided by Apache HTTPD.
We hope this will also be of use to other Java developers. 

## A note on Release Numbers
We try and follow the [Semantic Versioning](https://semver.org/) convention, whilst also incorporating
the version number of Apache HTTPD from which the `mime.types` file was taken.

Our release version numbers follow the template:
```
${apache.httpd.version}+${project.version}
```

So for Apache HTTP 2.4.46, and the first version of this project (i.e. 1.0.0), our release version is: `2.4.46+1.0.0`.

## Using with Maven
Release artifacts are published to [Maven Central](https://search.maven.org/search?q=g:com.evolvedbinary.thirdparty.org.apache.httpd).

Add the following to the `<dependencies>` section of your `pom.xml`:

```xml
<dependency>
    <groupId>com.evolvedbinary.thirdparty.org.apache.httpd</groupId>
    <artifactId>apache-httpd-mime-types</artifactId>
    <version>2.4.46+1.0.0</version>
</dependency>
```

You might also like to use the latest version of the `javax.activation` API. If so, then also add the following to the `<dependencies>` section of your `pom.xml`:
```xml
<dependency>
    <groupId>jakarta.activation</groupId>
    <artifactId>jakarta.activation-api</artifactId>
    <version>2.0.0</version>
</dependency>
```
