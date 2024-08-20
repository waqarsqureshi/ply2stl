
# Minimum required version of CMake
cmake_minimum_required(VERSION 2.8)
# set CMake project name
project(PLY2STL)
set (VERSION_MAJOR 1)
set (VERSION_MINOR 0)
configure_file (
  "./ply2stlConfig.h.in"
  "${PROJECT_BINARY_DIR}/ply2stlConfig.h"
  )

list( APPEND CMAKE_CXX_FLAGS "-std=c++0x ${CMAKE_CXX_FLAGS} -g -ftest-coverage -fprofile-arcs")
# Temporary settings until third party build logic is
set(VCG_INCLUDE_DIR https://github.com/cnr-isti-vclab/vcglib/)
include_directories(${VCG_INCLUDE_DIR} ${PROJECT_BINARY_DIR})
set(SOURCES ply2stl.cpp ${VCG_INCLUDE_DIR}/wrap/ply/plylib.cpp)
add_library(plylib ${VCG_INCLUDE_DIR}/wrap/ply/plylib.cpp)
add_executable (ply2stl  ${SOURCES})
target_link_libraries (ply2stl plylib)
