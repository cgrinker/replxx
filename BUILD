cc_library(
    name="replxx",
    visibility = ["//visibility:public"],
    hdrs=glob([
        "include/**/*.h*",
    ]),
    srcs=glob([
        "src/**/*.h*",
        "src/**/*.c*"
    ]),
    includes=[
        "src",
        "include",
    ],
    copts = select({
        "@bazel_tools//src/conditions:windows": ["/std:c++17"],
        "//conditions:default": ["-std=c++17"],
    }),
    defines=[
        "REPLXX_STATIC"
    ],
)

cc_binary(
    name = "capi",
    srcs = [
        "examples/c-api.c",
        "examples/util.c",
        "examples/util.h"
    ],
    deps = [
        ":replxx",
    ],
    copts = select({
        "@bazel_tools//src/conditions:windows": ["/std:c++17"],
        "//conditions:default": ["-std=c++17"],
    }),
)

cc_binary(
    name = "cxxapi",
    srcs = [
        "examples/cxx-api.cxx",
        "examples/util.c",
        "examples/util.h"
    ],
    deps = [
        ":replxx",
    ],
    copts = select({
        "@bazel_tools//src/conditions:windows": ["/std:c++17"],
        "//conditions:default": ["-std=c++17"],
    }),
)