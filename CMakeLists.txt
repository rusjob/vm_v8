cmake_minimum_required(VERSION 3.8.0)

project(vm_v8 VERSION 1.0.0 LANGUAGES C CXX)

set(CMAKE_CXX_STANDARD 17)

if(NOT CMAKE_BUILD_TYPE)
    message(STATUS "No build type selected, default is Release")
    set(CMAKE_BUILD_TYPE "Release")
endif()

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

include(CTest)
enable_testing()

find_package(GTest REQUIRED)
include_directories(SYSTEM ${GTEST_INCLUDE_DIR})

find_package(GMock REQUIRED)
include_directories(SYSTEM ${GMOCK_INCLUDE_DIRS})


add_subdirectory(src)
