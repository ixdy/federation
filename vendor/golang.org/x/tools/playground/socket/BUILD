load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = ["socket.go"],
    importpath = "golang.org/x/tools/playground/socket",
    visibility = ["//visibility:public"],
    deps = ["//vendor/golang.org/x/net/websocket:go_default_library"],
)

go_test(
    name = "go_default_test",
    srcs = ["socket_test.go"],
    importpath = "golang.org/x/tools/playground/socket",
    library = ":go_default_library",
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [":package-srcs"],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
