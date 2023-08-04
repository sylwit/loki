# Backport PRs and Commits

Any PRs and commits not on the release branch need to be cherry-picked over to it.

## Before you begin

If the release branch already has all the code changes on it, skip this step.

## Steps

1. Backport PR(s) that are not in release branch into it by adding label `backport <release-branch>` label to the PR.

	- For example, [this PR](https://github.com/grafana/loki/pull/9757) is backported to release v2.8 branch.
	- Sometimes backport may fail due to merge conflicts or incompatible changes. In those cases, backport it manually by following commands that are commented by `grafanabot` in the same PR. For example, [this PR](https://github.com/grafana/loki/pull/9951) backported manually.

	Usually backporting PR(s) is enough to get all the code changes into release branch.

	But sometimes you may have to randomly pick specific commits into the release branch. Follow the below step to do that.

	**IMPORTANT** When you cherry pick commits, make sure those are always from `main` branch assuming it's already reviewed properly by peers.

2. Create PR(s) to cherry-pick additional commits into release branch as needed from main

	```
	git cherry-pick -x COMMIT_SHA
	```

	If there are several commits to cherry-pick, consider using one branch to cherry-pick to and ask reviewers to review commit-by-commit
