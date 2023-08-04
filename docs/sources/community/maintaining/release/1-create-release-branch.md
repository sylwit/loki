# Create Release Branch

A single release branch is created for every `MAJOR.MINOR` release. That release branch is then used for all the Stable Release and all Patch Releases for that `MAJOR.MINOR` version of the Loki.

## Before you begin

1. Determine the [VERSION_PREFIX](concepts/version.md)

## Steps

1. Determine which commit should be used as a base for the release branch:

	This is usually some weekly `kXXX` release branches that we think stable enough to make it base commit for Loki public release.

	- Examples:
		- [k161 branch](https://github.com/grafana/loki/tree/k161)

1. Create and push the release branch from the selected base commit:

	The name of the release branch should be `release-VERSION_PREFIX` defined above, such as `release-v2.9`.

	**NOTES**:
	1. Branches are only made for VERSION_PREFIX; do not create branches for the full VERSION such as `release-v2.9.1`.

	1. Do not create any other branches that are prefixed with `release` when creating PRs or those branches will conflict with our automated release build publish workflows.
