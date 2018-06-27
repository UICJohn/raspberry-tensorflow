# Tensorflow in Raspberry
### Device & Preparation

  - Raspberry Pi 3B
  - 2G Flash Drive
  - 32GB SD card
  - Ubuntu mate 16.04. see [Ubuntu Mate](https://ubuntu-mate.org/raspberry-pi/)

### Compile Bazel in Raspberry pi
  1. Download source code(v0.15.1). Source code can be found here [Bazel](https://github.com/bazelbuild/bazel/releases)
  ```sh
  1. wget https://github.com/bazelbuild/bazel/releases/download/0.15.0/bazel-0.15.0-dist.zip
  2. mkdir bazel && unzip bazel-0.15.0-dist.zip -d bazel/
  ```
  
  2. Tweak **bazel/scripts/bootstrap/compile.sh** line 117
  
  ```sh
  run "${JAVAC}" -classpath "${classpath}" -sourcepath "${sourcepath}" \
    -d "${output}/classes" -source "$JAVA_VERSION" -target "$JAVA_VERSION" \
    -encoding UTF-8 "@${paramfile}" -J-Xmx500M
  ```


  3. Compile Bazel 
  ```
    ./compile.sh
  ```
The compiling could take up to 4 hours.

### Compile Tensorflow