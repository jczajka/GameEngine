cmake_minimum_required(VERSION 3.9)
project(GameEngine)

set(CMAKE_CXX_STANDARD 14)

set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)

add_subdirectory(libs/glfw)
add_subdirectory(libs/glm)

include_directories(libs/glad/include)
include_directories(libs/glm/glm)

add_executable(GameEngine main.cpp libs/glad/src/glad.c)

target_link_libraries(GameEngine glfw)