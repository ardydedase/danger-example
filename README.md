## Installation

Install danger using npm.
```
npm install
```

Set your GitHub token env variable.
```
export DANGER_GITHUB_API_TOKEN=<yourtoken>
```

## Test using danger-js 
This will NOT comment on the PR
```
export DANGER_MANUAL_CI=MyCI
node_modules/danger/distribution/commands/danger-pr.js https://github.com/danger/danger-js/pull/1192
```

## Test using danger-ci
This will comment on the PR

```
export DANGER_MANUAL_CI=MyCI
export DANGER_MANUAL_GH_REPO=ardydedase/danger-example
DANGER_MANUAL_PR_NUM=1 node_modules/danger/distribution/commands/danger-ci.js
```
Update the GitHub token with your own in `cloudbuild-local.yaml`.

## Test with cloudbuild-local

Install CloudBuild local builder:
- https://cloud.google.com/sdk/docs/install-sdk
- https://cloud.google.com/build/docs/build-debug-locally#install_the_local_builder

Run the command:
```
cloud-build-local --config=./cloudbuild-local.yaml .
```