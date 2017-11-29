# 设置静态IP  
sudo vim /etc/network/interfaces  
添加以下内容：  
auto eth0    其中，eth0为你的挂载的网卡名，如果不是这个名字，就换成对应的名字  
iface eth0 inet static  
address 192.168.0.1  
gateway 192.168.0.254  
netmask 255.255.255.0  
重启网络使上面配置生效：  
sudo /etc/init.d/networking restart  

给两个Ubuntu电脑设置好静态ip，就可以让他们使用一根网线通过socket直接通信了
