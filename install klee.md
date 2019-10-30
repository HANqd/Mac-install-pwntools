# 安装klee
## 1. 安装依赖
$ sudo apt-get install build-essential curl libcap-dev git cmake libncurses5-dev python-minimal python-pip unzip libtcmalloc-minimal4 libgoogle-perftools-dev libsqlite3-dev doxygen</br>
$ pip install tabulate</br>
$ sudo apt-get install clang-6.0 llvm-6.0 llvm-6.0-dev llvm-6.0-tools </br> 
## 安装z3
$ git clone https://github.com/Z3Prover/z3.git</br>
$ cd z3</br>
$ CXX=clang++-6.0 CC=clang-6.0 python scripts/mk_make.py</br>
$ cd build</br>
$ make</br>
$ sudo make install</br>
退出z3的文件夹再安装下边的。</br>
## 安装uclibc   
$ git clone https://github.com/klee/klee-uclibc.git  </br>
$ cd klee-uclibc </br>
修改configure文件中llvm-config的绝对路径。命令：vim configure ，然后把llvm-configure的路径那里改为llvm-configure-6.0（在配置文件中的位置比较靠后）</br>
$ CC=/usr/bin/clang-6.0 ./configure --make-llvm-lib --enable-assertions --with-llvm-config /usr/bin/llvm-config-6.0  </br>
$ make -j2  </br>
$ cd .. (退出uclibc安装文件）</br> 
## 获取google测试源码
$ curl -OL https://github.com/google/googletest/archive/release-1.7.0.zip </br>
$ unzip release-1.7.0.zip</br>
## 安装lit
$ pip install lit </br>
## 获取klee
$ git clone https://github.com/klee/klee.git</br>
## build klee
$ mkdir build</br>
$ cd build</br>
$ cmake -DENABLE_SOLVER_Z3=ON -DENABLE_POSIX_RUNTIME=ON -DENABLE_KLEE_UCLIBC=ON -DKLEE_UCLIBC_PATH=/home/ubuntu/klee-uclibc -DENABLE_UNIT_TESTS=ON -DENABLE_SYSTEM_TESTS=ON -DGTEST_SRC_DIR=/home/ubuntu/googletest-release-1.7.0 -DLLVM_CONFIG_BINARY=/usr/bin/llvm-config-6.0 -DLLVMCC=/usr/bin/clang-6.0 -DLLVMCXX=/usr/bin/clang++-6.0 /home/ubuntu/klee/</br>
## 如果有上述错误：下载zlib
$ sudo apt-get install zlib1g-dev</br>
安装后再重新编译cmake那句，成功后输入make，和sudo make install即可 </br>

