# 一些Linux使用技巧

## 非管理员用户如何替换系统旧版软件

```bash
在个人目录编译好新版软件之后，编辑$HOME/.bash_profile。添加export PATH=(新软件的bin所在目录，如$HOME/usr/bin):$PATH。这样便可实现“覆盖”系统已有软件。
```

<font color=red>需要留意：```$HOME/usr/bin:$PATH```和```$PATH:$HOME/usr/bin```的效果是不一样的！放在前面的优先级较高。<font color=red>

### error
*/2.6.37/include/linux/types.h:13:2: warning: #warning "Attempt to use kernel headers from user space, see http://kernelnewbies.org/KernelHeaders"

make headers_install INSTALL_HDR_PATH=$HOME/usr

调整后：selinux/selinux.h找不到，在configure选项上加 --without-selinux

* 由selinux引起的编译错误，都可以由此来解决。

### error relocation R_X86_64_32 against `.rodata.str1.1' can not be used when making a shared object; recompile with -fPIC

两种方式：

（1）在makefile文件里的CFLAGS里加上 -fPIC选项，这样可以一劳永逸

（2）如果你的makefile很大，CFLAGS也不明确，那就在配置时手动加上，即：

$CFLAGS="-fPIC" ./configure ..............

如果这样还不行，你需要试一下sudo

即：

$sudo   CFLAGS="-fPIC" ./configure ..............


### cmake is not able to find python-libraries

-DPYTHON_INCLUDE_DIR=$(python -c "from distutils.sysconfig import get_python_inc; print(get_python_inc())")  \
-DPYTHON_LIBRARY=$(python -c "import distutils.sysconfig as sysconfig; print(sysconfig.get_config_var('LIBDIR'))")

https://stackoverflow.com/questions/24174394/cmake-is-not-able-to-find-python-libraries
