All notable changes to this project's current version will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/). Note that
this project does not adhere to [Semantic Versioning](https://semver.org/spec/v2.0.0.html)
: major and minor versions are following those of
[`spring-boot-starter-parent`](https://spring.io/projects/spring-boot) and patch version
can be incremented even for breaking changes.

### Added

### Changed

- Bump maven-site-plugin from 3.12.0 to 3.12.1 (#33).
- Bump spring-boot-starter-parent from 2.7.1 to 2.7.5 (#36).
- Bump flatten-maven-plugin from 1.2.7 to 1.3.0 (#37).
- Bump git-code-format-maven-plugin from 3.4 to 3.5 (#38).
- Bump jib-maven-plugin from 3.2.1 to 3.3.1 (#39).

### Removed

### Fixed

## Internal

- Prevent duplicate build workflow run on pull requests (#40).
- Disable sonar analysis on pull requests from forks (#40).
- Bump actions/checkout from 2 to 3 (#34).
- Bump actions/setup-java from 1 to 3 (#35).
- Switch to `temurin` for `build` workflow (#35).
- Activate `maven` cache in `build` workflow (#35).
- Reformat and annotate build workflow file (#41).
- Improve build workflow cache (#41). Add a cache for Sonar and explicitly configure Maven cache.
- Use `fetch_depth=0` instead of a custom command in build workflow to disable shallow clones (#41).
  As seen [on Sonarcloud documentation](https://docs.sonarqube.org/latest/analysis/github-integration/).
- Add `CODEOWNERS` (#42).
- Add a Contributor Covenant Code of Conduct (#42).
- Add a security policy (#42).
- Add a supported JVM versions badge (#42).
- Add a SonarCloud vulnerabilities badge (#42).
- Add a `.tool-versions` file (#42).
