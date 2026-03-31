# VPLC_Motion_Kernel
x86_Linux内核优化 、适用于Phoenix  Virtual PLCnext Control Motion

## 准备

当前脚本在不需要修改的情况下支持帮用户一键化部署 Linux6.8.2 rt补丁，同时进行相关性能优化：

该脚本仅支持 **x86-Linux（Ubuntu22.04以上）**；

如果需要Arm版本优化和运控适配需要联系菲尼克斯电气：

suntao@phoenixcontact.com.cn；

xupeiwen@phoenixcontact.com.cn；

在进行内核编译的时候需进行6.8.2的内核下载

**下载地址：**

内核下载路径

[Index of /pub/linux/kernel/v6.x/](https://cdn.kernel.org/pub/linux/kernel/v6.x/)

下载内核 linux-6.8.2.tar.xz

https://cdn.kernel.org/pub/linux/kernel/v6.x/linux-6.8.2.tar.xz

补丁下载地址：

[Index of /pub/linux/kernel/projects/rt/6.8/](https://cdn.kernel.org/pub/linux/kernel/projects/rt/6.8/)

下装补丁 patch-6.8.2-rt11.patch.xz

https://cdn.kernel.org/pub/linux/kernel/projects/rt/6.8/patch-6.8.2-rt11.patch.xz

(如果用户需要其他内核版本请修改脚本)

## 使用

将 vplc-installer.run 脚本和 patch-6.8.2-rt11.patch.xz  linux-6.8.2.tar.xz 放在同一个文件夹下面

执行

```
 ./vplc-installer.run --kernel
```

注意：如果电脑中没有cmake 、gcc等软件则需要联网采购执行下去



**该脚本支持的功能**

```
| 示例                                                            | 说明            |
| ------------------------------------------------------------- | ------------- |
| sudo ./vplc-installer.run --kernel                            | 编译并安装实时内核     |
| sudo ./vplc-installer.run --atemsys                           | 编译 atemsys 驱动 |
| sudo ./vplc-installer.run --auto                              | 自动模式          |
| sudo ./vplc-installer.run --unbind --iface enp2s0             | 解绑网卡          |
| sudo ./vplc-installer.run --unbind --iface enp2s0 --permanent | 永久解绑网卡        |
| sudo ./vplc-installer.run --bind --iface enp2s0               | 绑定网卡          |
| sudo ./vplc-installer.run --isolcpus --cpus 2,3               | CPU 隔离        |
| sudo ./vplc-installer.run --view                              | 查看系统配置        |
| sudo ./vplc-installer.run --nic-list                          | 查看网卡列表        |
| sudo ./vplc-installer.run --extract                           | 解压安装文件        |

```

