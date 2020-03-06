
java_library(
    name = "lib",
    srcs = glob(["src/main/java/**/*.java"]),
    deps = [
        "@maven//:commons_lang_commons_lang",
    ],
    tags = ["maven_coordinates=com.test:lib:{pom_version}"]
)


load("@graknlabs_build_tools//distribution/maven:rules.bzl", "assemble_maven", "deploy_maven")

assemble_maven(
    name = "assemble-maven",
    target = ":lib",
    package = "java"
)

deploy_maven(
    name = "deploy-maven",
    target = ":assemble-maven",
    deployment_properties = "//:repo.properties"
)