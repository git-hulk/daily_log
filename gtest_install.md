## gtest 编译安装

下面内容来自 [stackflow](http://stackoverflow.com/questions/13513905/how-to-properly-setup-googletest-on-linux), 这里记录只为了防止重复查找。

### 编译
```shell
$ cd gtest-1.7.0
$ ./configure
$ make
```

### 安装
gtest 本身没有自带 `make install` , 如果执行会得到下面的结果:

```
'make install' is dangerous and not supported. Instead, see README for how to integrate Google Test into your build system.
```

所以需要手动把头文件和动态库自己拷贝到默认查找路径
```shell
$ sudo cp -a include/gtest /usr/include
$ sudo cp -a lib/.libs/* /usr/lib/
```

### 使用

后面使用直接在编译指定 `-lgtest` 即可使用 gtest, 如果自己没有指定入口(main)，可以加上默认的入口，-lgtest_main 。
