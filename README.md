## play_glfw_cmake

#Play with cmake

//from a cmake newbie

use cmake link glfw static lib to a custom test code

ENV:
    glfw static lib: libglfw3.a
    glfw version: 3.2.1
    OS: MaxOSX 10.11.6
    CMake: from homebrew
    Apple LLVM version: 8.0.0

Use CMake:
    Copy libglfw3.a to deps
    mkdir build
    cd build
    cmake ../
    make



main.c copy from glfw-3.2.1/example/simple.c

deps & include also copy from glfw-3.2.1

myCMath is for testing custom static lib
