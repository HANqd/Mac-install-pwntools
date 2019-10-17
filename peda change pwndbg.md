<p>最近做题遇到了PIE保护，用之前的gdb-peda就不好调试了，这里安装了pwndbg。然而却不是怎么好装。期间出错了几次，发现是python版本的问题，后来又重新安了一遍,自动给安装了相应的python及pip。</p>
<p>安装网上可以找到，这里记录一下由peda转换为pwndbg的方法</p>
在终端输入：sudo nano ./.gdbinit</pr>
然后把其他gdb方式用井号注释掉即可。</pr>
如果没有source /home/yourname/pwndbg/gdbinit.py，则把他加上。</pr>
ctrl+x保存更改，回车退出即可。
