All notable changes to this project's current version will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/). Note that
this project does not adhere to [Semantic Versioning](https://semver.org/spec/v2.0.0.html)
: major and minor versions are following those of
[`spring-boot-starter-parent`](https://spring.io/projects/spring-boot) and patch version
can be incremented even for breaking changes.

### Added

### Changed

- Bump spotless-maven-plugin from 2.37.0 to 2.43.0 (#96, #99, #104, #118).
- Bump maven-release-plugin from 3.0.0 to 3.0.1 (#94).
- Bump sonar-maven-plugin from 3.9.1.2184 to 3.10.0.2594 (#101).
- Bump jib-maven-plugin from 3.3.2 to 3.4.1 (#103, #120).
- Bump jacoco-maven-plugin from 0.8.10 to 0.8.11 (#105).
- Bump maven-gpg-plugin from 3.1.0 to 3.2.1 (#121, ##123).
- Bump sonar-maven-plugin from 3.10.0.2594 to 3.11.0.3922 (#122).
- Bump actions/checkout from 3 to 4 (#100).
- Bump actions/cache from 3 to 4 (#116).
- Bump java from 17.0.7+7 to 17.0.8+101 (#100).

### Removed

### Fixed

## Internal

- Use Java 17 in GitHub Actions (#101). It is now required by the sonar-maven-plugin, see
  https://docs.sonarcloud.io/appendices/scanner-environment/.
