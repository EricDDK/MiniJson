cmake_minimum_required(VERSION 2.6)
set (CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++17 -Wall")

PROJECT(MiniJson)

include_directories(${CMAKE_CURRENT_LIST_DIR}/include)
AUX_SOURCE_DIRECTORY(src DIR_SRCS)

add_library(json ../src/json.cpp)
add_library(parse ../src/parse.cpp)
add_library(test ../test/test.cpp)

add_executable(checkJson ${CMAKE_CURRENT_LIST_DIR}/test/checkJson.cpp)
target_link_libraries(checkJson json parse test)
