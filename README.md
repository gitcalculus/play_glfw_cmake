## play_glfw_cmake

#Play with cmake

//from a cmake newbie

use cmake link glfw static lib to a custom test code

ENV:<br/>
    glfw static lib: libglfw3.a<br/>
    glfw version: 3.2.1<br/>
    OS: MaxOSX 10.11.6<br/>
    CMake: from homebrew<br/>
    Apple LLVM version: 8.0.0<br/>

Use CMake:<br/>
    Copy libglfw3.a to deps<br/>
    mkdir build<br/>
    cd build<br/>
    cmake ../ <br/>
    make<br/>



main.c copy from glfw-3.2.1/example/simple.c

deps & include also copy from glfw-3.2.1

myCMath is for testing custom static lib






EOF
