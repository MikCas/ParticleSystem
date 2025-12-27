cmake_minimum_required(VERSION 3.10)
project(ParticleSystem)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(glfw3 3.3 REQUIRED)
find_package(OpenGL REQUIRED)

include_directories(${CMAKE_SOURCE_DIR}/include)

add_executable(ParticleSystem 
    src/main.cpp 
    lib/glad.c
)

target_link_libraries(ParticleSystem glfw OpenGL::GL)

file(COPY ${CMAKE_SOURCE_DIR}/shaders DESTINATION ${CMAKE_BINARY_DIR})