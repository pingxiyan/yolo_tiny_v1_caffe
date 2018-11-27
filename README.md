# yolo_tiny_v1_caffe
~~~
	refer:
	1.
	2.

	Modification: activation layer "leaky -> relu"
~~~

# dependency

## 1. CAFFE, CUDA 9.2
~~~
  $ git clone https://github.com/BVLC/caffe.git
  $ cd caffe
  $ git checkout 99bd99795dcdf0b1d3086a8d67ab1782a8a08383
  $ mkdir build
  $ cmake -DCUDA_TOOLKIT_ROOT_DIR=/usr/local/cuda-9.2 ..
  $ make -j
~~~


