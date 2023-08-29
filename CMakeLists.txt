cmake_minimum_required(VERSION 2.6)
project(ScanCUDA)
find_package(CUDA)

message(STATUS "CMAKE_MODULE_PATH is " ${CMAKE_CURRENT_SOURCE_DIR})
include_directories(${CMAKE_CURRENT_SOURCE_DIR})

cuda_add_library(ScanKernel STATIC scan.cu)
add_executable(Scan main.cpp scan_gold.cpp)
target_link_libraries(Scan ScanKernel)