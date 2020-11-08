# Apache HTTP Server mime.types for use with Java's [MimetypesFileTypeMap](https://docs.oracle.com/javase/8/docs/api/javax/activation/MimetypesFileTypeMap.html)

[![Build Status](https://travis-ci.com/evolvedbinary/apache-httpd-mime-types.png?branch=main)](https://travis-ci.com/evolvedbinary/apache-httpd-mime-types)
[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

This Maven project simply downloads a `mime.types` file from the Apache HTTP Server project
and creates a Jar file containing the file `META-INF/mime.types`.

This makes the `mime.types` file usable from Java's [MimetypesFileTypeMap](https://docs.oracle.com/javase/8/docs/api/javax/activation/MimetypesFileTypeMap.html)
just by placing the resultant Jar file on the classpath.

## A note on Release Numbers
We try and follow the [Semantic Versioning](https://semver.org/) convention, whilst also incorporating
the version number of Apache HTTPD from which the `mime.types` file was taken.

Our release version numbers follow the template:
```
${apache.httpd.version}+${project.version}
```

So for Apache HTTP 2.4.46, and the first version of this project (i.e. 1.0.0), our release version is: `2.4.46+1.0.0`.

## Using with Maven
Add the following to the `dependencies` section of your `pom.xml`:

```xml
<dependency>
    <groupId>com.evolvedbinary.thirdparty.org.apache.httpd</groupId>
    <artifactId>apache-httpd-mime-types</artifactId>
    <version>2.4.46+1.0.0</version>
</dependency>
```

You might also like to use the latest version of the `javax.activation` API. If so, then also add the following to the `dependencies` section of your `pom.xml`:
```xml
<dependency>
    <groupId>jakarta.activation</groupId>
    <artifactId>jakarta.activation-api</artifactId>
    <version>2.0.0</version>
</dependency>
```
