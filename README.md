# Reusable Workflows

Reusable GitHub Actions workflows that can be shared between projects -- by me or by anyone.

## Java / Maven Matrix Build

[This is](.github/workflows/matrix-maven) a simple Java/Maven build workflow.

Uses a matrix build strategy to build by default in:
    - all LTS versions of Java (8, 11)
    - two distros: zulu, temurin

You can override the java versions or java distros with workflow inputs (`java-versions`, `java-distros`). At the moment, the inputs cannot be an array type, so it's a JSON-encoded string. If, for instance, you wanted to build in Java 11 and 16, you could specify an input:

```
  java-versions: "[ \"11\", \"16\" ]"
```

This workflow uses a Maven cache on `setup-java` and [dorny/test-reporter](https://github.com/dorny/test-reporter) for JUnit test reports.
