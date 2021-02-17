
# SYCL for Nvidia Exercises

These exercises introduce the CUDA backend of the DPC++ SYCL compiler and runtime.


# Prerequisites

The [NVIDIA Container Toolkit](https://github.com/NVIDIA/nvidia-docker) must be installed to run the image.

These examples are intended to be used with this [docker image](https://hub.docker.com/r/ruyman/dpcpp_cuda_examples). 
It provides all the examples, libraries and the required environment variables. 

A useful guide for setting up docker and the NVIDIA Container Toolkit can be found [here](https://www.pugetsystems.com/labs/hpc/Workstation-Setup-for-Docker-with-the-New-NVIDIA-Container-Toolkit-nvidia-docker2-is-deprecated-1568).

Getting Started
-------------

Once docker and the NVIDIA Container Toolkit are installed, we can create a new container and run the examples witin it.

``` sh
$ sudo docker run --gpus all -it ruyman/dpcpp_cuda_examples
```

Once inside the docker image, navigate to `/home/` and clone the exercises repository:

``` sh
$ git clone https://github.com/codeplaysoftware/dpcpp-workshop.git
$ cd dpcpp_workshop/exercises
```

Refer to each example and/or exercise for detailed instructions on how  to run it.


---

## Exercise 1 - Using the CUDA backend
In the first exercise you will learn how to select a CUDA device for a SYCL queue and verify that your application running on a CUDA device. You will also implement a simple vector addition kernel and verify the results are correct running on the CUDA device.

[Exercise 1 Instructions](https://github.com/codeplaysoftware/dpcpp-workshop/tree/master/exercises/Exercise1_Using_the_CUDA_Backend)

## Exercise 2 - Calling cuBLAS sgemm from a SYCL command group
The second exercise introduces SYCL interoperability with CUDA libraries. You will need to implement a command group that calls `cublasSgemm`. In order to achieve this, you will use the `interop_task` interface, and will have to retrieve native CUDA memory handles from the SYCL runtime API to pass to `cublasSgemm`.

[Exercise 2 Instructions](https://github.com/codeplaysoftware/dpcpp-workshop/tree/master/exercises/Exercise2_Using_CUBLAS_in_SYCL)

## Exercise 3 - Calling a native CUDA kernel from a SYCL command group
The third exercise introduces SYCL interoperability with native CUDA kernels. You will need to implement a command group that calls a provided CUDA kernel. To do this you will use the `interop_task` interface, and similarly to exercise 2, you will have to retrieve native CUDA memory handles to pass to the CUDA kernel.

[Exercise 3 Instructions](https://github.com/codeplaysoftware/dpcpp-workshop/tree/master/exercises/Exercise3_Calling_CUDA_kernels_in_SYCL)

## Exercise 4 - Porting CUDA to SYCL
In the fourth and final exercise, you will need to port some CUDA code to SYCL. The CUDA application implements a simple matrix multiplication.

[Exercise 4 Instructions](https://github.com/codeplaysoftware/dpcpp-workshop/tree/master/exercises/Exercise4_Porting_CUDA_to_SYCL)

---
