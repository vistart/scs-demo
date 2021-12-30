# This file handles building each task as sub-project.
#
# Each task becomes an independent project in which you can experiment.
#
# Tasks are added as separate sub-projects so as compilation errors in
# one task don't affect another task.

cmake_minimum_required(VERSION 3.5)
project(scs-demo)

set(CMAKE_CXX_STANDARD 14)
find_package(scs REQUIRED)

# Add tasks subprojects
# include(cmake/utils.cmake)
# add_subprojects(${CMAKE_SOURCE_DIR})
# add_executable(example example.cpp)
# add_executable(degenerate example/degenerate.cpp)
add_executable(small_lp example/small_lp.cpp)
add_executable(small_qp example/small_qp.cpp)

target_link_libraries(small_lp scs::scsdir)
target_link_libraries(small_lp scs::scsindir)
target_link_libraries(small_qp scs::scsdir)
target_link_libraries(small_qp scs::scsindir)