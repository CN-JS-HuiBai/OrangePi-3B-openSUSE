**openSUSE For OrangePi 3B镜像存储仓库**

这里是用于存储FedoraLinux 38（Linux-6.6-MainLine内核） OrangePi 3B的镜像仓库，
该镜像目前已经可以提供UWE5622网卡的支持(蓝牙似乎没有正常运行)，但镜像默认不启用该部分模块，您可以通过以下命令启用：

```shell
modprobe lib80211
modprobe cfg80211
modprobe sprdwl_ng
```
该镜像默认使用的root账户的密码为orangepi(不支持ssh登录，镜像默认启用cockpit，可用root用户登录)

该镜像额外的管理员账户用户名为orangepi密码为orangepi

进入系统后可以使用以下命令来扩容根目录：

```shell
dnf install cloud-utils-growpart
growpart /dev/mmcblk1 3
resize2fs /dev/mmcblk1p3
