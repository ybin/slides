### Introduction to Android Studio
<br/>

<small>孙延宾</smal>

<=== slide ===>

### Start
<br/>

1. <p class="fragment">Download Android Studio(and SDK)</p>
1. <p class="fragment">Set network proxy for Maven(optional)</p>
1. <p class="fragment">No step.3</p>

<=== slide ===>

##### Download Android Studio(and SDK)
<br/>

- [http://www.androiddevtools.cn/](http://www.androiddevtools.cn/)
- [http://www.android-studio.org/](http://www.android-studio.org/)

<=== subslide ===>

![Download Android Studio](../slides/android-studio/android_studio_download.jpg)

<=== slide ===>

##### Set network proxy for Maven
<br/>

```bash
# set environment variables
http_proxy=http://<username>:<passwd>@<host>:<port>
https_proxy=http://<username>:<passwd>@<host>:<port>

# for example
http_proxy=http://10130990:zte.1234@proxyxa.zte.com.cn:80
https_proxy=http://10130990:zte.1234@proxyxa.zte.com.cn:80
```

<=== slide ===>

##### Project Structure of Android Studio


<=== slide ===>

### Settings for Camera APP
<br/>
`build.gradle`

```groovy
apply plugin: "com.android.application"
android {
    compileSdkVersion 23
    buildToolsVersion "22.0.1"
    defaultConfig {
        applicationId "com.zte.camera"
        targetSdkVersion 23
        versionCode 1
        versionName "1.0"
    }
    buildTypes {
        debug {
            applicationIdSuffix ".dual"
            versionNameSuffix "-dual"
        }
    }
```

<=== subslide ===>

`build.gradle` (continue)
```groovy
    sourceSets {
        main {
            manifest.srcFile 'AndroidManifest.xml'
            java.srcDirs = ['src']
            resources.srcDirs = ['src']
            aidl.srcDirs = ['src']
            renderscript.srcDirs = ['src']
            res.srcDirs = ['res']
            assets.srcDirs = ['assets']
            jniLibs.srcDirs = ['libs']
        }
    }
    lintOptions {
        abortOnError false
    }
}
```

<=== subslide ===>

`build.gradle` (continue)
```groovy
/**
 * Important!!!
 */
gradle.projectsEvaluated {
    tasks.withType(JavaCompile) {
        options.compilerArgs <<
			"-Xbootclasspath/p:<path/to/your/zte_framework.jar>"
        options.encoding = "GBK"
    }
}

dependencies {
    compile fileTree(dir:'libs', include:'*.jar')
}
```

<=== slide ===>

### What is Android Studio?
<br/>

- <p class="fragment">IntelliJ Idea</p>
- <p class="fragment">Android plugin for Intellij Idea</p>
- <p class="fragment">Android plugin for Gradle</p>
- <p class="fragment">CLion for C/C++</p>

<=== slide ===>

##### IntelliJ Idea

<=== slide ===>

##### Android plugin for Idea

<=== slide ===>

##### Android plugin for Gradle

<=== slide ===>

##### CLion for C/C++

<=== slide ===>

### Configurations for your own Android Studio

<=== slide ===>

### 实时监控APP状态

<=== slide ===>

### Debug

<=== slide ===>

### Unresolved problems

