# Example repo to showcase issue with symplify/monorepo-builder when replacing a legacy buildscript.

Issue: `symplify/monorepo-builder` will error out when it encounters non semver tags during a release process.

```
> monorepo-builder release 1.0

In Version.php line 141:

  Version string 'release-2021-09-01' does not follow SemVer semantics


release [--dry-run] [--stage STAGE] [-c|--config CONFIG] [--] <version>

Script monorepo-builder release 1.0 handling the try-v1-release event returned with error code 1
```

This repo has been built to demonstrate this issue, to do so:

1. Clone the repo
2. Ensure tags were also cloned (`git tag`)
3. Run `composer install` to install monorepo-builder and deps.
4. Run `composer try-v1-release` to simulate a 1.0.0 release under monorepo.