# Mac-install-pwntools
在Mac上安装pwntools时，遇到了很多问题，安了好几天，这里记录一下安装步骤，以防以后用到。
## 先安装以下环境
sudo apt-get install libffi-dev</br>
sudo apt-get install libssl-dev</br>
sudo apt-get install python3</br>
sudo apt-get install python3-pip</br>

## 在安装pwntools时首先安装Capstone
命令：</br>
git clone https://github.com/aquynh/capstone </br>
cd capstone</br>
make</br>
make install</br>
若安装出错，则在git安装之前加上以下命令：</br>
git config --global http.postBuffer 1048576000  </br>
即扩大存储大小</br>
安装成功</br>

## 安装pwntools
这一步安了很多次，经常出现错误，有一晚安到了凌晨两点多。。。。。，终于通过海搜，找到了解决办法！！！！
命令：</br>
pip3 install pwntools -i https://pypi.douban.com/simple/ --trusted-host=mirrors.aliyun.com
最后安装出错，加上 --user即可</br>
pip3 install pwntools -i https://pypi.douban.com/simple/ --trusted-host=mirrors.aliyun.com --user</br>

## 检验是否安装成功
在安装的文件夹下打开终端，输入python3（这里我用的python3-pip安装的上述环境，所以要用python3），在输入import pwn，如未报错误，则安装成功。



