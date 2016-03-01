# code-experience
The  Programming experience
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
```
from pyspark import SparkContext, SparkConf
from pyspark.sql import SQLContext

conf = (SparkConf()
    .set("spark.driver.maxResultSize", "2g"))
sc = SparkContext(conf=conf)
sqlc = SQLContext(sc)
```
linux和windows系统不同，linux不会产生无用垃圾文件，但是在升级缓存中，linux不会自动删除这些文件，还是很占硬盘的！

##一、删除缓存

###1，非常有用的清理命令：
```sudo apt-get autoclean    ```            
清理旧版本的软件缓存

```sudo apt-get clean   ```                
清理所有软件缓存

```sudo apt-get autoremove ```        
删除系统不再使用的孤立软件

这三个命令主要清理升级缓存以及无用包的。

###2，清理opera firefox的缓存文件：
```ls ~/.opera/cache4```
```ls ~/.mozilla/firefox/*.default/Cache```

###3，清理Linux下孤立的包：
终端命令下我们可以用：
```sudo apt-get install deborphan -y```

###4，卸载：tracker
这个东西一般我只要安装ubuntu就会第一删掉tracker 他不仅会产生大量的cache文件而且还会影响开机速度。所以在新得利里面删掉就行。

附录：
包管理的临时文件目录:包在
```
/var/cache/apt/archives
```
没有下载完的在：
```/var/cache/apt/archives/partial
   ```

##二、删除软件

ubuntu软件的删除一般用“ubuntu软件中心”或“新立得”就能搞定，但有时用命令似乎更快更好～～
```sudo apt-get remove --purge ```软件名
```sudo apt-get autoremove ```         删除系统不再使用的孤立软件
```sudo apt-get autoclean  ```          清理旧版本的软件缓存
```dpkg -l |grep ^rc|awk '{print $2}' |sudo xargs dpkg -P ```  清除残余的配置文件

保证干净。

##三、删除多余内核

###1，首先要使用这个命令查看当前Ubuntu系统使用的内核
```uname -a```

###2，再查看所有内核
```dpkg --get-selections|grep linux```

###3，最后小心翼翼地删除吧
```sudo apt-get remove linux-image-2.6.32-22-generic```

####ps：linux-image-xxxxxx-generic    就是要删除的内核版本
还有
```
linux-headers-xxxxxx
linux-headers-xxxxxx-generic
```
总之中间有“xxxxxx”那段的旧内核都能删，注意一般选内核号较小的删
