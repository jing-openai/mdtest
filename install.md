# Installation Guide

## 1. Preparation

### 1.1 Download source code

	cd ~
	
	git clone --recursive gitlab@219.139.34.186:openailab/tengine.git

### 1.2 Prepare makfile.config

	cd ~/tengine
	
	cp makefile.config.example makefile.config

Then edit makefile.config according to your requirements. 

### 1.3 Prepare caffe (Optional)

If you want to use caffe's operators, build [Caffe](https://github.com/BVLC/caffe) or [CaffeOnACL](https://github.com/OAID/CaffeOnACL), and set the path of caffe to `CAFFE_ROOT` in `makefile.config`.<br>
For example:

	CAFFE_ROOT = /home/firefly/caffe

## 2. Build

	cd ~/tengine
	
	make
	
	make test (Optional)

`make test` is executed when you need to build and run some additional test programs in the project.

## 3. Test
Please refer to the documentation of [benchmark](./benchmark.md).
