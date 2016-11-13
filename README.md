# AndroidCodeQualityConfig

Code quality config for android project, including lint, pmd, findbugs, checkstyle, jacoco code coverage. Serve as a submodule for repo: https://github.com/Piasy/AndroidTDDBootStrap

+  Usage
  +  step 1. fork me
  +  step 2. import the forked repo as git submodule, or just put the folder under your project root.
  +  step 3. `apply from: '../AndroidCodeQualityConfig/quality.gradle'` for android module then run `gradle check`
  +  step 4. no more step 4 :).

If you have many modules, you have another option:

+ step 3. add below code into your root project's `build.gradle`:

``` gradle
subprojects {
    apply from: "$rootProject.projectDir/AndroidCodeQualityConfig/quality.gradle"

    afterEvaluate {
        check.dependsOn 'checkstyle', 'findbugs', 'pmd', 'lint'
   }
}
```

+ step 4. remove `check.dependsOn 'checkstyle', 'findbugs', 'pmd', 'lint'` in quality.gradle.
+ step 5. change the last paragraph of quality.gradle into this:

``` gradle
afterEvaluate {
    android {
        lintOptions {
            abortOnError true
            xmlReport true
            htmlReport true
            lintConfig file("${project.rootDir}/AndroidCodeQualityConfig/quality/lint/lint.xml")
        }
    }
}
```

## CheckStyle
+  [CheckStyle](https://github.com/checkstyle/checkstyle)
+  [CheckStyle-IDEA plugin](https://github.com/jshiell/checkstyle-idea)

## FindBugs
+  [Findbugs](https://github.com/findbugsproject/findbugs)

## PMD
+  [PMD](https://github.com/pmd/pmd)

## Lint
+  [Android Lint](http://tools.android.com/tips/lint)

## Jacoco

In your root project `build.gradle`:

``` gradle
apply from: 'AndroidCodeQualityConfig/jacoco.gradle'
```

then define `ignoredByJacoco` array in your root project ext part to define ignoring module, and `moduleExcludes` for each not ignoring module.

## License

    The MIT License (MIT)

    Copyright (c) 2015 Piasy

    Permission is hereby granted, free of charge, to any person obtaining a copy
    of this software and associated documentation files (the "Software"), to deal
    in the Software without restriction, including without limitation the rights
    to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
    copies of the Software, and to permit persons to whom the Software is
    furnished to do so, subject to the following conditions:

    The above copyright notice and this permission notice shall be included in all
    copies or substantial portions of the Software.

    THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
    IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
    FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
    AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
    LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
    OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
    SOFTWARE.
