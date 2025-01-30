cmake_minimum_required(VERSION 3.24.2 FATAL_ERROR)

set(CMAKE_CXX_STANDARD 17)
set(PROJECT_NAME testproj)

project(${PROJECT_NAME} VERSION 1.0.0)

file(GLOB_RECURSE files
    "src/*.h"
    "src/*.hpp"
    "src/*.c"
    "src/*.cpp"
)

add_executable(${PROJECT_NAME} ${files})

source_group(TREE ${CMAKE_CURRENT_SOURCE_DIR} FILES ${files})
set_property(DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR} PROPERTY VS_STARTUP_PROJECT ${PROJECT_NAME})
