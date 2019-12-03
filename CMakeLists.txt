project(global_reconstruction CXX CUDA)
cmake_minimum_required(VERSION 3.10)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(Eigen3 REQUIRED CONFIG)
find_package(Ceres REQUIRED CONFIG)

if(NOT TARGET gtest_main)
  add_subdirectory(external/google-test)
endif()
if(NOT TARGET benchmark_main)
  set(BENCHMARK_ENABLE_TESTING
      OFF
      CACHE BOOL "Suppress google-benchmark tests" FORCE)
  add_subdirectory(external/google-benchmark)
endif()
