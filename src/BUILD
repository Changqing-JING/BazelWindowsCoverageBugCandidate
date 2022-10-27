
opt=["-std=c++14"]

cc_library(
    name = "lib1",
    srcs = ["lib1.cpp"],
    hdrs = ["lib1.hpp"]
)

cc_binary(
    name = "BazelLearn",
    srcs = ["main.cpp"],
    copts = opt
)


cc_test(
    name = "test_lib1",
    size = "small",
    srcs = ["test.cpp"],
    tags = ["unit"],
    deps = [
        "@googletest//:gtest_main",
        ":lib1"
    ],
)
