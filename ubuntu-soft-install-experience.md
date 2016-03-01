# code-experience
The  Programming experience
'''
import readline, rlcompleter; readline.parse_and_bind("tab: complete")
'''

## cuda 安装
下载对应的*.deb*文件
```
sudo dpkg -i cuda-repo-<distro>_<version>_<architecture>.deb
sudo apt-get update
sudo apt-get install cuda
sudo reboot
```

## python 依赖环境
```
sudo apt-get install python2.7-dev build-essential libssl-dev libevent-dev libjpeg-dev libxml2-dev libxslt-dev
sudo apt-get install libpng-dev libjpeg8-dev libfreetype6-dev
sudo apt-get install gfortran libopenblas-dev liblapack-dev
```

## pip 安装
下载[get-pip.py](https://bootstrap.pypa.io/get-pip.py)
```
sudo python get-pip.py
```

## python package 安装
```
sudo pip install numpy scipy matplotlib ipython seaborn scikit-learn
```

## pycharm 安装
下载[pycharm5.01](https://www.jetbrains.com/pycharm/download/)
进入pycharm/bin目录
```
./pycharm.sh
```
如果报错
```
sudo apt-get install openjdk-7-jdk
./pycharm.sh
```
注册方法:在注册时选择License server，填 http://idea.lanyus.com ，然后点击OK

## spark 配置
```
gedit ~/.bashrc
export PATH=$PATH:/home/your_name/spark-1.5.2-bin-hadoop2.6/bin
```
