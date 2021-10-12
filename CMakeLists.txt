# Top-level CMake file, at root direcotry, states project name and cmake version
cmake_minimum_required(VERSION 3.20)
project(Barney12-cmake-build-systems)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# Load any sub-directories, to one layer down
add_subdirectory(utilities)
