Download link :https://programming.engineering/product/cuda-parallel-scan-work-efficient-prefix-sum-with-shared-memory/

# CUDA-Parallel-Scan-Work-Efficient-Prefix-Sum-with-Shared-Memory
CUDA Parallel Scan: Work-Efficient Prefix Sum with Shared Memory
If you have already checked out the repo before 10/20 8PM, you need to rerun `git pull` to make sure everything is up to date.

To submit your code, you need to run `rai -p ./MP6 –submit MP6`. To check your submission history, run `rai history -p ./MP6` (last 20 enties) or `rai l-history -p ./MP6` (last 100 enties).

Objective

The purpose of this lab is to implement one or more kernels and their associated host code to perform parallel scan on a 1D list. The scan operator used

will be addition. You should implement the work- efficient kernel discussed in lecture. Your kernel should be able to handle input lists of arbitrary length.

However, for simplicity, you can assume that the input list will be at most 2,048 * 2,048 elements.

Prerequisites

Before starting this lab, make sure that:

* You have completed all week 4 lecture videos

* You have completed all week 5 lecture videos

* You have completed the List Reduction Lab

Instruction

The boundary condition can be handled by filling ‘identity value (0 for sum)’ into the shared memory of the last block when the length is not a multiple of

the thread block size.

You will need to launch multiple kernels to complete the parallel scan as discussed in the lecture.

Edit the code in the code tab to perform the following:

* allocate device memory

* copy host memory to device

* initialize thread block and kernel grid dimensions

* invoke CUDA kernel

* copy results from device to host

* deallocate device memory

* implement the work-efficient scan kernel to generate per-block scan array and store the block sums into an auxiliary block sum array.

* use shared memory to reduce the number of global memory accesses, handle the boundary conditions when loading input list elements into the shared memory

* reuse the kernel to perform scan on the auxiliary block sum array to translate the elements into accumulative block sums. Note that this kernel will be launched with only one block.

* implement the kernel that adds the accumulative block sums to the appropriate elements of the per-block scan array to complete the scan for all the elements.

Instructions about where to place each part of the code is demarcated by the //@@ comment lines.

