# Repro for AGP transform failure

## Steps:
```
./gradlew :samples:SupportPreferenceDemos:mergeExtDexDebug
```

## Expected

Success

## Actual

Failure with:
```
FAILURE: Build failed with an exception.

* What went wrong:
Execution failed for task ':samples:SupportPreferenceDemos:mergeExtDexDebug'.
> Could not resolve all files for configuration ':samples:SupportPreferenceDemos:debugRuntimeClasspath'.
   > Failed to transform lifecycle-common-2.4.0-rc01.jar (androidx.lifecycle:lifecycle-common:2.4.0-rc01) to match attributes {artifactType=android-dex, asm-transformed-variant=NONE, dexing-enable-desugaring=true, dexing-is-debuggable=true, dexing-min-sdk=1, org.gradle.category=library, org.gradle.dependency.bundling=external, org.gradle.jvm.version=8, org.gradle.libraryelements=jar, org.gradle.status=release, org.gradle.usage=java-runtime}.
      > Could not resolve all files for configuration ':samples:SupportPreferenceDemos:debugRuntimeClasspath'.
         > Failed to transform annotation.jar (project :annotation:annotation) to match attributes {artifactType=android-classes-jar, org.gradle.category=library, org.gradle.dependency.bundling=external, org.gradle.jvm.version=11, org.gradle.libraryelements=jar, org.gradle.usage=java-runtime}.
            > Execution failed for IdentityTransform: /ssd/ssd1/temp/ProjectSwapTransform/annotation/annotation/build/libs/annotation-1.6.0.jar.
               > File/directory does not exist: /ssd/ssd1/temp/ProjectSwapTransform/annotation/annotation/build/libs/annotation-1.6.0.jar

* Try:
> Run with --stacktrace option to get the stack trace.
> Run with --info or --debug option to get more log output.
> Run with --scan to get full insights.

* Get more help at https://help.gradle.org

BUILD FAILED in 1s

```
