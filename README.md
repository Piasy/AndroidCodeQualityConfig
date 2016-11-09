# AndroidCodeQualityConfig

Code quality config for android project, including lint, pmd, findbugs, checkstyle, jacoco code coverage. Serve as a submodule for repo: https://github.com/Piasy/AndroidTDDBootStrap

+  Usage
  +  step 1. fork me
  +  step 2. import the forked repo as git submodule, or just put the folder under your project root.
  +  step 3. `apply from: '../AndroidCodeQualityConfig/quality.gradle'` for android module then run `gradle check`
  +  step 4. no more step 4 :).

If you have many modules, you can add below code into your root project's `build.gradle` and skip step 3:

``` gradle
subprojects {
    apply from: "$rootProject.projectDir/AndroidCodeQualityConfig/quality.gradle"

    afterEvaluate {
        check.dependsOn 'checkstyle', 'findbugs', 'pmd', 'lint'
   }
}
```

Notice: You should first remove check.dependsOn 'checkstyle', 'findbugs', 'pmd', 'lint' in quality.gradle. [See more](https://github.com/Piasy/AndroidCodeQualityConfig/issues/3).

## CheckStyle
+  [CheckStyle](https://github.com/checkstyle/checkstyle)
+  [CheckStyle-IDEA plugin](https://github.com/jshiell/checkstyle-idea)

## FindBugs
+  [Find bugs](https://github.com/findbugsproject/findbugs)

## PMD
+  [PMD](https://github.com/pmd/pmd)

## Lint

## Jacoco

In your root project `build.gradle`:

``` gradle
apply from: 'AndroidCodeQualityConfig/jacoco.gradle'
```

then define `ignoredByJacoco` array in your root project ext part to define ignoring module, and `moduleExcludes` for each not ignoring module.
