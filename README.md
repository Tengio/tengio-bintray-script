Tengio bintray Script
=====================

Script that simplify the bintray configuration for android libraries. The configuration is based on tengio usual configuration. 
If you want to use something similar for your organization you can override all the bintray properties.

Usage
-----

You can place this in your root build.gradle or you app build.gradle.

To use the script you just have to use ```apply from``` in the library module.

```
apply from: 'https://raw.githubusercontent.com/Tengio/tengio-bintray-script/master/bintray.gradle'
```

You then need to add the following information for bintray:

```

bintray {
  pkg {
    name = 'project-name'
    vcsUrl = 'https://github.com/Tengio/your-repo.git'
  }
}
```

