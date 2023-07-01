cmake_minimum_required(VERSION 3.25)
project(GLFWTest_2)

set(CMAKE_CXX_STANDARD 17)

add_executable(GLFWTest_2 main.cpp)

include_directories(
        "${CMAKE_CURRENT_SOURCE_DIR}/Dependencies/GLFW/include"
)

add_library(glfw STATIC IMPORTED)
set_target_properties(
        glfw PROPERTIES
        IMPORTED_LOCATION "${CMAKE_CURRENT_SOURCE_DIR}/Dependencies/GLFW/lib/libglfw3.a"
        INTERFACE_INCLUDE_DIRECTORIES "${CMAKE_CURRENT_SOURCE_DIR}/Dependencies/GLFW/include")

target_link_libraries(GLFWTest_2 glfw)
add_library(
        glad STATIC
        Dependencies/GLFW/lib/glad.c
)
target_link_libraries(GLFWTest_2 glad)


