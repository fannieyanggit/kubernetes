package(default_visibility = ["//visibility:public"])

load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_test(
    name = "go_default_test",
    size = "large",
    srcs = [
        "ipam_test.go",
        "main_test.go",
    ],
    embed = [":go_default_library"],
    tags = ["integration"],
    deps = [
        "//pkg/api/testapi:go_default_library",
        "//pkg/controller/nodeipam:go_default_library",
        "//pkg/controller/nodeipam/ipam:go_default_library",
        "//test/integration/framework:go_default_library",
        "//test/integration/util:go_default_library",
        "//vendor/github.com/golang/glog:go_default_library",
        "//vendor/k8s.io/api/core/v1:go_default_library",
        "//vendor/k8s.io/client-go/informers:go_default_library",
        "//vendor/k8s.io/client-go/kubernetes:go_default_library",
        "//vendor/k8s.io/client-go/rest:go_default_library",
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

go_library(
    name = "go_default_library",
    srcs = [
        "cloud.go",
        "results.go",
        "util.go",
    ],
    importpath = "k8s.io/kubernetes/test/integration/ipamperf",
    deps = [
        "//pkg/api/testapi:go_default_library",
        "//pkg/cloudprovider:go_default_library",
        "//pkg/cloudprovider/providers/gce/cloud:go_default_library",
        "//pkg/cloudprovider/providers/gce/cloud/meta:go_default_library",
        "//pkg/controller/nodeipam/ipam:go_default_library",
        "//pkg/controller/nodeipam/ipam/cidrset:go_default_library",
        "//pkg/controller/util/node:go_default_library",
        "//test/integration/util:go_default_library",
        "//vendor/github.com/golang/glog:go_default_library",
        "//vendor/google.golang.org/api/compute/v0.beta:go_default_library",
        "//vendor/google.golang.org/api/compute/v1:go_default_library",
        "//vendor/k8s.io/api/core/v1:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/api/resource:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/apis/meta/v1:go_default_library",
        "//vendor/k8s.io/client-go/informers:go_default_library",
        "//vendor/k8s.io/client-go/kubernetes:go_default_library",
        "//vendor/k8s.io/client-go/rest:go_default_library",
        "//vendor/k8s.io/client-go/tools/cache:go_default_library",
    ],
)
