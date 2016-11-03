A minimalistic kokkos example to compute Mandelbrot set.

# What is kokkos ?

A modern C++ based programming model for HPC applications designed for portability across multiple hardware architectures (multicore, GPU, KNL, Power8, ...) and also providing as efficient as possible performance.

# Build

0. Need to have installed [kokkos](https://github.com/kokkos/kokkos)

   * Kokkos backend can be CUDA, OpenMP, ...
   * Compiler can be nvcc_wrapper, g++, xlc++, ...

1. Set env variable KOKKOS_PATH to the root directory where Kokkos is installed

2. make

3. run

   ./mandelbrot.omp (or ./mandelbrot.cuda)


With default parameters (image of size 8192x8192), some performance:
 * Nvidia K80 : 1.5 seconds 
 * Power8 (g++ 4.8.5)
   * 20  threads : 50.1 seconds
   * 40  threads : 27.7 seconds
   * 60  threads : 16.9 seconds
   * 160 threads : 10.5 seconds
   
