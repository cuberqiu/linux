# 在Ubutntu17.04上配置tensorflow

## 安装CUDA Toolkit
1. 在官网下载cuda toolkit : [下载](https://developer.nvidia.com/cuda-downloads)  

2. 切换到下载文件的目录：   
`sudo dpkg -i   cuda-repo-ubuntu1604-8-0-local-ga2_8.0.61-1_amd64.deb`  
`sudo apt-get update`  
`sudo apt-get install cuda`  
注意：如果最后提示uefi secure boot enable的话，重启电脑，进入bios，关闭scure boot即可。  

3. 添加环境变量  
`export PATH=/usr/local/cuda-8.0/bin${PATH:+:${PATH}}`  
此处安装时要根据自己的cuda版本来，最好是自己手打，不要复制粘贴，容易添加环境变量出错。  

4. 编译cuda samples  
进入到samples 文件夹，make -j即可。  
编译成功后，会生成/usr/local/cuda-8.0/samples/bin/x86_64/linux/release文件夹，里面都是编译好的可执行文件，./deviceQuery可以运行测试。

## 安装cudnn for cuda8.0
1. 官网下载：[download](https://developer.nvidia.com/rdp/cudnn-download)  
2. 解压  
 `sudo cp cuda/include/cudnn.h /usr/local/cuda-8.0/include/`   
 `sudo cp cuda/lib64/libcudnn* /usr/local/cuda-8.0/lib64/`  
 `sudo chmod a+r /usr/local/cuda-8.0/incude/cudnn.h`   
 `sudo chmod a+r /usr/local/cuda-8.0/lib64/libcudnn*`   
3. 配置环境变量：  
  vim ~/.bashrc  
  添加以下内容：  
  export LD_LIBRARY_PATH="$LD_LIBRARY_PATH:/usr/local/cuda-8.0/lib64:/usr/local/cuda-8.0/extras/CUPTI/lib64"  
export CUDA_HOME=/usr/local/cuda

## 安装tensorflow
1. Install pip and virtualenv by issuing the following command:  
`$ sudo apt-get install python-pip python-dev python-virtualenv`
2. Create a virtualenv environment by issuing the following command:  
`$ virtualenv --system-site-packages targetDirectory`
3. The targetDirectory specifies the top of the virtualenv tree. Our instructions assume that targetDirectory is ~/tensorflow, but you may choose any directory.
Activate the virtualenv environment by issuing one of the following commands:  
 `$ source ~/tensorflow/bin/activate # bash, sh, ksh, or zsh`
 `$ source ~/tensorflow/bin/activate.csh  # csh or tcsh`  
4. Issue one of the following commands to install TensorFlow in the active virtualenv environment:
`(tensorflow)$ pip install --upgrade tensorflow      # for Python 2.7`  
 `(tensorflow)$ pip install --upgrade tensorflow-gpu  # for Python 2.7 and GPU`

 上诉安装完成之后在tensorflow激活的状态下，执行：  
pip install jupyter  
pip install ipython  
可以让tensorflow在jupyter notebook 中使用。  
注意，在用atomn作为编辑器时，也需要在tensorflow被激活的情况下打开atom才能识别到trensorflow库。
