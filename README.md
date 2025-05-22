# 安装Ubuntu环境

下载虚拟机软件，软件名称：VirtualBox，现在个人用的是6.1.50

下载乌班图ISO镜像，下载地址：https://releases.ubuntu.com/ ，现在个人用20.04.06版本

在VirtualBox软件中新建，类型为Linux，版本为Ububtu（64-bit），文件夹和名称随意，其他按路径操作完，记住要先把配置设置好，ISO镜像文件先配置好后再点击启动

安装好后共享文件夹需要下面的操作
执行以下命令：

```
sudo usermod -aG vboxsf $USER
```

这里 $USER 是当前登录的用户名。这条命令会将当前用户添加到 vboxsf 组中。
重启系统：用户组的更改在你重新登录或者重启系统后生效。你可以选择重启系统，或者通过以下命令重新登录：

```
su - $USER
```

检查共享文件夹的挂载：确认共享文件夹已成功挂载，可以通过以下命令检查：

```
mount | grep vboxsf
```

之后能看到成功了

配置git
首先安装git

```
sudo apt install git
```



```
cd /
mkdir .ssh/
```

把windows下面的id_rsa和id_rsa.pub放在Ubuntu的用户下面新建的.ssh/目录内，然后chmod 700 -R .ssh/*提权即可


# 开发编译环境配置

```
sudo apt-get update
sudo apt-get -y dist-upgrade
sudo apt-get clean
sudo apt-get autoremove
sudo apt install lzop
sudo apt install libsdl2-dev
sudo apt install nodejs npm
npm i lv_i18n -g

sudo apt-get install build-essential libc6-dev lib32ncurses5-dev libncurses5-dev libncurses5:i386 libgl1-mesa-dev g++-multilib mingw-w64 tofrodos lib32z1 u-boot-tools zlib1g-dev bison libbison-dev flex mtd-utils vim squashfs-tools gawk cmake cmake-data liblz4-tool libmpc3 libstdc++6 device-tree-compiler android-sdk-libsparse-utils android-sdk-ext4-utils texinfo python3-pyelftools python3-crypto libssl-dev
```

下载附件的文件，导入到至乌班图中进行解压
解压之前先创建下面的目录，使用指令

```
cd /
sudo mkdir /opt/ivot
sudo tar -jxvf aarch64-ca53-linux-gnueabihf-8.4.01.tar.bz2 -C /opt/ivot
```

变更Shell 的 symbolic link

```
sudo ls -l /bin/sh
sudo rm –rf /bin/sh
sudo ln -s /bin/bash /bin/sh
```

输入为/bin/bash代表编译SDK成功。
