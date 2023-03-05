cmake_minimum_required(VERSION 3.20)
# Add vcpkg as package manager and install dependencies
include(FetchContent)
FetchContent_Declare(vcpkg
     GIT_REPOSITORY https://github.com/microsoft/vcpkg/
     GIT_TAG 2022.09.27
)
FetchContent_MakeAvailable(vcpkg)
 
set(CMAKE_TOOLCHAIN_FILE "${vcpkg_SOURCE_DIR}/scripts/buildsystems/vcpkg.cmake" CACHE FILEPATH "")
 
project(terrain-generator LANGUAGES CXX)

# Dependencies
find_package(glfw3 CONFIG REQUIRED)
find_package(glad CONFIG REQUIRED)
find_package(glm CONFIG REQUIRED)
find_package(imgui CONFIG REQUIRED)
find_path(STB_INCLUDE_DIRS "stb_c_lexer.h")

add_subdirectory(src)