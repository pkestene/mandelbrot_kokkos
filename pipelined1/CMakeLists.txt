cmake_minimum_required(VERSION 3.1)
project(Mandelbrot CXX C)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_EXTENSIONS OFF)
list(APPEND CMAKE_CXX_FLAGS ${CMAKE_CXX_FLAGS} -O3)

add_subdirectory(${Mandelbrot_SOURCE_DIR}/../kokkos ${Mandelbrot_BINARY_DIR}/kokkos)

if(KOKKOS_ENABLE_CUDA)
  set( CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -DKOKKOS_ENABLE_CUDA" )
endif()

add_executable(mandelbrot OpenMPTimer.cpp main.cpp)
target_link_libraries(mandelbrot kokkos)
