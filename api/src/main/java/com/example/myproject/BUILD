java_library(
    name = "lib",
    srcs = glob(["*.java"]),
    visibility = ["//api/src/test:__subpackages__"],
    deps = [
        "@maven//:org_springframework_boot_spring_boot",
        "@maven//:org_springframework_boot_spring_boot_autoconfigure",
        "@maven//:org_springframework_boot_spring_boot_starter_web",
        "@maven//:org_springframework_spring_context",
        "@maven//:org_springframework_spring_web",
        "//lib/src/main/java/com/example/demo:calculator"
    ],
)

java_binary(
    name = "app",
    main_class = "com.example.myproject.Application",
    runtime_deps = [
        ":lib",
    ],
)
