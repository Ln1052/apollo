load("//tools:cpplint.bzl", "cpplint")

package(default_visibility = ["//visibility:public"])

cc_inc_library(
    name = "hw_chk_utils",
    hdrs = [
        "hw_chk_utils.h",
    ],
    deps = [
        "//modules/monitor/common:hw_checker",
    ],
)

cc_binary(
    name = "can_check",
    srcs = [
        "can_check.cc",
    ],
    deps = [
        ":hw_chk_utils",
        "//external:gflags",
        "//modules/hmi/utils:hmi_status_helper",
        "//modules/monitor/common:can_checker_factory",
        "//modules/canbus/proto:canbus_proto",
        "//modules/canbus/common:canbus_common",
        "//modules/common/util:util",
    ],
)

cc_binary(
    name = "gps_check",
    srcs = [
        "gps_check.cc",
    ],
    deps = [
        ":hw_chk_utils",
        "//external:gflags",
        "//modules/common:log",
        "//modules/common/proto:gnss_status_proto",
        "//modules/hmi/utils:hmi_status_helper",
        "@ros//:ros_common",
    ],
)

cc_binary(
    name = "mock_can_check",
    srcs = [
        "can_check.cc",
    ],
    defines = ["DEBUG"],
    deps = [
        ":hw_chk_utils",
        "//external:gflags",
        "//modules/hmi/utils:hmi_status_helper",
        "//modules/monitor/common:can_checker_factory",
        "//modules/canbus/proto:canbus_proto",
        "//modules/canbus/common:canbus_common",
        "//modules/common/util:util",
    ],
)

cpplint()
