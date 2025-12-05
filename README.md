# Matrix Multiplication Parallel Computing Assignment

## Prerequisites
- MSYS2 MinGW with GCC and OpenMP support
- MPICH or OpenMPI (via MSYS2)
- NVIDIA CUDA Toolkit (for CUDA implementation)
- Windows environment with MSYS2



## Compilation Instructions

### Serial Code Compilation
```bash
gcc serial_code.c -o serial_code
```

### OpenMP Code Compilation
```bash
gcc -fopenmp openmp_code.c -o openmp_code
```

### MPI Code Compilation
```bash
mpicc -o mpi_code mpi_code.c
```

### CUDA Code Compilation
```bash
nvcc cuda_code.cu -o cuda_code.exe
```

## Execution Instructions

### Serial
```bash
./serial_code
```

### OpenMP
```bash
# Run with different thread counts (MSYS2 MinGW)
export OMP_NUM_THREADS=1 && ./openmp_code
export OMP_NUM_THREADS=2 && ./openmp_code
export OMP_NUM_THREADS=4 && ./openmp_code
export OMP_NUM_THREADS=8 && ./openmp_code
```

### MPI
```bash
# Run with different process counts (MSYS2 MinGW)
mpiexec -n 1 ./mpi_code
mpiexec -n 2 ./mpi_code
mpiexec -n 4 ./mpi_code
mpiexec -n 8 ./mpi_code
```

### CUDA
```bash
# Modify block size in source code before compilation
./cuda_code.exe
```

## Notes
- Matrix size N is defined in source code (default: 1000)
- For CUDA: Use N=5 for testing, N=1000 may cause memory issues
- All implementations use dynamic memory allocation
- Performance results will vary based on hardware specifications

## Hardware Requirements
- Minimum 8GB RAM for N=1000 matrix operations
- NVIDIA GPU with CUDA capability for CUDA implementation
- Multi-core processor recommended for OpenMP/MPI testing