# 34786

Reproduction for [Renovate discussion 34786](https://github.com/renovatebot/renovate/discussions/34786).


## Current behavior

This repo contains a Dockerfile with dependency on image with tag versioning like:
```
FROM ghcr.io/atanev/minimal-reproduction-template:2025.02.14-1
```

Also a `Chart.yaml` file with a dependecy chart using the same versioning:

```
dependencies:
  - name: parent-chart
    version: 2025.02.14-1
```
Both are using versioning based on `YYYY.MM.DD-buildID`.

In the reproduction scenario I have published the same artifacts with version like `YYYY.MM.DD-buildID` also with semver `0.0.1` and `0.0.2`
When I switch the versions in the Dockerfile/Chart.yaml to the semver format right away I get the PRs for both, but when I have like this it does not work.


## Expected behavior

I would like to receive PRs for versioning following the `YYYY.MM.DD-buildID` increments.