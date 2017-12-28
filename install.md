# Installation Guide

This guide page gives instructions on how to build and test TEngine on your system.

## 1. Preparation

### 1.1 Download source code

To get started, clone the latest TEngine repository. <br>
It is important to specify the `--recursive` option to clone the submodules along.

	cd ~
	
	git clone --recursive gitlab@219.139.34.186:openailab/tengine.git

### 1.2 Prepare config files

	cd ~/tengine
	
	cp makefile.config.example makefile.config
	
	cp etc/config.example etc/config

Then edit `makefile.config` and `etc/config` according to your specific requirements.

### 1.3 Prepare caffe (Optional)

If you want to use caffe's operators in TEngine, please build [Caffe](https://github.com/BVLC/caffe) or [CaffeOnACL](https://github.com/OAID/CaffeOnACL) in advance and set the path of caffe to `CAFFE_ROOT` in `makefile.config`.<br>
For example:

	CONFIG_CAFFE_REF=y
	CAFFE_ROOT = /home/firefly/caffe

## 2. Build

	cd ~/tengine
	
	make
	
	make test (Optional)

`make test` is executed when you need to build and run some additional test programs in the project.

## 3. Run tests

TEngine also provides you some example programs for tests, and you can easily validate whether your TEngine is successfully built by running them.

### 3.1 Run SqueezeNet

	cd ~/tengine
	
	./build/tests/bin/test_sqz

Output message:

	0.2763 - "n02123045 tabby, tabby cat"
	0.2673 - "n02123159 tiger cat"
	0.1766 - "n02119789 kit fox, Vulpes macrotis"
	0.0827 - "n02124075 Egyptian cat"
	0.0777 - "n02085620 Chihuahua"

### 3.2 Run MobileNet

	cd ~/tengine
	
	./build/tests/bin/test_sqz

Output message:

	8.5976 - "n02123159 tiger cat"
	7.9550 - "n02119022 red fox, Vulpes vulpes"
	7.8679 - "n02119789 kit fox, Vulpes macrotis"
	7.4274 - "n02113023 Pembroke, Pembroke Welsh corgi"
	6.3647 - "n02123045 tabby, tabby cat"

For more information about the performance test of TEngine, please refer to the documentation of [benchmark](benchmark.md).
