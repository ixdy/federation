load("@io_bazel_rules_go//go:def.bzl", "go_library")

go_library(
    name = "go_default_library",
    srcs = ["sdk.go"],
    importpath = "github.com/aws/aws-sdk-go",
    visibility = ["//visibility:public"],
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [
        ":package-srcs",
        "//vendor/github.com/aws/aws-sdk-go/aws:all-srcs",
        "//vendor/github.com/aws/aws-sdk-go/awstesting:all-srcs",
        "//vendor/github.com/aws/aws-sdk-go/example/service/s3/putObjectAcl:all-srcs",
        "//vendor/github.com/aws/aws-sdk-go/example/service/sqs/mockingClientsForTests:all-srcs",
        "//vendor/github.com/aws/aws-sdk-go/models/endpoints:all-srcs",
        "//vendor/github.com/aws/aws-sdk-go/private/protocol:all-srcs",
        "//vendor/github.com/aws/aws-sdk-go/private/signer/v2:all-srcs",
        "//vendor/github.com/aws/aws-sdk-go/private/util:all-srcs",
        "//vendor/github.com/aws/aws-sdk-go/private/waiter:all-srcs",
        "//vendor/github.com/aws/aws-sdk-go/service:all-srcs",
    ],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
