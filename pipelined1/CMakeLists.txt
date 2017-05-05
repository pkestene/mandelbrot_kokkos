cmake_minimum_required(VERSION 3.1)
project(Example CXX C)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_EXTENSIONS OFF)
list(APPEND CMAKE_CXX_FLAGS ${CMAKE_CXX_FLAGS} -O3)

add_subdirectory(kokkos)

add_executable(mandelbrot OpenMPTimer.cpp main.cpp)
target_link_libraries(mandelbrot kokkos)
