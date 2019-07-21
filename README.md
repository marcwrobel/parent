Writing and maintaining Maven projects [POM](https://maven.apache.org/guides/introduction/introduction-to-the-pom.html)
is boring. This parent POM is simplifying those tasks.

## How to use it?
Just use it as your project POM's parent:
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
  <name>my project</name>
  <description>My project description.</description>
...
</project>
