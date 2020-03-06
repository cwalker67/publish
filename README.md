## Publishing

### Setup
```
export DEPLOY_MAVEN_USERNAME=username
export DEPLOY_MAVEN_PASSWORD=password
```

### snapshots
```
bazel run --define version=$(cat VERSION) //:deploy-maven -- snapshot
```

### release
```
bazel run --define version=$(cat VERSION) //:deploy-maven -- release
```