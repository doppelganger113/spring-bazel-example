# Spring boot monorepo with Bazel

Sample of using [Bazel](https://docs.bazel.build/versions/3.7.0/getting-started.html) with multiple Spring boot projects 
inside a monorepo. Focus is on Bazel v4 as it is the first LTS version.

# Requirements
 - **InteliJ** version **2020.2.4** and **Bazel plugin** so that InteliJ can properly map dependencies
 - Appropriate version of Java installed (8 or larger)
 - [Bazelisk](https://github.com/bazelbuild/bazelisk) wrapper for user-friendly commands

# Setup
 - Install Java and set `JAVA_HOME` environment variable to your Java sdk
   - OS X
        ```bash
        export JAVA_HOME=/Library/Java/JavaVirtualMachines/adoptopenjdk-14.jdk/Contents/Home/
        ```

# Commands
 - Build
    ```bash
    bazelisk build '...' 
    ```
 - Run myproject app
    ```bash
    bazelisk run //api/src/main/java/com/example/myproject:app
    ``` 
 - Test all
    ```bash
    bazelisk test //... 
    ```
 - Clean/purge
    ```bash
    bazelisk clean --expunge 
    ```
