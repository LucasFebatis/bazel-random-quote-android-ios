load("@build_bazel_rules_apple//apple:ios.bzl", "ios_application", "ios_unit_test")
load("@build_bazel_rules_swift//swift:swift.bzl", "swift_library")
load(
    "@rules_xcodeproj//xcodeproj:defs.bzl",
    "top_level_target",
    "xcodeproj",
)

swift_library(
    name = "tests",
    srcs = glob(["RandomQuoteTests/*.swift"]),
    visibility = ["//visibility:private"],
    deps = [":sources"],
    module_name = "RandomQuoteTests"
)

swift_library(
    name = "sources",
    srcs = glob(["RandomQuote/Sources/*.swift"]),
    visibility = ["//visibility:private"],
    module_name = "RandomQuote"
)

ios_unit_test(
    name = "iostests",
    deps = [":tests"],
    minimum_os_version = "14.0",
    test_host = ":iosapp",
    platform_type = "ios",
    visibility = ["//visibility:public"]
)

ios_application(
    name = "iosapp",
    deps = [":sources"],
    bundle_id = "com.febatis.randomquote",
    families = [
        "iphone",
        "ipad"
    ],
    infoplists = ["RandomQuote/App/Info.plist"],
    resources = glob(["RandomQuote/App/Assets.xcassets/**"]),
    minimum_os_version = "14.0",
    visibility = ["//visibility:public"]
)

# xcodeproj(
#     name = "xcodeproj",
#     project_name = "RandomQuote",
#     targets = [":iosapp"]
# )

xcodeproj(
    name = "xcodeproj",
    build_mode = "bazel",
    project_name = "RandomQuote",
    tags = ["manual"],
    top_level_targets = [
        ":iosapp",
    ],
)