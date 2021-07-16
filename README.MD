# Shotgun Gradle Plugin

A gradle configuration plugin for [shotgun](https://github.com/sonalake/shotgun)

## Using the plugin

In `build.gradle`

Add the plugin

    plugins {
      id 'shotgun-gradle-plugin' version "1.0.0"
    }

## Configuring the plugin

The minimum configuration is a simple

    shotgun

This will scan the current directory, and using defaults, will write out to
`.shotgun/report.html`


The default options are suitable for most java projects

    shotgun {
      inputDirectory            = "$projectDir"
      outputFile                = ".shotgun/report.htm"
      sourceSets                = ["src/main/java",
                                    "src/main/resources",
                                    "src/main/webapp",
                                    "src/test/java",
                                    "src/test/resources"]
      minimumCommitInterest     =   3
      topCommitValueForFileSets =   10
      topCommitValueForFiles    =   40
      legendLevels              =   [10, 20, 30, 50, 80, 120]
    }

### Running the plugin

Simple enough

    ./gradlew shotgun