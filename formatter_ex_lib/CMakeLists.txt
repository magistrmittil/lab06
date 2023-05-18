cmake_minimum_required(VERSION 3.20)

project(formatter_ex)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/formatter_lib)
add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/formatter_lib formatter)
add_library(formatter_ex STATIC ${CMAKE_CURRENT_SOURCE_DIR}/formatter_ex.cpp)

target_link_libraries(formatter_ex formatter)
