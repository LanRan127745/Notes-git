# GItHub教程 SSH Keys配置

### SSH为Secure Shell的缩写，是建立在应用层和传输层基础上的安全协议  

<br>

### SSH特点

​    1、加密：通过使用SSH，可以将所有传输的数据进行加密，可以防止DNS欺骗和IP欺骗。

​	2、数据压缩：传输的数据是经过压缩的，所以可以加快传输速度  

<br>

### 传统的网络服务程序

- 如FTP、Pop和Telnet在传输机制和实现原理上是没有考虑安全机制的，其本质上都是不安全的；

- 因为它们在网络上用明文传送数据，别有用心的人通过窃听等网络攻击手段可以很容易地截获这些数据；
- 这些网络服务程序的简单安全验证方式的弱点：很容易受到"中间人"这种攻击方式的攻击；
- 所谓"中间人"的攻击方式，就是"中间人"冒充真正的[服务器](https://baike.baidu.com/item/服务器)接收你的传给服务器的数据，然后再冒充你把数据传给真正的服务器；

<br>

### **两种方式的主要区别**

- https url：复制https url然后到git Bash里面直接用clone命令克隆到本地就好了，但是每次fetch和push代码都需要输入账号和密码；

- SSH url：需要在只用之前先配置和添加好SSH key。fetch和push代码不需要输入账号和密码；如果你想要每次都输入账号密码才能进行fetch和push也可以另外进行设置。


<br>

<br>

## SSH Keys配置

### 1.检查你电脑上是否有SSH Key

##### 这行命令的作用是查看电脑上有没有.ssh文件夹

```
~/.ssh` 或者用`~/.ssh ls
```

- 若电脑上有：显示 **bash: /C/Users/…/.ssh: Is a directory**
- 若电脑上没有：显示 **bash: /C/Users/…/.ssh: No such file or directory**

<br>

### 2.创建SSH Key

##### 如果电脑上有了，可以直接跳过这一步

```
$ ssh -keygen -t rsa -c "个人邮箱"
```

##### 3次直接回车：

> 回车后，第一次要求输入一个文件名，用于保存刚才生成的 SSH key 代码。可以直接回车，那么就会默认生成id_rsa和id_rsa.pub两个秘钥文件，这时候已经创建好.ssh这个文件夹；
>
> 第二次要求输入密码，在使用ssh传输文件的时候，就要输入这个密码，所以不用设置直接回车；
>
> 第三次要求输入确认密码

##### 到此就表示公钥配置完成

<br>

### 3.添加SSH Key到GitHub

##### 打开路径：头像 --> Settings --> SSH and GPG keys 

> 1、点击右上角的New SSH key
>
> 2、Title随便起个别名
>
> 3、打开电脑中的.ssh文件夹，用记事本的方式打开id_rsa.pub文件，将内容复制到Key文本框中

##### 然后就会收到建立成功的邮件

<br>

### 4.测试SSH Key

在git Bash中输入以下代码

```
$ssh -T git@github.com
```

接下来会提示是否继续连接，输入yes回车

<br>

接下来会提示输入密码，如果上边设置ssh的时候，没有设置密码会提示：

**Warning: Permanently added ‘github.com,192.30.255.112’ (RSA) to the list of known hosts.**

<br>

警告完了，如果你能看到如下提示，那你已经成功设置SSH密钥。

 **Hi “用户名”! You’ve successfully authenticated, but GitHub does not provide shell access.**

 如果你看到 **access denied**，表示拒绝访问，那么你就需要使用 https 去访问。





