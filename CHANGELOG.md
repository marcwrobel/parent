All notable changes to this project's current version will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html) (major and
minor versions are following those of [`spring-boot-starter-parent`](https://spring.io/projects/spring-boot)).



## 2.2.0 (unreleased)
### Added
- This CHANGELOG file to keep track of `parent`'s changes.
- An [editorconfig](https://editorconfig.org/) file for defining a basic coding styles.
- A gitignore to exclude Maven and Intellij IDEA files from being committed.
- An initial version of the `parent` POM with default Maven configuration for `organization`,
  `developers`, `scm`, `issueManagement`, `ciManagement`, `distributionManagement`.
- Plugin management for [flatten-maven-plugin](https://www.mojohaus.org/flatten-maven-plugin/).
- Plugin management for [git-commit-id-plugin](https://github.com/git-commit-id/maven-git-commit-id-plugin).
- Plugin management for [jacoco-maven-plugin](https://www.jacoco.org/jacoco/).
- Plugin management for [jib-maven-plugin](https://github.com/GoogleContainerTools/jib/tree/master/jib-maven-plugin).
- Plugin management for [kotlin-maven-plugin](https://kotlinlang.org/docs/reference/using-maven.html).
- Plugin management for [maven-compiler-plugin](https://maven.apache.org/plugins/maven-compiler-plugin/).
- Plugin management for [maven-enforcer-plugin](https://maven.apache.org/enforcer/maven-enforcer-plugin/).
- Plugin management for [maven-failsafe-plugin](http://maven.apache.org/surefire/maven-failsafe-plugin/).
- Plugin management for [maven-git-code-format](https://github.com/Cosium/maven-git-code-format).
- Plugin management for [spring-boot-maven-plugin](https://docs.spring.io/spring-boot/docs/current/maven-plugin/index.html).
- GitHub Action configuration for testing this project.
