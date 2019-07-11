# PyTorch_ONNX_TensorRT
A tutorial about how to build a TensorRT Engine from a PyTorch Model with the help of ONNX


# Environment
0. Ubuntu 16.04 x86_64, CUDA 10.0
1. Python 3.5
2. PyTorch 1.0 (https://pytorch.org/get-started/locally/)
3. TensorRT 5.0 (If you are using Jetson TX2, TensorRT will be already there if you have installed the jetpack)
3.1 Download TensorRT from https://developer.nvidia.com/tensorrt (The latest version is 5.1, you should pick up, yet 5.0 is used here. The pack should match your environment)
3.2 Debian installation
```
  $ sudo dpkg -i nv-tensorrt-repo-ubuntu1x04-cudax.x-trt5.x.x.x-ga-yyyymmdd_1-1_amd64.deb # The downloaeded file
  $ sudo apt-key add /var/nv-tensorrt-repo-cudax.x-trt5.x.x.x-gayyyymmdd/7fa2af80.pub
  $ sudo apt-get update
  $ sudo apt-get install tensorrt
  
  $ sudo apt-get install python3-libnvinfe # Install
```
To verify the installation of TensorRT
`$ dpkg -l | grep TensorRT`
You should see similar things like
```
  ii  graphsurgeon-tf	5.1.5-1+cuda10.1	amd64	GraphSurgeon for TensorRT package
  ii  libnvinfer-dev	5.1.5-1+cuda10.1	amd64	TensorRT development libraries and headers
  ii  libnvinfer-samples	5.1.5-1+cuda10.1	amd64	TensorRT samples and documentation
  ii  libnvinfer5		5.1.5-1+cuda10.1	amd64	TensorRT runtime libraries
  ii  python-libnvinfer	5.1.5-1+cuda10.1	amd64	Python bindings for TensorRT
  ii  python-libnvinfer-dev	5.1.5-1+cuda10.1	amd64	Python development package for TensorRT
  ii  python3-libnvinfer	5.1.5-1+cuda10.1	amd64	Python 3 bindings for TensorRT
  ii  python3-libnvinfer-dev	5.1.5-1+cuda10.1	amd64	Python 3 development package for TensorRT
  ii  tensorrt	5.1.5.x-1+cuda10.1	amd64	Meta package of TensorRT
  ii  uff-converter-tf	5.1.5-1+cuda10.1	amd64	UFF converter for TensorRT package
```

3.2 Install PyCuda (This will support TensorRT)
  ```
   $ pip3 install pycuda 
  ```
If you get problems with the that line of code, please try
 
 ```$ sudo apt-get install python3-pycuda #(Install for /usr/bin/python3)
 ```
For full details, Please check https://docs.nvidia.com/deeplearning/sdk/tensorrt-install-guide/index.html#uninstalling


# Usage
## Convert a PyTorch model to ONNX model
  Please check the file 'pytorch_2_onnx.py'
## Load a ONNX model with TensorRT API
  # Please check onnx 'onnx_2_tensorrt.py'
