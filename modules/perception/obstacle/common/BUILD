load("//tools:cpplint.bzl", "cpplint")

package(default_visibility = ["//visibility:public"])

cc_library(
    name = "common",
    srcs = [
        "hungarian_bigraph_matcher.cc",
        "object_sequence.cc",
        "pose_util.cc",
    ],
    hdrs = [
        "convex_hullxy.h",
        "hungarian_bigraph_matcher.h",
        "object_sequence.h",
        "pose_util.h",
    ],
    linkopts = [
        "-lqhull",
    ],
    deps = [
        "//modules/common:log",
        "//modules/perception/common:pcl_util",
        "//modules/perception/lib/base",
        "//modules/perception/obstacle/base",
        "@eigen",
        "@opencv2//:core",
        "@yaml_cpp//:yaml",
    ],
)

cc_test(
    name = "common_test",
    size = "small",
    srcs = [
        "convex_hullxy_test.cc",
        "hungarian_bigraph_matcher_test.cc",
        "object_sequence_test.cc",
        "pose_util_test.cc",
    ],
    data = [
        "//modules/perception:perception_data",
    ],
    deps = [
        ":common",
        "//modules/perception/obstacle/lidar/object_builder/min_box",
        "@gtest//:main",
    ],
)

cpplint()
