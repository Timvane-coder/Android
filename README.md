# termux__app-template
Android application template for termux

### termux info
```
device: aarch64
gradle: 8.6
java: 17
```

### android-sdk info
https://github.com/lzhiyong/termux-ndk/releases
```
cmake: 3.25.1
build-tools: 34.0.0
platform-tools: 34.0.3
```

### android-sdk-tools (sdk patch for termux) info
https://github.com/lzhiyong/android-sdk-tools/releases
```
version: 34.0.3
```

### Folder tree
```
.
├── .
├── app
│   ├── src
│   │   └── main
│   │       ├── java/com/template
│   │       │   └── MainActivity.java
│   │       ├── res/*
│   │       └── AndroidManifest.xml
│   ├── build.gradle
│   └── proguard-rules.pro
├── gradle
│   └── wrapper
│       ├── gradle-wrapper.jar
│       └── gradle-wrapper.properties
├── .gitignore
├── build.gradle
├── gradle.properties
├── gradlew
├── gradlew.bat
├── local.properties
└── settings.gradle
```

---
### app config info
compile, build tool version to 34 as
```
compileSdkVersion 34
buildToolsVersion "34.0.3"
```
in `./app/build.gradle` file

### plugin info 
```
version: 8.4
```
- `com.android.tools.build:gradle:8.4.0` in `./build.gradle` file
- `distributionUrl=https\://services.gradle.org/distributions/gradle-8.4-bin.zip` in `./gradle/wrapper/gradle-wrapper.properties` file 

---

if you wish to change the android-sdk pathing for your app, update the app files accordingly, default locations are as below

### path info
- android-sdk = `$PREFIX/share/android-sdk/`
- sdkmanager = `$PREFIX/bin/sdkmanager`
```
#!/data/data/com.termux/files/usr/bin/bash

 /data/data/com.termux/files/usr/share/android-sdk/tools/bin/sdkmanager \
     --sdk_root=/data/data/com.termux/files/usr/share/android-sdk "$@"
```


### file config
- `./gradle.properties`'s aapt2 path to 
```
android.aapt2FromMavenOverride=/data/data/com.termux/files/usr/share/android-sdk/build-tools/34.0.0/aapt2
```
- `./local.properties`'s sdk path to
```
sdk.dir=/data/data/com.termux/files/usr/share/android-sdk
```


