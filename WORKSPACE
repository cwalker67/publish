load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")


RULES_JVM_EXTERNAL_TAG = "3.0"
RULES_JVM_EXTERNAL_SHA = "62133c125bf4109dfd9d2af64830208356ce4ef8b165a6ef15bbff7460b35c3a"


git_repository(
    name = "graknlabs_bazel_distribution",
    remote = "https://github.com/graknlabs/bazel-distribution",
    commit = "dddcd93b067a6b6052baead477cd0b241b4a33ca" # sync-marker: do not remove this comment, this is used for sync-dependencies by @graknlabs_bazel_distribution
)

git_repository(
        name = "graknlabs_build_tools",
        remote = "https://github.com/cwalker67/build-tools",
        commit = "c8a10c594d1aebf34103294e7fb72fc1c371a4b3" # sync-marker: do not remove this comment, this is used for sync-dependencies by @graknlabs_bazel_distribution
)

http_archive(
    name = "rules_jvm_external",
    strip_prefix = "rules_jvm_external-%s" % RULES_JVM_EXTERNAL_TAG,
    sha256 = RULES_JVM_EXTERNAL_SHA,
    url = "https://github.com/bazelbuild/rules_jvm_external/archive/%s.zip" % RULES_JVM_EXTERNAL_TAG,
)

load("@rules_jvm_external//:defs.bzl", "maven_install")

maven_install(
    artifacts = [
        "commons-lang:commons-lang:2.6",
    ],
    repositories = [
        "https://jcenter.bintray.com",
    ]
)


BAZEL_SKYLIB_TAG = "0.8.0"

http_archive(
    name = "bazel_skylib",
    strip_prefix = "bazel-skylib-%s" % BAZEL_SKYLIB_TAG,
    url = "https://github.com/bazelbuild/bazel-skylib/archive/%s.tar.gz" %
          BAZEL_SKYLIB_TAG,
)