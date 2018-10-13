workspace(name = "rules_nodejs_rollup_commonjs_bundle")

# git_repository(
#     name = "build_bazel_rules_nodejs",
#     remote = "https://github.com/bazelbuild/rules_nodejs.git",
#     tag = "0.15.0",
# )

local_repository(
    name = "build_bazel_rules_nodejs",
    path = "../wayou_rules_nodejs",
)

load("@build_bazel_rules_nodejs//:package.bzl", "rules_nodejs_dependencies")
rules_nodejs_dependencies()

load("@build_bazel_rules_nodejs//:defs.bzl", "node_repositories")
node_repositories(package_json = ["//:package.json"])

load("@build_bazel_rules_nodejs//:defs.bzl", "yarn_install")
yarn_install(
    name = "npm",
    package_json = "//:package.json",
    yarn_lock = "//:yarn.lock",
)
