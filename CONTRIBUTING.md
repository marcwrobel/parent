# Contribution guide

Want to contribute? Great! We try to make it easy, and all contributions, even the smaller ones, are more than welcome.
This includes bug reports, fixes, documentation, examples... But first, read this page.

## Legal

All original contributions to parent are licensed under the ASL - Apache License, version 2.0 or later.

All contributions are subject to the Developer Certificate of Origin (DCO). The DCO text is also included verbatim in
the [dco.txt](/dco.txt) file in the root directory of the repository.

## Code of conduct

In the interest of fostering an open and welcoming environment, parent team members and contributors are expected to
follow our [code of conduct](/CODE_OF_CONDUCT.md).

## Reporting an issue

This project uses [GitHub issues](https://docs.github.com/en/issues) to manage the issues. Open an issue directly in
GitHub.

If you found a bug, please use the _Bug report_ template and follow the indications.

## Developer requirements

Before you start developing on parent you will need to :

1. install Git,
2. install a JDK 11+ (for instance [Eclipse Temurin™](https://adoptium.net/temurin/releases)),
3. install [Maven 3.8+](https://maven.apache.org/download.cgi).

It is recommended to install the JDK and Maven using tools like [asdf](https://asdf-vm.com/guide/getting-started.html)
or [SDKMan!](https://sdkman.io/). Note that an asdf [.tool-versions](/.tool-versions) file that list the required JDK
and Maven versions can be found in the root directory of the repository.

Also, make sure you have set up your Git authorship correctly:

```bash
git config --global user.name "Your Full Name"
git config --global user.email your.email@example.com
```

## Code Style

Contribution to parent must adhere to the project [EditorConfig](/.editorconfig). Most IDE support EditorConfig files so
you should not have anything to do.

## Building and testing

Just execute the following commands:

```shell
git clone git@github.com:marcwrobel/parent.git
cd parent
mvn verify
```

Wait for a bit and you're done.

## Releasing

In order to publish a release to Maven Central, you :

- must be a listed collaborator on [`marcwrobel/parent`](https://github.com/marcwrobel/parent),
- must have an account on the [Sonatype Jira issue tracker](https://issues.sonatype.org),
- need to declare, in your Maven `settings.xml`, the `oss.sonatype.org` profile and the `sonatype-nexus-staging` server
  (you can find those declarations in [this sample settings.xml](/.mvn/build-settings.xml)),

Then you can start the release process. First disable the [`main` branch protection
rules](https://github.com/marcwrobel/parent/settings/branches) _Require a pull request before merging_ and _Require
status checks to pass before merging_.

Then execute the following commands:

```shell
cd parent
mvn release:prepare -Prelease
mvn release:perform -Prelease
```

If everything went fine, go to [oss.sonatype.org](https://oss.sonatype.org/) and close/release the staging repository.
Details are available on the [OSSRH publish guide](https://central.sonatype.org/publish/publish-guide/).

And finally:

1. declare the release [on GitHub](https://github.com/marcwrobel/parent/tags) :
   1. copy the [changelog content](/CHANGELOG.md) in the release notes,
   2. check _Set as the latest release_ if appropriate,
   3. and check _Create a discussion for this release_  to automatically create the [release
      discussion](https://github.com/marcwrobel/parent/discussions)),
2. empty the [changelog](/CHANGELOG.md) for the next release,
3. update parent version in [README.md](/README.md),
4. update the [security policy](/SECURITY.md) if necessary,
5. lock and unpin the [discussion](https://github.com/marcwrobel/parent/discussions) that relates to the previous
   version,
6. pin the [discussion](https://github.com/marcwrobel/parent/discussions) that relates to the current version.
7. re-enable the disabled [branch protection rules](https://github.com/marcwrobel/parent/settings/branches).

## Continuous Integration

Because we are all humans, and to ensure parent is stable for everyone, all changes must go through parent
continuous integration. parent CI is based on GitHub Actions, which means that everyone has the ability to
automatically execute CI in their forks as part of the process of making changes (except maybe the Sonarcloud analysis).

parent CI checks are:

1. project builds,
2. [SonarCloud](https://sonarcloud.io/project/overview?id=fr.marcwrobel:parent) analysis.

CI checks are automatically triggered on PR and on push on main or maintenance branches. All workflows are also
automatically triggered weekly.

## Contribution rules

To contribute, use a GitHub pull requests from your own fork. You can find more information on GitHub's
documentation [Contributing to projects](https://docs.github.com/en/get-started/quickstart/contributing-to-projects).

### Code reviews

All submissions need to be reviewed by at least one parent committer before being merged.
[GitHub Pull Request Review Process](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/about-pull-request-reviews)
is followed for every pull request.

### Coding Guidelines

- Commits should be atomic and semantic. Please properly squash your pull requests before submitting them. Fixup commits
  can be used temporarily during the review process but things should be squashed at the end to have meaningful commits.
- Git authorship (i.e. git `user.name` and `user.email`) must be properly set.
- Documentation (reference documentation, comments...) is not optional.

## Security

parent's dependencies are kept up-to-date using [Dependabot](https://docs.github.com/en/code-security/dependabot).
