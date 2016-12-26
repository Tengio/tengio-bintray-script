Tengio bintray Script
=====================

Script that simplify the bintray configuration for android libraries. The configuration is based on tengio usual configuration. 
If you want to use something similar for your organization you can override all the bintray properties.

Usage
-----

You can place this in your root build.gradle or you app build.gradle.

This script need bintray and maven plugin to be declared as dependencies: 

```
classpath 'com.jfrog.bintray.gradle:gradle-bintray-plugin:1.7.3'
classpath 'com.github.dcendents:android-maven-gradle-plugin:1.5'
```

they need to be added in the buildscript like this example:

```
buildscript {
  repositories {
        jcenter()
        maven { url "https://plugins.gradle.org/m2/" }
    }
    dependencies {
        classpath 'com.android.tools.build:gradle:2.2.3'
        classpath 'com.jfrog.bintray.gradle:gradle-bintray-plugin:1.7.3'
        classpath 'com.github.dcendents:android-maven-gradle-plugin:1.5'
        classpath "gradle.plugin.com.tengio.gradle:tengio-checkstyle-plugin:1.0"
    }
}
```

To use the script you just have to use ```apply from``` in the library module.

```
apply from: 'https://raw.githubusercontent.com/Tengio/tengio-bintray-script/master/bintray.gradle'
```

Finally aa minimal configuration for the project you need:

```
bintray {
  pkg {
    name = 'project-name'
    vcsUrl = 'https://github.com/Tengio/your-repo.git'
  }
}
```

Bintray plugin expect the user and api key to be declared as env properties. 
The best way to set the properties you can add them in the ~/.gradle/gradle.properties file.

```
BINTRAY_KEY=
BINTRAY_USER=
```