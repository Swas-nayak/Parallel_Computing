# Parallel Computing Lab

This repository contains the practical programs and experiments for ** Parallel Computing **, covering **OpenMP** and **MPI** programming concepts.


## Experiments

### OpenMP Programs

1. **Sequential and Parallel Merge Sort**

   * Implement merge sort using both sequential and parallel approaches.
   * Use OpenMP `sections` for parallel execution.
   * Record and compare the execution times.

2. **OpenMP Static Scheduling**

   * Write an OpenMP program using `OMP_SCHEDULE=static,2`.
   * Divide loop iterations into chunks containing two iterations.
   * Display which iterations are executed by each thread.
   * Example:

     ```text
     Thread 0 : Iterations 0 -- 1
     Thread 1 : Iterations 2 -- 3
     ```

3. **Fibonacci Using OpenMP Tasks**

   * Calculate `n` Fibonacci numbers using OpenMP tasks.
   * Demonstrate task-based parallelism.

4. **Prime Numbers Using OpenMP**

   * Find prime numbers from `1` to `n` using the OpenMP `parallel for` directive.
   * Calculate and compare serial and parallel execution times.

### MPI Programs

5. **MPI_Send and MPI_Recv**

   * Demonstrate point-to-point communication using `MPI_Send` and `MPI_Recv`.

6. **MPI Deadlock and Avoidance**

   * Demonstrate deadlock using point-to-point communication.
   * Demonstrate deadlock avoidance by altering the communication call sequence.

7. **MPI Broadcast**

   * Demonstrate the broadcast operation using `MPI_Bcast`.

8. **MPI Scatter and Gather**

   * Demonstrate data distribution using `MPI_Scatter`.
   * Collect the results using `MPI_Gather`.

9. **MPI Reduce and Allreduce**

   * Demonstrate `MPI_Reduce` and `MPI_Allreduce`.
   * Perform the following operations:

     * `MPI_MAX`
     * `MPI_MIN`
     * `MPI_SUM`
     * `MPI_PROD`

## Technologies Used

* **C / C++**
* **OpenMP**
* **MPI**
* GCC / G++
* OpenMPI or MPICH

## OpenMP Compilation

Compile an OpenMP program using GCC:

```bash
gcc program.c -o program -fopenmp
```

Run:

```bash
./program
```

To specify the number of threads:

```bash
export OMP_NUM_THREADS=4
./program
```

For the static scheduling experiment:

```bash
export OMP_NUM_THREADS=2
export OMP_SCHEDULE="static,2"
./program
```

## MPI Compilation

Compile an MPI program using `mpicc`:

```bash
mpicc program.c -o program
```

Run with multiple processes:

```bash
mpirun -np 4 ./program
```

For example:

```bash
mpicc mpi_send_recv.c -o mpi_send_recv
mpirun -np 2 ./mpi_send_recv
```

## Suggested Repository Structure

```text
BCS702-PARALLEL-COMPUTING-LAB/
│
├── README.md
│
├── OpenMP/
│   ├── 01_parallel_mergesort.c
│   ├── 02_static_schedule.c
│   ├── 03_fibonacci_tasks.c
│   └── 04_parallel_primes.c
│
├── MPI/
│   ├── 05_send_recv.c
│   ├── 06_deadlock.c
│   ├── 07_broadcast.c
│   ├── 08_scatter_gather.c
│   └── 09_reduce_allreduce.c
│
└── screenshots/
```

