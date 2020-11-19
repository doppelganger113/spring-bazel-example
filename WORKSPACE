workspace(name = "java_dependencies")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# "New" Java support

http_archive(
    name = "rules_java",
    sha256 = "220b87d8cfabd22d1c6d8e3cdb4249abd4c93dcc152e0667db061fb1b957ee68",
    url = "https://github.com/bazelbuild/rules_java/releases/download/0.1.1/rules_java-0.1.1.tar.gz",
)

load("@rules_java//java:repositories.bzl", "rules_java_dependencies", "rules_java_toolchains")

rules_java_dependencies()

rules_java_toolchains()

# Download JDKs

http_archive(
    name = "jdk8_linux",
    build_file = "@local_jdk//:BUILD.bazel",
    sha256 = "568e7578f1b20b1e62a8ed2c374bad4eb0e75d221323ccfa6ba8d7bc56cf33cf",
    strip_prefix = "zulu8.38.0.13-ca-jdk8.0.212-linux_x64",
    urls = [
        "https://cdn.azul.com/zulu/bin/zulu8.38.0.13-ca-jdk8.0.212-linux_x64.tar.gz",
    ],
)

http_archive(
    name = "jdk8_macos",
    build_file = "@local_jdk//:BUILD.bazel",
    sha256 = "64538f3eed34a298cc48168e89326fd323a55d801a3e6b2c3cc948effe124250",
    strip_prefix = "zulu8.38.0.13-ca-jdk8.0.212-macosx_x64",
    urls = [
        "https://cdn.azul.com/zulu/bin/zulu8.38.0.13-ca-jdk8.0.212-macosx_x64.tar.gz",
    ],
)

http_archive(
    name = "jdk8_windows",
    build_file = "@local_jdk//:BUILD.bazel",
    sha256 = "f5367fc29485252e91d3d1d28b069277b7133dfa2e104fc181af4373267d3a82",
    strip_prefix = "zulu8.38.0.13-ca-jdk8.0.212-win_x64",
    urls = [
        "https://cdn.azul.com/zulu/bin/zulu8.38.0.13-ca-jdk8.0.212-win_x64.zip",
    ],
)

# Official Bazel tools to get Maven repo dependencies; there are other
# unofficial tools also.

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

RULES_JVM_EXTERNAL_TAG = "3.3"
RULES_JVM_EXTERNAL_SHA = "d85951a92c0908c80bd8551002d66cb23c3434409c814179c0ff026b53544dab"

http_archive(
    name = "rules_jvm_external",
    strip_prefix = "rules_jvm_external-%s" % RULES_JVM_EXTERNAL_TAG,
    sha256 = RULES_JVM_EXTERNAL_SHA,
    url = "https://github.com/bazelbuild/rules_jvm_external/archive/%s.zip" % RULES_JVM_EXTERNAL_TAG,
)

load("@rules_jvm_external//:defs.bzl", "maven_install")

maven_install(
    artifacts = [
        "junit:junit:4.12",
        "org.hamcrest:hamcrest-library:1.3",
        "org.springframework.boot:spring-boot-autoconfigure:2.1.3.RELEASE",
        "org.springframework.boot:spring-boot-test-autoconfigure:2.1.3.RELEASE",
        "org.springframework.boot:spring-boot-test:2.1.3.RELEASE",
        "org.springframework.boot:spring-boot:2.1.3.RELEASE",
        "org.springframework.boot:spring-boot-starter-web:2.1.3.RELEASE",
        "org.springframework:spring-beans:5.1.5.RELEASE",
        "org.springframework:spring-context:5.1.5.RELEASE",
        "org.springframework:spring-test:5.1.5.RELEASE",
        "org.springframework:spring-web:5.1.5.RELEASE",
    ],
    repositories = [
        # Private repositories are supported through HTTP Basic auth
        "http://username:password@localhost:8081/artifactory/my-repository",
        "https://jcenter.bintray.com/",
        "https://maven.google.com",
        "https://repo1.maven.org/maven2",
    ],
    fetch_sources = True,
)

# Pinning is both safer (like an NPM package-lock) and avoids
# the spurious use of an OS-installed JVM.

load("@maven//:defs.bzl", "pinned_maven_install")

pinned_maven_install(
    # name = "maven",
)

# bazel run @maven//:pin
# bazel run @unpinned_maven//:pin

# <groupId>com.google.guava</groupId>
# <artifactId>guava</artifactId>
# <version>28.1-jre</version>