All notable changes to this project's current version will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/). Note that this project does not adhere
to [Semantic Versioning](https://semver.org/spec/v2.0.0.html) : major and minor versions are following those
of [`spring-boot-starter-parent`](https://spring.io/projects/spring-boot)
and patch version can be incremented even for breaking changes.

### Added

- Add version management for Flatten Maven Plugin (#9). [Plugin management for `spring-boot-dependencies` has been removed](https://github.com/spring-projects/spring-boot/wiki/Spring-Boot-2.4-Release-Notes#removal-of-plugin-management-for-flatten-maven-plugin).

### Changed

- Upgrade to spring-boot-starter-parent [2.4.3](https://github.com/spring-projects/spring-boot/releases/tag/v2.4.3) (#9). See
  also [Spring Boot 2.4 Release Notes](https://github.com/spring-projects/spring-boot/wiki/Spring-Boot-2.4-Release-Notes).
- Upgrade to Git Code Format Maven Plugin [2.7](https://github.com/Cosium/git-code-format-maven-plugin) (#10).
- Upgrade to jib-maven-plugin [2.7.1](https://github.com/GoogleContainerTools/jib/blob/master/jib-maven-plugin/CHANGELOG.md#271) (#11).
- Upgrade to sonar-maven-plugin [3.8.0.2131](https://jira.sonarsource.com/secure/ReleaseNote.jspa?projectId=10977&version=16337) (#12)

### Removed

### Fixed
