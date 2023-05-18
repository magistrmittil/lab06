cmake_minimum_required(VERSION 3.4)

#set(PRINT_VERSION "0.1.2.0")

project(solver)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)


add_executable(solver ${CMAKE_CURRENT_SOURCE_DIR}/solver_application/equation.cpp)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/formatter_ex_lib ${CMAKE_CURRENT_SOURCE_DIR}/solver_lib)
add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/formatter_ex_lib formatter_ex)
add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/formatter_lib formatter_lib)
add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/solver_lib solver_lib)

target_link_libraries(solver formatter_ex solver_lib)

install(TARGETS solver
RUNTIME DESTINATION bin
)


include(CPackConfig.cmake)