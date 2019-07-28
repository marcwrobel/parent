Writing and maintaining Maven projects
[POM](https://maven.apache.org/guides/introduction/introduction-to-the-pom.html)
is boring. This parent POM is simplifying those tasks in the context of an open source project
developed by an individual developer by:
* defining common project and developer
  [properties](https://books.sonatype.com/mvnref-book/reference/resource-filtering-sect-properties.html)
  that can be easily overridden in a single place;
* defining a convenient set of configuration default (if you use GitHub, Travis CI and JFrog
  Bintray).
* providing dependency and plugin management

## How to use it?
Just inherit from it in your project :
```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>

  <parent>
    <groupId>fr.marcwrobel</groupId>
    <artifactId>parent</artifactId>
    <version>1.0.0-SNAPSHOT</version>
    <relativePath/>
  </parent>

  <artifactId>myproject</artifactId>
  <version>x.y.z-SNAPSHOT</version>
...
  <!-- only override if needed -->
  <properties>
    <this.name>${project.artifactId}</this.name>
    <this.description>${my.name} parent POM.</this.description>
    <this.url>${project.scm.url}</this.url>
    <this.inceptionYear>2019</this.inceptionYear>

    <this.java.version>1.8</this.java.version>
    <this.maven.version>3.6.1</this.maven.version>
    ...
  </properties>
</project>
```

All inherited information can be overridden, especially properties (take a look at
this [parent POM](pom.xml) for an exhaustive list). Remember you can display the effective POM using
[`maven-help-plugin`](https://maven.apache.org/plugins/maven-help-plugin/effective-pom-mojo.html) in
your project:
```bash
mvn help:effective-pom
```


## Why `spring-boot-starter-parent`?
This POM is inheriting from [`spring-boot-starter-parent`](https://spring.io/projects/spring-boot)
in order to:
* take advantage of the Spring Boot team's work on dependencies compatibility (see
  `spring-boot-dependencies`);
* benefit from some good plugin management defaults.

Because this POM is relying so much on `spring-boot-starter-parent` its major and minor versions are
also following those of Spring Boot.
