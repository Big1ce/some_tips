## Ubuntu 16.04 重置密码

### 1. 进入 GRUB 界面

		> 搜索到三种方法，分别为
		> 1. 开机时，长按 shift
		> 2. 开机时，长按 Esc
		> 3. 开机时，长按 e
		
		
	我尝试了第一种，在刚出现图形界面时，快速摁shift，成功进入 GRUB 界面。（但是会导致出现“粘滞键提示”）

**进入之后界面如下**：

![](https://img-blog.csdn.net/20180322215253143)


如果是英语系统则**Ubuntu 高级选项**显示为**Advanced options for Ubuntu**

### 2.选择 *Ubuntu 高级选项* 或 *Advanced options for Ubuntu*
	
> 摁**向下箭头**选择目标项,然后摁Enter进入

**进入之后界面如下**：

![](https://img-blog.csdn.net/20161213175947735)

### 3. 箭头向下选择带有 recovery mode 的那一项，摁“e” 进入编辑界面

**不要摁回车**

**不要摁回车**

**不要摁回车**


> 此时如果有两个 recovery mode, 选择哪个都可以
 
**进入之后界面如下**：

![](https://upload-images.jianshu.io/upload_images/3972299-948325eed4052bbd.png?imageMogr2/auto-orient/strip|imageView2/2/w/639/format/png)

### 4. 向下寻找 recovery nomodeset 字样，一般在倒数第四行

**实际界面如下**：

![](https://img-blog.csdn.net/20161213180034937)

### 5. 删除 recovery nomodeset ，并在本行末尾加上 quiet splash rw init=/bin/bash

> 注意有时recovery nomodeset后还有其他文本，一定要在本行末尾添加

![](https://img-blog.csdn.net/20180322220320326)

### 6. 摁F10启动系统

**进入之后界面如下**：

![](https://img-blog.csdn.net/20180322220649396)

> 上面的内容无所谓，最下面一行出现root@(none):/# 即可

### 7. 输入 *passwd 用户名*（用户名为你要找回密码的账户），然后摁 Enter

 > 注意此处的用户名不一定是你平时登陆界面的用户名，是终端中每条命令前的那个用户名

之后需要输入两次新密码，直接输入后回车即可，用户界面不显示明文和密文。

最后返回 password updated successfully ，表明重置密码成功。

### 8. 直接关机，重启

	这一步搜索时还看到了其他方法，但经过实测，直接关机就可以了。比如断电源或虚拟机直接关机。
