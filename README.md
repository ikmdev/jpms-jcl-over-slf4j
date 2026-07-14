# jpms-jcl-over-slf4j
The jpms-jcl-over-slf4j repository is dedicated to making [jcl-over-slf4j](https://www.slf4j.org/legacy.html#jclOverSLF4J) compliant with the Java Platform Module System (JPMS). This compliance ensures that the jcl-over-slf4j shim can be seamlessly integrated into modular Java applications, leveraging the benefits of JPMS such as improved encapsulation, security, and maintainability.

`jcl-over-slf4j` is a drop-in replacement for `commons-logging` that redirects the Jakarta Commons Logging (JCL) API to SLF4J. It exists specifically to satisfy libraries such as `org.apache.httpcomponents:httpclient`, which depend on the Commons Logging API surface, without pulling in a real `commons-logging` implementation onto the classpath. See the [SLF4J legacy bridging documentation](https://www.slf4j.org/legacy.html#jclOverSLF4J) for details.

## Features

* **JPMS Compliance:** The library is packaged as a JPMS module, enabling better encapsulation and dependency management in Java projects.
* **Ease of Use:** Simple integration into projects using JPMS.

## Getting Started
### Prerequisites

* **Java 11 or higher:** JPMS was introduced in Java 9, so a minimum of Java 11 is recommended for compatibility and support.
* **Maven or Gradle:** For dependency management and building the project.

Add the following dependency to your pom.xml:
```xml
<dependency>
    <groupId>dev.ikm.jpms</groupId>
	<artifactId>jcl-over-slf4j</artifactId>
    <version>${latest-jpms-jcl-over-slf4j-version}</version>
</dependency>
```

Add the following dependency to your build.gradle:
```groovy
implementation 'dev.ikm.jpms:jcl-over-slf4j:${latest-jpms-jcl-over-slf4j-version}'
```

In your module descriptor (module-info.java), declare the dependency on the jpms-jcl-over-slf4j module:

```java
module your.module.name {
    requires dev.ikm.jpms.jcl.over.slf4j;
}
```


## Issues and Contributions
Technical and non-technical issues can be reported to the [Issue Tracker](https://github.com/ikmdev/jpms-jcl-over-slf4j/issues).

Contributions can be submitted via pull requests. Please check the [contribution guide](doc/how-to-contribute.md) for more details.
