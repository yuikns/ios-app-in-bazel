package(default_visibility = ["//visibility:public"])

licenses(["notice"])

load("@build_bazel_rules_apple//apple:ios.bzl", "ios_application")
load(
    "@build_bazel_rules_apple//apple:versioning.bzl",
    "apple_bundle_version",
)

objc_library(
    name = "Sources",
    srcs = [
        "Sources/AppDelegate.h",
        "Sources/AppDelegate.m",
        "Sources/main.m",
    ],
    resources = [
        "Resources/Main.storyboard",
    ],
)

apple_bundle_version(
    name = "HelloWorldVersion",
    build_version = "1.0",
)

ios_application(
    name = "HelloWorld",
    app_icons = ["//examples/resources:PhoneAppIcon.xcassets"],
    bundle_id = "com.example.hello-world",
    families = [
        "iphone",
        "ipad",
    ],
    infoplists = [":Info.plist"],
    launch_storyboard = "//examples/resources:Launch.storyboard",
    minimum_os_version = "8.0",
    version = ":HelloWorldVersion",
    deps = [":Sources"],
)
