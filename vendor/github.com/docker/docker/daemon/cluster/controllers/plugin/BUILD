load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = ["controller.go"],
    importpath = "github.com/docker/docker/daemon/cluster/controllers/plugin",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/docker/distribution/reference:go_default_library",
        "//vendor/github.com/docker/docker/api/types:go_default_library",
        "//vendor/github.com/docker/docker/api/types/swarm/runtime:go_default_library",
        "//vendor/github.com/docker/docker/plugin:go_default_library",
        "//vendor/github.com/docker/docker/plugin/v2:go_default_library",
        "//vendor/github.com/docker/swarmkit/api:go_default_library",
        "//vendor/github.com/gogo/protobuf/proto:go_default_library",
        "//vendor/github.com/pkg/errors:go_default_library",
        "//vendor/github.com/sirupsen/logrus:go_default_library",
        "//vendor/golang.org/x/net/context:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = ["controller_test.go"],
    importpath = "github.com/docker/docker/daemon/cluster/controllers/plugin",
    library = ":go_default_library",
    deps = [
        "//vendor/github.com/docker/distribution/reference:go_default_library",
        "//vendor/github.com/docker/docker/api/types:go_default_library",
        "//vendor/github.com/docker/docker/api/types/swarm/runtime:go_default_library",
        "//vendor/github.com/docker/docker/pkg/pubsub:go_default_library",
        "//vendor/github.com/docker/docker/plugin:go_default_library",
        "//vendor/github.com/docker/docker/plugin/v2:go_default_library",
        "//vendor/github.com/sirupsen/logrus:go_default_library",
        "//vendor/golang.org/x/net/context:go_default_library",
    ],
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
