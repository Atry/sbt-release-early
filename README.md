# Meet `sbt-release-early`

`sbt-release-early` is an sbt plugin to help you follow the maxim
`"Release early, release often"`. The major goal is to provide out-of-the-box
support for automatic releases.

## Use

Not ready yet. Coming soon.

## Requirements

If you want to use `sbt-release-early`, you need to:
  
* Use git and have it in the `PATH`.
* Have a [Bintray](https://github.com/sbt/sbt-bintray) account.
 
To synchronize your artifacts with Maven Central, you need a [Sonatype](https://www.sonatype.com/)
account. This feature is optional, but enabled by default for releases via tag.

## In a nutshell

Every time you *push a commit* to a branch, `sbt-release-early` will release an
artifact with a version derived from the git metadata (version and distance from
last git tag). For example, `0.3.0+10-4f489199`, where `10` is the distance
and the suffix is the commit hash.

Every time you *push a tag* to a branch, `sbt-release-early` will release an
artifact with the version you've specified, usually a "final" version. For example, `v0.1.0`.

### Version schema

Any version that is not final is considered a snapshot even if it has a stable
number and lacks the `-SNAPSHOT` suffix. For example, `0.3+10-4f489199` is a
snapshot. In short, a snapshot version is *a snapshot* of your codebase at any
time.

Every time you push a commit to a branch, 


## Motivation

`sbt-release-early` takes a distinct approach to releases.

While some projects decide to include the versions in sbt files, `sbt-release-early`
derives the versions of your project from your git tags. This has several benefits:

1. Tag uniqueness. Git prevents you from trying to release a version twice.
2. Both you and the CI don't need to push commits just to bump up versions.

These two and the automatic derivation of version reduce substantially the complexity
of handling releases.

