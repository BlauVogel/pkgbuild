- [hadoop - ArchWiki](<https://wiki.archlinux.org/index.php/Hadoop_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87)>)

```bash
$ sudo pacman -S jdk11-openjdk
$ sudo archlinux-java set java-11-openjdk # 设置默认 java 环境
$ makepkg -si

$ hadoop version
-- 输出的警告和错误 --
WARNING: HADOOP_SLAVES has been replaced by HADOOP_WORKERS. Using value of HADOOP_SLAVES.
ERROR: JAVA_HOME is not set and could not be found.

$ code /etc/hadoop/hadoop-env.sh
-- 编辑 --
export JAVA_HOME=/usr/lib/jvm/default

$ code /etc/profile.d/hadoop.sh
-- 编辑 --
export HADOOP_CONF_DIR=/etc/hadoop
export HADOOP_LOG_DIR=/tmp/hadoop/log
export HADOOP_WORKERS=/etc/hadoop/workers
export HADOOP_PID_DIR=/tmp/hadoop/run
-- 注销重新登录 --

$ hadoop version
-- 此时无警告和错误了 --
```
