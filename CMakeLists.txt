cmake_minimum_required(VERSION 3.17.2)

# Not really recommended, but we do it anyways
set(CMAKE_C_COMPILER "clang")
set(CMAKE_CXX_COMPILER "clang++")

project(hello VERSION 0.1.0 LANGUAGES C CXX)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

set(SOURCES
    src/main.cpp
)

# Compiler flags
set(COMPILE_FLAGS "-Wall")
set(CMAKE_CXX_FLAGS ${COMPILE_FLAGS})

# Bynary file
add_executable(hello ${SOURCES})

# Finding and linking libraries
find_package(fmt REQUIRED)
target_link_libraries(hello fmt::fmt)
