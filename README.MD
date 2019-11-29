# Shotgun Gradle Plugin

A gradle configuration plugin for [shotgun](https://bitbucket.org/sonalake/shotgun)

## Using the plugin

In `build.gradle`

Add the plugin

    plugins {
      id 'shotgun-gradle-plugin' version "1.0.0-SNAPSHOT"
    }

### Finding the plugin

Unless we make this public, you'll need to update your `settings.gradle` to
include this setting so your gradle will know to look into our nexus.


    pluginManagement {
      repositories {
        maven {url "http://atlanta:8081/nexus/content/groups/public"}
        gradlePluginPortal()
      }
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
      legendLevels              =   ["10", "20", "30", 50", "80", "120"]
    }
