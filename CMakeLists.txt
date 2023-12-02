cmake_minimum_required(VERSION 3.5)

project(shaderbasics)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -Wno-dev -O3")

find_package(PkgConfig REQUIRED)
pkg_search_module(GLFW REQUIRED glfw3)

set(SOURCE_FILES src/main.cpp src/glad/glad.c)

add_executable(shaderbasics ${SOURCE_FILES})
target_link_libraries(shaderbasics ${GLFW_LIBRARIES})
target_include_directories(shaderbasics PRIVATE include)
set_target_properties(shaderbasics PROPERTIES CXX_STANDARD 14)