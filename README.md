# Spring boot monorepo with Bazel

Sample of using Bazel with multiple Spring boot projects inside a monorepo.

# Commands
 - Build: `bazel build '...'`
 - Run: `bazel run //api/src/main/java/com/example/myproject:app`
 - Clean: `bazel clean --expunge`