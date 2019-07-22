Writing and maintaining Maven projects
[POM](https://maven.apache.org/guides/introduction/introduction-to-the-pom.html)
is boring. This parent POM is simplifying those tasks by defining:
* common properties that can be easily overridden;
* a convenient set of configuration default (if you use GitHub, Travis CI and JFrog Bintray).

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
  <!-- override only the needed properties -->
  <properties>
    <project.name>${project.artifactId}</project.name>
    <project.description>${my.name} parent POM.</project.description>
    <project.url>${project.scm.url}</project.url>
    <project.inceptionYear>2019</project.inceptionYear>
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
