All notable changes to this project's current version will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/). Note that
this project does not adhere to [Semantic Versioning](https://semver.org/spec/v2.0.0.html)
: major and minor versions are following those of
[`spring-boot-starter-parent`](https://spring.io/projects/spring-boot) and patch version
can be incremented even for breaking changes.

### Added

### Changed

- Upgrade to spring-boot-dependencies
  [2.6.7](https://github.com/spring-projects/spring-boot/releases/tag/v2.6.7) (#26).
- Upgrade git-code-format-maven-plugin to [3.3](https://github.com/Cosium/git-code-format-maven-plugin#breaking-changes-between-2x-and-3x)
  (#27). This upgrade requires you now use Java 11+ in order to build you project, even if
  the target (`this.java.version`) is Java 8.

### Removed

### Fixed
