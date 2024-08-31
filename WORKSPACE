# simple setup

# create a variable
build_name = "RandomQuotes"

# print to the console
print(build_name)


load("functions.blz", "get_project_policy")

print(get_project_policy(build_name))

# rules for building Random Quotes for iOS

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "build_bazel_rules_swift",
    sha2 = "a2fd565e527f83fb3f9eb07eb9737240e668c9242d3bc318712efa54a7deda97",
    url = "https://github.com/bazelbuild/rules_swift/releases/download/0.27.0/rules_swift.0.27.0.tar.gz",
)

load(
    "@build_bazel_rules_swift//swift:repositories.bzl",
    "swift_rules_dependencies"
)

swift_rules_dependencies()


load(
    "@build_bazel_rules_swift//swift:extras.bzl",
    "swift_rules_extras_dependencies"
)

swift_rules_extras_dependencies()

http_archive(
    name = "build_bazel_rules_apple",
    sha2 = "a5f00fd89eff67291f6cd3efdc8fad30f4727e6ebb90718f3f05bbf3c3dd5ed7",
    url = "https://github.com/bazelbuild/rules_apple/releases/download/0.33.0/rules_apple.0.33.0.tar.gz"
)

load(
    "@build_bazel_rules_apple//apple:repositories.bzl",
    "apple_rules_dependencies"
)

apple_rules_dependencies()