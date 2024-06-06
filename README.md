# Test repo for gpu integration with nanos


## Build environment

- Ubuntu 22.04 (5.15.0-107-generic)
- Cuda 12.4.1
- Nvidia driver 550.54.15
- gpu_nvidia [main/e8534f0](https://github.com/nanovms/gpu-nvidia/commit/e8534f04869d728e76a4c35e2fa12b2301f550f9)

## Run deviceQuery in nanos
```
ops run -n -c ./manifest.json ./deviceQuery
```

Running this command on my machine gives the following error:
```
NVRM _sysCreateOs: RM Access Sys Cap creation failed: 0x56
NVRM: loading NVIDIA UNIX Open Kernel Module for x86_64  535.113.01  Release Build  (root@ipfs)  Tue Jun  4 01:42:09 PM CST 2024
Loaded the UVM driver, major device number 0.
deviceQuery Starting...

 CUDA Device Query (Runtime API) version (CUDART static linking)

cudaGetDeviceCount returned 304
-> OS call failed or operation not supported on this OS
Result = FAIL
```


## Run deviceQuery in nano and enable trace
```
ops run --trace -n -c ./manifest.json ./deviceQuery
```

## trace log

### linux
[linux_trace.log](./linux_trace.log)

### nanos
[nanos.log](./nanos_trace.log)
