# Installation Guide

## 1. Preparation

### 1.1 Download source code

	cd ~
	
	git clone --recursive gitlab@219.139.34.186:openailab/tengine.git

### 1.2 Prepare makfile.config

	cd ~/tengine
	
	cp makefile.config.example makefile.config

Then edit makefile.config according to your requirements. 

### 1.3 Prepare caffe

If you are not on an arm64 target, it is necessary to build [Caffe](https://github.com/BVLC/caffe) or [CaffeOnACL](https://github.com/OAID/CaffeOnACL), and set the path of caffe to `CAFFE_ROOT` in makefile.config.<br>
For example:

>CAFFE_ROOT = /home/firefly/caffe

## 2. Build

	cd ~/tengine
	
	make
	make test

`make test` is optional, 

## 3. Test
Please refer to [benchmark](./benchmark.md).
