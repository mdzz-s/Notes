# CentOs mimimal版本安装后，常用软件的安装

- jdk：java语言安装包

  ​	`yum install -y java-1.8.0-openjdk-devel.x86_64` 

- Vim ：Linux文本编译工具

  ​	`yum -y install vim-enhanced`

  ​	`yum -y install vim-common`

  ​	`yum -y install vim-minimal `

- Net-toos：linux网络配置工具

  ​	`yum install net-tools`

- Wget：linux从网络下载文件工具

  ​	`yum -y install wget`

- Unzip：linux解压zip包的工具

  ​	`yum install -y unzip zip`

- tar:建立,还原备份文件的工具

  ​	`yum install -y tar`

- make指令:yum -y install make

- Python：

  - Gcc:Linux的变成语言编译器

    `yum -y install gcc`

  - Other:其他安装软件 

    ​	`yum -y install zlib-devel bzip2-devel openssl-devel ncurses-devel sqlite-devel readline-devel tk-devel gdbm-devel db4-devel libpcap-devel xz-devel libffi-devel`

    > 安装这些软件时需要的问题No match for argument: xxx，源有问题，解决方案看这里https://fedoraproject.org/wiki/EPEL。 (db4-devel安装不上，跳过)

  - 下载python：wget https://www.python.org/ftp/python/3.7.0/Python-3.7.0.tgz

  - 解压：tar -zxvf Python-3.7.0.tgz

  - 创建目录：mkdir /usr/local/python3

  - 配置python`./configure --prefix=/usr/local/python3 --enable-shared CFLAGS=-fPIC`

  - Python目录下执行`make `

  - Python目录下执行`make install `

  - 修改python库路径`vim /etc/ld.so.conf.d/python3.conf` 添加`**/usr/local/python3/lib`   使用`ldconfig`使配置生效

  - 建立软连接,同时配置到了环境变量中

    `ln -s /usr/local/python3/bin/python3.7 /usr/bin/python3`

    `ln -s /usr/local/python3/bin/pip3.7 /usr/bin/pip3`

  - 查询版本号安装PIP

    ​	`python3 -V` 返回`Python 3.7.0`

    升级pip：`pip3 install *--upgrade pip`

    安装pymssql：`pip3 install "pymssql<3.0"`

  



