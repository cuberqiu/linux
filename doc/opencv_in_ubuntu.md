# Ubuntu下安装Opencv3.2
下载opencv2.0 : [下载地址](http://opencv.org/releases.html)  
![](https://github.com/CraftHeart/Linux-Study/blob/master/picture/1.png)
1. 安装依赖包  
[compuiler] sudo apt-get install build-essential  
[required] sudo apt-get install cmake git libgtk2.0-dev pkg-config libavcodec-dev libavformat-dev libswscale-dev  
[optional] sudo apt-get install python-dev python-numpy libtbb2 libtbb-dev libjpeg-dev libpng-dev libtiff-dev libjasper-dev libdc1394-22-dev  

2. 编译安装过程  
解压下载的包,cd 进去，然后mkdir release , cd release.  
开始编译：  
cmake -D CMAKE_BUILD_TYPE=RELEASE -D CMAKE_INSTALL_PREFIX=/usr/local ..  
make或者make -j
sudo make install

3. 使得动态库链接生效  
sudo vim /etc/ld.so.conf  
添加 /usr/local/lib  
sudo ldconfig -v

4. 查看opencv对应的库文件
pkg-config --cflags --libs opencv
