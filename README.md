# Google Summer of Code 2022: HSF EIC ATHENA Clustering on GPUs

## Warm-up Exercise

For this practice exercise you will be using Intel's oneAPI DPC++. To submit your results, create a repository where you add the files with a suitable organizational structure (public or private with the two mentors added with user names @wdconinc and @sly2j).

### Setup

Install Intel oneAPI DPC++ on a system you have access to (both command line and IDE are acceptible, but at least some familiarity with linux command line operation of dpcpp will be necessary for the project). For some profiling tasks you will benefit from a system to which you have administrator access.

Locate and explore the Intel oneAPIs example codes for vector addition (`vector-add`) and matrix multiplication (`matrix_mul`). Both are available in oneapi-cli or as part of the oneapi-samples repository.

### Exercises

You may elect to complete not all of these parts, at your discretion.

1. Demonstrate with output logs (in properly formatted markdown in your repository) that you can compile and execute the vector addition and matrix multiplication examples. (Ignore openMP operation; focus on DPC++ only.)

2. Modify the matrix multiplication example to increase the problem size for matrix multiplication by a factor 10. Modify the SYCL queues to use at least one hardware resource selector that is not the default (depending on your hardware). Assess the impact of changing the selected hardware resources with a simple timing tool like `multitime`, add the output logs to your repository, and discuss your observations.

3. Write a new example that calculates the bilinear quadratic form `v^T*b*v` of an N-dimensional column vector v over a square symmetric N-dimensional matrix b. For definiteness, use vector `v[i] = i` and `b[i,j] = i+j`, for i,j = 0,...,N-1. As in the provided samples above, your code must calculate the quantity twice, once with SYCL and once without, and compare the result for correctness. Upload your code and a Makefile to compile the code. (Keeping in mind part 4 below, your code does not need to be optimal.)

4. Analyze your implementation in part 3 in VTune. Identify any areas for improvement. Using VTune screenshots, justify one to three areas of improvement that you would explore next.
