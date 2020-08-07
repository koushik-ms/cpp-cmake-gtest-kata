project(cpp-cmake-gtest-kata)

cmake_minimum_required(VERSION 2.8)

enable_testing()

# Set C++ Language versions and options
set(CXX_STANDARD 17)
set(CXX_STANDARD_REQUIRED ON)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

add_subdirectory(/usr/src/googletest gtest)

add_executable(kata kata.cpp)
target_link_libraries(kata gtest gtest_main)

add_test(kata kata)
