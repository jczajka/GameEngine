cmake_minimum_required(VERSION 3.9)
project(GameEngine)

set(CMAKE_CXX_STANDARD 14)

set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)
set(GLFW_USE_HYBRID_HPG ON CACHE BOOL "" FORCE)

add_subdirectory(libs/glfw)
add_subdirectory(libs/glm)
add_subdirectory(libs/imgui)
add_subdirectory(libs/glad)

include_directories(libs/glad/include)
include_directories(libs/glm/glm)
include_directories(libs/imgui)

add_executable(GameEngine main.cpp imgui_impl_glfw_gl3.cpp imgui_impl_glfw_gl3.h)

target_link_libraries(GameEngine glfw)
target_link_libraries(GameEngine ImGui)
target_link_libraries(GameEngine glad)