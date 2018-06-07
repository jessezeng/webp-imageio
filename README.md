# webp-imageio
fork from :  https://bitbucket.org/luciad/webp-imageio

# Description
[Java Image I/O](http://docs.oracle.com/javase/7/docs/api/javax/imageio/package-summary.html) reader and writer for the
[Google WebP](https://developers.google.com/speed/webp/) image format.

# License
webp-imageio is distributed under the [Apache Software License](https://www.apache.org/licenses/LICENSE-2.0) version 2.0.

# Usage
- Add webp-imageio.jar to the classpath of your application
- Ensure libwebp-jni.so or webp-jni.dll is accessible on the Java native library path (java.library.path system property)
- The WebP reader and writer can be used like any other Image I/O reader and writer.

# Compiling
The build should work with either Maven or CMake but the Maven build incorporates unit tests to confirm that the generated library works.

## Maven
The Maven build uses the [cmake-maven-plugin](https://code.google.com/p/cmake-maven-project/) to build the native code.  The Java code, of course, just uses Maven.
- Run 'mvn clean install'
- The build will automatically download libwebp and compile it into the JNI library

## CMake
- Install CMake 2.8 or newer. CMake can be downloaded from www.cmake.org or installed using your systems package manager.
- Create a directory called build in the root of the project
- Open a terminal and navigate to the newly created 'build' directory
- Run cmake .. in the 'build' directory to generate the build scripts for your system.
- cmake --build . to compile the library
- The compiled library can be found under the directory build/src/main/c
## Compiling the Java library
Using Gradle
- Run ./gradlew build -x test in the root of the project
- The compiled Java library can be found under the build directory
