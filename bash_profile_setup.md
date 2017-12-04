# 配置~/.bash\_profile

```bash
# .bash_profile

# Get the aliases and functions
if [ -f ~/.bashrc ]; then
        . ~/.bashrc
fi

# User specific environment and startup programs

PATH=$HOME/usr/bin:$HOME/sbin:$HOME/bin:$HOME/x86_64-pc-linux-gnu/bin:$PATH

export PATH

#LD_LIBRARY_PATH=$HOME/usr/lib:$HOME/usr/lib64
#export LD_LIBRARY_PATH

LD_RUN_PATH=$LIBDIR:$LD_RUN_PATH
export LD_RUN_PATH

RPM_BUILD_ROOT=$HOME
export RPM_BUILD_ROOT 

RPM_BUILD_DIR=$HOME/usr/src/redhat/BUILD
export RPM_BUILD_DIR
```



