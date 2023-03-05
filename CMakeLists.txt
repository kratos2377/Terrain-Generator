cmake_minimum_required(VERSION 3.2 FATAL_ERROR)
project(terrain_generator VERSION 0.1 LANGUAGES CXX)

set (CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -g -O2 -Wall -Wshadow")

add_subdirectory(external)
add_subdirectory(src)
