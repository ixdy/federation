load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "ea.go",
        "reparse.go",
        "syscall.go",
    ] + select({
        "@io_bazel_rules_go//go/platform:windows_amd64": [
            "backup.go",
            "file.go",
            "fileinfo.go",
            "pipe.go",
            "privilege.go",
            "sd.go",
            "zsyscall_windows.go",
        ],
        "//conditions:default": [],
    }),
    importpath = "github.com/Microsoft/go-winio",
    visibility = ["//visibility:public"],
    deps = select({
        "@io_bazel_rules_go//go/platform:windows_amd64": [
            "//vendor/golang.org/x/sys/windows:go_default_library",
        ],
        "//conditions:default": [],
    }),
)

go_test(
    name = "go_default_test",
    srcs = [
        "backup_test.go",
        "ea_test.go",
        "pipe_test.go",
        "privileges_test.go",
        "sd_test.go",
    ],
    importpath = "github.com/Microsoft/go-winio",
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
    srcs = [
        ":package-srcs",
        "//vendor/github.com/Microsoft/go-winio/archive/tar:all-srcs",
        "//vendor/github.com/Microsoft/go-winio/backuptar:all-srcs",
        "//vendor/github.com/Microsoft/go-winio/vhd:all-srcs",
        "//vendor/github.com/Microsoft/go-winio/wim:all-srcs",
    ],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
