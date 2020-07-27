All notable changes to this project's current version will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/). Note that this
project does not adhere to [Semantic Versioning](https://semver.org/spec/v2.0.0.html) : major and
minor versions are following those of [`spring-boot-starter-parent`](https://spring.io/projects/spring-boot)
and patch version can be incremented even for breaking changes.

### Changed
* Upgrade to `spring-boot-starter-parent` [2.3.2.RELEASE](https://github.com/spring-projects/spring-boot/releases/tag/v2.3.2.RELEASE) (#2).
* Upgrade to `git-code-format-maven-plugin` [2.5](https://github.com/Cosium/git-code-format-maven-plugin/releases/tag/2.5) (#3).
  Following this upgrade the plugin has [new coordinates](https://github.com/Cosium/git-code-format-maven-plugin#breaking-changes-between-1x-and-2x)
  : `com.cosium.code:git-code-format-maven-plugin`.
* Default goal is now `verify` instead of `install` (#4). This goal has more meaning as a default :
  usually developers wants to verify the build, not install the artifact(s) in the local repository.
