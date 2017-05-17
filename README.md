# example-cmake-helloworld-cpp
[![Build Status](https://travis-ci.org/ibrahimelfar/example-cmake-travis-helloworld-cpp.svg?branch=master)](https://travis-ci.org/ibrahimelfar/example-cmake-travis-helloworld-cpp)

This is an example of how to use CMake and Travis to build a Hello World C++ program and set up continuous integration.

## Getting and Running this Example

To get and run this example on Mac or Ubuntu

```bash
git clone https://github.com/ibrahimelfar/example-cmake-travis-helloworld-cpp.git
cmake . && make && ./hello
```

## Elements

After making sure [cmake is installed](https://cmake.org/install/), there are four pieces to this example.

First, there is the hello world C++ file.

```cpp
#include<iostream>

int main(int argc, char *argv[]){
   std::cout << "hello" << std::endl;
   return 0;
}
```

Second, there is the CMakeLists.txt which tells cmake how to build this simple project.

```
project (hello)
add_executable(hello hello.cpp)
```

Third, to verify things locally, simply run cmake, followed by make, and then the hello world executable itself.

```bash
cmake . && make && ./hello
```

Last, this is a minimal file for Travis CI to work.

```
script:
  - cmake . && make && ./hello
```
