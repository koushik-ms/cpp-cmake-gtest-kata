project(cpp-cmake-gtest-kata)

cmake_minimum_required(VERSION 2.8)

enable_testing()

# Set C++ Language versions and options
set(CXX_STANDARD 17)
set(CXX_STANDARD_REQUIRED ON)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

# find_package(gtest REQUIRED)

find_package(Threads REQUIRED)

add_library(gtest STATIC /usr/src/googletest/googletest/src/gtest-all.cc)
target_include_directories(gtest PUBLIC /usr/src/googletest/googletest/)

add_library(gtest_main STATIC /usr/src/googletest/googletest/src/gtest_main.cc)
target_include_directories(gtest_main PUBLIC /usr/src/googletest/googletest/)

add_executable(kata kata.cpp)
target_link_libraries(kata gtest gtest_main Threads::Threads)

# add_custom_command(TARGET kata POST_BUILD  COMMAND ${CMAKE_CURRENT_SOURCE_DIR}/build/kata USES_TERMINAL)
