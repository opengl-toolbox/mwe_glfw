cmake_minimum_required(VERSION 3.10)

project(mwe_glfw)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

add_executable(mwe_glfw main.cpp)

# GLAD: opengl function loader

include_directories(external_libraries/glad_opengl_3.3_core/include)
add_subdirectory(external_libraries/glad_opengl_3.3_core)

# GLFW: opengl framework

# disable unnessary steps in build
set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)

add_subdirectory(external_libraries/glfw)

target_link_libraries(mwe_glfw glfw glad)
