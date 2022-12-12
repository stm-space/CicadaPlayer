# AndroidCompile
This page is an introduction to the compilation for Android on MacOS or Ubuntu.
1. install android ndk (14b) and Android studio
     - [Android Studio](https://developer.android.com/studio)
     - [Android ndk](https://developer.android.com/ndk/downloads/older_releases.html)

       [we recommend 14b for MacOS](https://dl.google.com/android/repository/android-ndk-r14b-darwin-x86_64.zip)

       [we recommend 14b for Linux](https://dl.google.com/android/repository/android-ndk-r20b-linux-x86_64.zip)
     -  [jdk](https://www.oracle.com/technetwork/java/javase/downloads/index.html)

        [we recommend jdk8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)

2. Host Requirements
    - MacOS
    
        - [brew](https://brew.sh/)

        ```bash
        brew install automake git libtool autoconf
        ```

    - Ubuntu
    
        ```bash
        sudo apt-get utomake git libtool autoconf
        ```
 
2. 设置环境变量（针对 Mac 设备）

	```bash
	export ANDROID_SDK_HOME=$HOME/Library/Android/sdk
	export PATH=$PATH:$ANDROID_SDK_HOME
	
	export ANDROID_NDK=${ANDROID_SDK_HOME}/ndk/android-ndk-r14b
	export PATH=$PATH:$ANDROID_NDK
	
	export PATH=$PATH:${ANDROID_NDK}:${ANDROID_NDK}/toolchains/arm-linux-androideabi-4.9/prebuilt/${HOST}-x86_64/bin
	export PATH=$PATH:${ANDROID_NDK}/toolchains/aarch64-linux-android-4.9/prebuilt/${HOST}-x86_64/bin
	export PATH=$PATH:${ANDROID_SDK_HOME}/platform-tools
	
	export ANDROID_NDK_ROOT=${ANDROID_NDK}
	export ANDROID_BUILD_DIR=$HOME/Downloads/github/CicadaPlayer
	export ANDROID_NDK_HOME=${ANDROID_NDK}
	export NDK_ROOT=${ANDROID_NDK}
	export VERSION="2022.1212.1522"
	```

3. 编译
    
    ```bash
    cd external
    sh build_external.sh Android
    ```
4. open the Android studio project  ../platform/Android/source/
5. edit local.properties ,add ndk.dir=your_ndk_path


