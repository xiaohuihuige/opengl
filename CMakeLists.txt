cmake_minimum_required(VERSION 3.22.1)
project(my_app)

set(CMAKE_CXX_STANDARD 11)
find_package(OpenGL REQUIRED)

set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)

include_directories(src)

include_directories(${CMAKE_SOURCE_DIR}/include)

add_executable(my_app src/main.cpp 3rdparty/glad/src/glad.c)

target_link_libraries(my_app OpenGL::GL)
target_link_libraries(my_app ${CMAKE_SOURCE_DIR}/3rdparty/libglfw3.a)
