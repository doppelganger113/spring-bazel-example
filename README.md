# Spring boot monorepo with Bazel

Sample of using [Bazel](https://docs.bazel.build/versions/3.7.0/getting-started.html) with multiple Spring boot projects 
inside a monorepo. Focus is on Bazel v4 as it is the first LTS version.

# Setup
 - Install Java and set `JAVA_HOME` environment variable to your Java sdk
   - OS X
        ```bash
        export JAVA_HOME=/Library/Java/JavaVirtualMachines/adoptopenjdk-14.jdk/Contents/Home/
        ```

# Commands
 - Build: `bazel build '...'`
 - Run: `bazel run //api/src/main/java/com/example/myproject:app`
 - Test all: `bazel test //...`
 - Clean/purge: `bazel clean --expunge`

## 
