# bgnode
start N-blog
## 安装nodejs

linux上使用远吗编译安装

```
curl -O https://nodejs.org/dist/v6.9.1/node-v6.9.1.tar.gz
tar -xzvf node-v6.9.1.tar.gz
cd node-v6.9.1
./configure
make
make install
```
这个我没试过 我是直接`tar -xzvf`之后直接用`ln -s /usr/local/nodejs/bin/node /usr/local/bin`

###1.1.2 n和nvm

看着nvm挺眼熟,npm是不是,一个是package管理,一个是version管理,管理的是nodejs的版本哦


  *  安装简易度。nvm 安装起来显然是要麻烦不少；n 这种安装方式更符合 node 的惯性思维。见仁见智吧。
  *  系统支持。注意， nvm 不支持 Windows。
  *  对全局模块的管理。n 对全局模块毫无作为，因此有可能在切换了 node 版本后发生全局模块执行出错的问题；nvm 的全局模块存在于各自版本的沙箱中，切换版本后需要重新安装，不同版本间也不存在任何冲突。
  *  关于 node 路径。n 是万年不变的 /usr/local/bin；nvm 需要手动指定路径。



### 1.1.3 nrm resource源的管理

这个你用了才知道以前cnpm那么装上去根本就是多次一句,直接用这个nrm多好

```
全局安装
npm i nrm -g

查看各种源的npm命令替代集合
nrm ls

切换用use
nrm use cnpm
```

这里我安装完nrm后出现2个问题,首先是因为之前我是用ln -s 这种方法添加到`/usr/local/bin`中的npm和node所以这个有问题了,这个nrm全局安装后还是在`/usr/local/nodejs/bin`中,所以又要一次`ln -s`
因该用PATH来添加到全局变量中,这样不用每次都ln
还有就是我安装完后就算到了这么做了,`nrm`也启动不了.

解决办法:

```
export PATH=/usr/local/nodejs/bin:$PATH
这个方法添加就没事了,可以找到nrm 所以还是别用ln -s添加
```
