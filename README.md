### Problem

A dependency is defined with a version catalog, a classifier set to the dependency is discarded in Gradle 7.6
if it is copy to another dependency configuration.
This problem happens only in Gradle 7.6 and 7.5.x copies classifiers to other dependency configurations.

### Example

If you execute the following command, you can see different results depending on the Gradle version.
```
./gradlew copyAndPrintDependencies
```

- In Gradle 7.5.1, all classifiers are preserved.
```
.../netty-tcnative-boringssl-static-2.0.54.Final-linux-x86_64.jar
.../netty-tcnative-boringssl-static-2.0.54.Final-windows-x86_64.jar
.../netty-tcnative-classes-2.0.54.Final.jar
``` 

- In Gradle 7.6, `windows-x86_64` classifier is discarded.
```
.../netty-tcnative-boringssl-static-2.0.54.Final-linux-x86_64.jar
.../netty-tcnative-boringssl-static-2.0.54.Final.jar
.../netty-tcnative-classes-2.0.54.Final.jar
```
