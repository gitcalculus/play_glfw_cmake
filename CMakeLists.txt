
project(glPlay C)
cmake_minimum_required(VERSION 2.8.12)

include_directories("${glPlay_SOURCE_DIR}/deps" "${glPlay_SOURCE_DIR}/include")

set(GLAD "${glPlay_SOURCE_DIR}/deps/glad/glad.h"
            "${glPlay_SOURCE_DIR}/deps/glad.c")

if( APPLE )
    # Set up library and include paths
    find_library(COCOA_FRAMEWORK Cocoa)
    find_library(IOKIT_FRAMEWORK IOKit)
    find_library(CORE_FOUNDATION_FRAMEWORK CoreFoundation)
    find_library(CORE_VIDEO_FRAMEWORK CoreVideo)
    mark_as_advanced(COCOA_FRAMEWORK
                     IOKIT_FRAMEWORK
                     CORE_FOUNDATION_FRAMEWORK
                     CORE_VIDEO_FRAMEWORK)
    list(APPEND glfw_LIBRARIES "${COCOA_FRAMEWORK}"
                               "${IOKIT_FRAMEWORK}"
                               "${CORE_FOUNDATION_FRAMEWORK}"
                               "${CORE_VIDEO_FRAMEWORK}")
endif()

find_library( MYMATH_LIBS NAMES myCMath PATHS ${glPlay_SOURCE_DIR}/deps NO_DEFAULT_PATH )
find_library( GLFW_LIBS NAMES glfw3 glfw libglfw PATHS ${glPlay_SOURCE_DIR}/deps NO_DEFAULT_PATH)

message("${MYMATH_LIBS} mymath_libs")
message("${GLFW_LIBS}  glfw_libs")

add_executable(mainApp WIN32 MACOSX_BUNDLE main.c ${GLAD})

target_link_libraries( mainApp ${MYMATH_LIBS} ${GLFW_LIBS} ${glfw_LIBRARIES} )

# set_target_properties(mainApp PROPERTIES MACOSX_BUNDLE_BUNDLE_NAME "mainApp")
