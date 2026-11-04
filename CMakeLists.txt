cmake_minimum_required(VERSION 3.20)
project(LearnOpenGL LANGUAGES C CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_executable(LearnOpenGL
    src/main.cpp
    external/glad/src/glad.c
)

if(MSVC)
    target_compile_options(LearnOpenGL PRIVATE /Zc:__cplusplus)
endif()

# GLFW headers
target_include_directories(LearnOpenGL PRIVATE
    "${CMAKE_CURRENT_SOURCE_DIR}/external/glad/include"
    "C:/Users/rache/Downloads/glfw-3.5.1/include"
)

# GLFW library and Windows OpenGL library
target_link_libraries(LearnOpenGL PRIVATE
    "C:/Users/rache/Downloads/glfw-3.5.1/build/src/Debug/glfw3.lib"
    opengl32
)