All notable changes to this project's current version will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/). Note that this project does not adhere
to [Semantic Versioning](https://semver.org/spec/v2.0.0.html) : major and minor versions are following those
of [`spring-boot-starter-parent`](https://spring.io/projects/spring-boot)
and patch version can be incremented even for breaking changes.

### Added

- Add a utility script to simplify dependency upgrades (#20).
- Set maven-release-plugin version (#22).

### Changed

- Upgrade spring-boot-starter-parent to [2.6.6](https://github.com/spring-projects/spring-boot/releases/tag/v2.6.6)
  (#19).
- Upgrade sonar-maven-plugin
  to [3.9.1.2184](https://jira.sonarsource.com/secure/ReleaseNote.jspa?projectId=10977&version=16990)
  (#18).
- Upgrade maven-gpg-plugin to [3.0.1](https://www.mail-archive.com/announce@maven.apache.org/msg01004.html) (#17).
- Upgrade jib-maven-plugin to 3.2.1 (#16).
- Change Jib base image to `eclipse-temurin` (#16). `eclipse-temurin` (JRE) is the default base image used by Jib since
  3.2.0.
- Upgrade jacoco-maven-plugin to [0.8.8](https://github.com/jacoco/jacoco/releases/tag/v0.8.8) (#15).
- Upgrade flatten-maven-plugin to
  [1.2.7](https://github.com/mojohaus/flatten-maven-plugin/compare/flatten-maven-plugin-1.2.5...flatten-maven-plugin-1.2.7)
  (#13).
- Upgrade minimal Maven version to 3.8.5 (#21).

### Removed

### Fixed
