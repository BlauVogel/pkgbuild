- [hadoop - ArchWiki](<https://wiki.archlinux.org/index.php/Hadoop_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87)>)

```bash
# 安装 jdk8
$ sudo pacman -S jdk8-openjdk
# 设置默认 java 环境
$ sudo archlinux-java set java-8-openjdk
# 设置打包者的信息
$ echo 'PACKAGER="hyuuko <hyuukolin@outlook.com>"' > ~/.makepkg.conf
# 构建软件包，并且自动用 pacman 安装依赖、自动安装构建好软件包
$ makepkg -si
# 测试
$ hadoop version
-- 输出的警告和错误 --
ERROR: JAVA_HOME is not set and could not be found.

$ code /etc/hadoop/hadoop-env.sh
-- 编辑 '# export JAVA_HOME=' 这一行 --
export JAVA_HOME=/usr/lib/jvm/default

$ hadoop version
Hadoop 3.3.0
Source code repository https://gitbox.apache.org/repos/asf/hadoop.git -r aa96f1871bfd858f9bac59cf2a81ec470da649af
Compiled by brahma on 2020-07-06T18:44Z
Compiled with protoc 3.7.1
From source with checksum 5dc29b802d6ccd77b262ef9d04d19c4
This command was run using /usr/lib/hadoop-3.3.0/share/hadoop/common/hadoop-common-3.3.0.jar
```
