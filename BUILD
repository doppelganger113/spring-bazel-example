alias(
    name = "jdk",
    actual = select(
        {
            "@bazel_tools//src/conditions:darwin": "@jdk8_macos//:jdk",
            "@bazel_tools//src/conditions:darwin_x86_64": "@jdk8_macos//:jdk",
            "@bazel_tools//src/conditions:linux_x86_64": "@jdk8_linux//:jdk",
            "@bazel_tools//src/conditions:windows": "@jdk8_windows//:jdk",
        },
        no_match_error = "Could not find a JDK for host execution environment, please explicitly" +
                         " provide one using `--host_javabase.`",
    ),
    visibility = ["//visibility:public"],
)