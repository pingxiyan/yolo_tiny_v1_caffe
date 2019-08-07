# yolo_tiny_v1_caffe
~~~
refer:
  1.https://github.com/pjreddie/darknet
  2.https://raw.githubusercontent.com/pjreddie/darknet/61c9d02ec461e30d55762ec7669d6a1d3c356fb2/cfg/yolov1-tiny.cfg
~~~
  Modification: activation layer "leaky -> relu"

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

# yolov2-tiny convert to CAFFE Guide

#### GetModel
	
	$ wget https://raw.githubusercontent.com/pjreddie/darknet/master/cfg/yolov2-tiny-voc.cfg
	$ wget https://pjreddie.com/media/files/yolov2-tiny-voc.weights 

#### Convert Tool

	$ git clone https://github.com/marvis/pytorch-caffe-darknet-convert.git
	$ git checkout 08d5418af0ad5fb744d0fe8c0ab229a0deca5c29
	
	Some dependency
	sudo apt-get install python-skimage
	sudo -E pip install torch
	pip install protobuf

#### Need caffe

	build yourcaffe 
  	$ git clone https://github.com/BVLC/caffe.git
  	$ cd caffe
  	$ git checkout 99bd99795dcdf0b1d3086a8d67ab1782a8a08383
  	$ mkdir build
  	$ cmake -DUSE_OPENCV=OFF -DCPU_ONLY=ON ..
  	$ make all -j30

	$ export PYTHONPATH=$PYTHONPATH:<PATH>/caffe/python

#### Convert

	$ python darknet2caffe.py ../yolov2-tiny-voc.cfg ../tiny-yolo-voc.weights tiny-yolo-voc.prototxt tiny-yolo-voc.caffemodel

	You will see:
	tiny-yolo-voc.prototxt
	tiny-yolo-voc.caffemodel

	Note: "yolo_tiny_v2_retrain/model/*" maybe is ok (Convert to Caffemodel)

