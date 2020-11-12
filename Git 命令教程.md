# Git 命令

### 1.本地库初始化

```
git init
```

> 注意：.git（Linux中以"."开头的目录或文件都是隐藏的）目录是本地库相关的子目录和文件，不要随意删除和修改  

<br>

### 2. 设置签名

#### 2.1 形式

> 用户名：zzw
>
> email地址：745532828@qq.com

#### 2.2 作用

​	区分不同开发人员的身份

#### 2.3 命令

- ###### 项目级别/仓库界别：仅在当前本地库范围内有效

  > git config user.name zzw_local
  >
  > git config user.email 745532828@qq.com

  ##### 信息保存的位置：./.git/config文件

  ![zzw_pro 745532828@qq.com ](图片/config.jpg)

