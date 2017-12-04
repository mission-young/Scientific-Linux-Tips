# 一些Linux使用技巧

## 非管理员用户如何替换系统旧版软件

```bash
在个人目录编译好新版软件之后，编辑$HOME/.bash_profile。添加export PATH=(新软件的bin所在目录，如$HOME/usr/bin):$PATH。这样便可实现“覆盖”系统已有软件。
```

<font color=red>需要留意：```$HOME/usr/bin:$PATH```和```$PATH:$HOME/usr/bin```的效果是不一样的！放在前面的优先级较高。<font color=red>





