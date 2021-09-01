# Release process for TMT software repositories

This is a procedure for release of all TMT repositories. Each repository has it's own `RELEASING.md` file checked in
which states releasing procedure for that particular repository in detail.

## Repositories

Release TMT software repositories in following order because of interdependency between repos. So after
release, version in dependent repos need to be updated.
For example,
After release of msocket, update msocket version in csw before releasing csw.

1. msocket
1. embedded-keycloak
1. sbt-docs
1. kotlin-plugin
1. rtm
1. CSW
1. pycsw
1. csw-c
1. csw.g8
1. ESW
1. ESW-backend-template.g8
1. esw-ts
1. esw-ui-template.g8
1. sequencer-scripts
1. esw-ocs-eng-ui

## Release process for all above repos

1. Upgrade third party repo versions. (libs + plugins)
1. Check for unused library dependencies if any.
1. Check `release.yml` for any modifications needed.
1. Update `Releasing.md` if any new release step is added for each repo.

## Guidelines for release

1. Dev pipeline is green.
1. Tagging of repository is done using `release.sh` checked in inside each repository.
1. Follow semantic versioning scheme. major.minor.patch version. Each tag version is prefixed with `v`.
1. For repos which don't have any changes, we can skip release for those repositories and use previously released version.

## Upgrade third party repo versions. (libs + plugins)

If a third party lib/ plugin has milestone release after latest stable / rc releases. Correct default is to pick latest stable version of it.

For ex: A library has

- Latest Milestone Version : 7.4.0-M4
- **Latest Stable Version : 7.3.2**       <= will be picked in the next release

## After release 

- Update the version of repos in [osw-dev](https://github.com/tmtsoftware/osw-dev) repo. e.g., esw, csw versions etc.
