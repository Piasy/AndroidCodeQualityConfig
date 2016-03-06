# AndroidCodeQualityConfig
Code quality config for android project, including lint, pmd, findbugs, checkstyle, jacoco code coverage. Serve as a submodule for repo: https://github.com/Piasy/AndroidTDDBootStrap
+  Usage
  +  step 1. fork me
  +  step 2. import the forked repo as git submodule, or just put the folder under your project root.
  +  step 3. `apply from: '../AndroidCodeQualityConfig/quality.gradle'` for android module or `apply from: '../AndroidCodeQualityConfig/quality-java.gradle'` for java module, then run `gradle check`
  +  step 4. no more step 4 :).

## CheckStyle
+  [CheckStyle](https://github.com/checkstyle/checkstyle)
+  [CheckStyle-IDEA plugin](https://github.com/jshiell/checkstyle-idea), the latest version has a problem, `Unsupported major.minor version 52.0 [Plugin: CheckStyle-IDEA] [Plugin: CheckStyle-IDEA]` when opening a project, [fix](https://github.com/jshiell/checkstyle-idea/issues/142).

## FindBugs
+  [Find bugs](https://github.com/findbugsproject/findbugs)

## PMD
+  [PMD](https://github.com/pmd/pmd)

## Lint

## Jacoco
`apply from: 'AndroidCodeQualityConfig/jacoco.gradle'`

then define `ignoredByJacoco` array in your root project ext part to define ignoring module, and `moduleClassDirs`,
`moduleJacocoExec`, `moduleExcludes` for each not ignoring module.
