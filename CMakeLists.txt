cmake_minimum_required(VERSION 3.15)
project(HelloCI LANGUAGES CXX)

# choose C++17 (or whatever you prefer)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# enable testing support
enable_testing()

# main executable (just prints "Hello, World!")
add_executable(hello src/main.cpp)

# add a simple test that runs the main executable
add_test(
  NAME HelloRuns
  COMMAND hello
)

# a separate small test executable using <cassert>
add_executable(test_assert tests/test_assert.cpp)
add_test(
  NAME AssertTest
  COMMAND test_assert
)
