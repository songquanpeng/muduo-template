cmake_minimum_required(VERSION 3.0)

project(echo CXX)

if(NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE "Release")
endif()

add_subdirectory(./lib/muduo)
include_directories("./lib/muduo")

add_executable(echo ./src/echo.cpp)
target_link_libraries(echo muduo_net)
target_link_libraries(echo muduo_base)
target_link_libraries(echo pthread rt)