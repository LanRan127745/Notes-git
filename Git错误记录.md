# 有关Git的错误记录

### 1、本地文件改变了位置发生的错误       时间：2020/11/11

#### 问题描述：

> Git error: “Please make sure you have the correct access rights and the repository exists

#### 问题原因（Answer）：

> Your git URL might have changed. Change the URL in the local directory by using the following command
>
> git 的地址或许已经改变，使用以下命令更改本地目录中的URL

```
git remote set-url origin git@yourGitUrlHere
```

