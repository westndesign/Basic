cmake_minimum_required(VERSION 3.10)

# Set the output directories for all build types
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/$<CONFIG>)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/$<CONFIG>)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/$<CONFIG>)

# Set the project name and version
project(MyProject VERSION 1.0)

# Specify the C++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# Add folders
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/inc)

# Add the executable
file(GLOB SOURCES "src/*.cpp")
add_executable(MyProject ${SOURCES})

# Optionally, you can enable testing like this:
enable_testing()
add_test(NAME MyTest COMMAND MyProject)
