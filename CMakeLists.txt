project(kata CXX C)

cmake_minimum_required(VERSION 2.8)

enable_testing()

set(CXX_STANDARD 17)
set(CXX_STANDARD_REQUIRED ON)
# set(GTEST_ROOT "/usr/src/gtest")

find_package(Threads REQUIRED)
find_package(GTest REQUIRED)

add_executable(kata kata.cpp)
target_link_libraries(kata GTest::GTest GTest::Main Threads::Threads)

# add_test(kata kata)

