[![Build](https://github.com/marcwrobel/parent/workflows/build/badge.svg)](https://github.com/marcwrobel/parent/actions)
[![Supported JVM Versions](https://img.shields.io/badge/JVM-8--17-brightgreen.svg?logo=openjdk)](https://github.com/marcwrobel/parent/)
[![Sonarcloud Status](https://sonarcloud.io/api/project_badges/measure?project=fr.marcwrobel:parent&metric=alert_status)](https://sonarcloud.io/dashboard?id=fr.marcwrobel:parent)
[![SonarCloud Vulnerabilities](https://sonarcloud.io/api/project_badges/measure?project=fr.marcwrobel:parent&metric=bugs)](https://sonarcloud.io/dashboard?id=fr.marcwrobel:parent)
[![Maven Central](https://img.shields.io/maven-central/v/fr.marcwrobel/parent.svg?label=Maven%20Central)](https://search.maven.org/search?q=g:%22fr.marcwrobel%22%20AND%20a:%22parent%22)

Writing and maintaining Maven projects
[POM](https://maven.apache.org/guides/introduction/introduction-to-the-pom.html) is
boring. This parent POM is simplifying those tasks in the context of my open source
projects by:

- defining common project and developer
  [properties](https://books.sonatype.com/mvnref-book/reference/resource-filtering-sect-properties.html)
  that can be easily overridden in a single place;
- defining a convenient set of configuration default (if you use
  [GitHub](https://github.com), [GitHub Actions](https://github.com/features/actions),
  [Sonatype OSSRH](https://oss.sonatype.org), [Docker Hub](https://hub.docker.com)).
- providing dependency and plugin management

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
		<version>2.7.3</version>
		<relativePath/>
	</parent>

	<groupId>groupId</groupId>
	<artifactId>artifactId</artifactId>
	<version>x.y.z-SNAPSHOT</version>

	<name>name</name>
	<description>description</description>
	<url>https://url.com</url>
	<inceptionYear>2020</inceptionYear>
	...
	<!-- only override if needed -->
	<properties>
		<this.java.version>1.8</this.java.version>
		<this.maven.version>3.8.5</this.maven.version>

		<dev.name>Marc Wrobel</dev.name>
		<dev.username>marcwrobel</dev.username>
		<dev.email>marc.wrobel@gmail.com</dev.email>
		<dev.url>http://www.marcwrobel.fr/</dev.url>
		...
	</properties>
</project>
```

All inherited information can be overridden, especially properties (take a look at this
[parent POM](pom.xml) for an exhaustive list). Remember you can display the effective POM
using [`maven-help-plugin`](https://maven.apache.org/plugins/maven-help-plugin/effective-pom-mojo.html)
in your project:

```bash
mvn help:effective-pom
```

Note that despite the code target (`this.java.version`) can be Java 8, you will have to
use at least Java 11 to build it (because maven-git-code-format dropped Java 8 support
since version 3.x). You must also declare a
[`maven-versions-rules.xml`](/maven-versions-rules.xml) file at the root of your project.

## What's included?

- default Maven configuration for `organization`, `developers`, `scm`, `issueManagement`,
  `ciManagement`, `distributionManagement` and `defaultGoal`,
- dependency management for dozens of libraries
  ([Apache Commons](https://commons.apache.org), [java extensions](https://www.jcp.org/),
  [Groovy](http://www.groovy-lang.org/), [Spring](https://spring.io/),
  [Hibernate](https://hibernate.org/) to name a few),
- plugin management for
  [flatten-maven-plugin](https://www.mojohaus.org/flatten-maven-plugin/)
  ([CI-friendly configuration](http://maven.apache.org/maven-ci-friendly.html)),
- plugin management for
  [git-commit-id-plugin](https://github.com/git-commit-id/maven-git-commit-id-plugin)
  (provided by `spring-boot-starter-parent` but non-verbose),
- plugin management for [jacoco-maven-plugin](https://www.jacoco.org/jacoco/)
  (activation),
- plugin management for
  [jib-maven-plugin](https://github.com/GoogleContainerTools/jib/tree/master/jib-maven-plugin)
  (default `from` and `to`),
- plugin management for
  [kotlin-maven-plugin](https://kotlinlang.org/docs/reference/using-maven.html)
  (provided by `spring-boot-starter-parent`),
- plugin management for
  [maven-compiler-plugin](https://maven.apache.org/plugins/maven-compiler-plugin/)
  (provided by `spring-boot-starter-parent`),
- plugin management for
  [maven-enforcer-plugin](https://maven.apache.org/enforcer/maven-enforcer-plugin/)
  (activation and configuration rules for Java and Maven versions),
- plugin management for
  [maven-failsafe-plugin](http://maven.apache.org/surefire/maven-failsafe-plugin/)
  (provided by `spring-boot-starter-parent`),
- plugin management for
  [maven-release-plugin](https://maven.apache.org/maven-release/maven-release-plugin/)
  (change `tagNameFormat`).
- plugin management for
  [maven-git-code-format](https://github.com/Cosium/maven-git-code-format)
  (hooks installation),
- plugin management and project configuration for
  [sonar-maven-plugin](https://sonarsource.github.io/sonar-scanner-maven/),
- plugin management and project configuration for
  [versions-maven-plugin](https://www.mojohaus.org/versions-maven-plugin/),
- plugin management for
  [spring-boot-maven-plugin](https://docs.spring.io/spring-boot/docs/current/maven-plugin/index.html)
  (provided by `spring-boot-starter-parent`).
- a `release` profile, activated automatically during release with `maven-release-plugin`,
  which triggers :
    - sources attachment with
      [maven-source-plugin](https://maven.apache.org/plugins/maven-source-plugin/),
    - javadoc attachment with
      [[maven-javadoc-plugin](http://maven.apache.org/plugins/maven-javadoc-plugin/),
    - a PGP signature with
      [maven-gpg-plugin](https://maven.apache.org/plugins/maven-gpg-plugin/).
- an `analyze` profile, that must be activated manually, which triggers the `jacoco` agent
  during unit or integration tests in order to calculate code coverage for SonarQube.

Take a look at the [POM](pom.xml) for more details.

## Why `spring-boot-starter-parent`?

This POM is inheriting from
[`spring-boot-starter-parent`](https://spring.io/projects/spring-boot) in order to:

- take advantage of the Spring Boot team's work on dependencies (with
  `spring-boot-dependencies`);
- benefit from some good plugin management defaults.

Because this POM is relying so much on `spring-boot-starter-parent` its major and minor
versions are also following those of Spring Boot.

## Contribute

Take a look at the [contribution guide](CONTRIBUTING.md).

## Need help ?

Start a [discussion](https://github.com/marcwrobel/parent/discussions),
raise an [issue](https://github.com/marcwrobel/parent/issues?sort=created&direction=desc&state=open)
or contribute with [a pull-request](https://github.com/marcwrobel/parent/pulls) (please take a look at the
[contribution guide](CONTRIBUTING.md) before).

And for the things that must be kept private (**only** !), such as [security issues](/SECURITY.md), email me at
[marc.wrobel@gmail.com](mailto:marc.wrobel@gmail.com).
