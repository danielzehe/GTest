cmake_minimum_required(VERSION 2.8)

# Locate GTest
# find_package(GTest REQUIRED)
include_directories(/usr/local/include/gtest)
link_directories(/usr/local/lib)
# Link runTests with what we want to test and the GTest and pthread library
add_executable(runTests tests.cpp)
target_link_libraries(runTests gtest pthread)
