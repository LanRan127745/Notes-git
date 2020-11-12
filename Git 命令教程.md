# Git 命令

### 1. 本地库初始化

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

  

- ###### 系统用户级别：登录当前操作系统的用户范围

- > git config --global user.name zzw_glb
  >
  > git config --global user.email 745532828@qq.com

- **信息保存的位置：~/.gitconfig文件**



- ###### 级别优先级

  - 就近原则：项目级别优先于系统用户级别，二者都有时采用项目级别的签名
  - 如果只有系统用户级别的签名，就以系统用户级别的签名为准
  - 二者都没有是不允许的



### 3. 基本操作

- ##### 状态查看操作：查看工作区、缓存区的状态

  ``` git status
  git status
  ```

- ##### 添加操作

  ```
  git add "file name"
  ```

- ##### 提交操作

  ```
  git commit -m "commit message" "file name"
  ```

- ##### 提交跟踪过的文件

  - 当工作区中新建了一个文件时，使用add后就会变成跟踪状态
  - 工作目录下面的所有文件有这两种状态：**已跟踪或未跟踪**
  - 跟踪的文件是指本来就被纳入版本控制管理的文件，在上次快照中有它们的记录，工作一段时间后，它们的状态可能是未更新，已修改或者已放入暂存区

  ```
  git commit -am "commit message"
  ```

  

### 4. 分支操作

- ##### 创建分支

  ```
  git branch [branch name]
  ```

- ##### 查看分支

  ```
  git branch -v
  ```

- ##### 切换分支

  ```
  git checkout [branch name]
  ```

- ##### 合并分支

  1. 切换到接受修改的分支上（被合并，增加新内容上）

     ```
     git checkout [branch name]
     ```

  2. 执行merge命令

     ```
     git merge [new content branch name]
     ```

- ##### 解决冲突

  1. 编译冲突的文件，删除特殊符号

     ​	如： <<<<<<<<<<<<< HEAD 

     ​			=================

     ​			>>>>>>>>>>>>>master

  2. 把文件修改到想要的结果，保存退出
  3. git add "file name"
  4. git commit -m "log message"

  **注意：此时commit不能带具体文件名**



### 5. GitHub

- ##### 创建远程仓库别名

  - 查看当前所有远程仓库别名

    ```
    git remote -v 
    ```

  - 添加远程仓库别名

    ```
    git remote add 别名 远程仓库地址
    ```

- ##### 推送

  ```
  git push 别名 分支名
  ```

  ###### 加了参数-u之后，以后可直接使用git push替代git push origin master

  ```
  git push -u origin master
  ```

- ##### 克隆

  将远程仓库下载到本地

  创建远程地址别名

  初始化本地仓库

  ```
  git clone 远程仓库地址
  ```

- ##### 拉取内容

  - 合并操作 pull = fetch + merge 

    ```
    git pull 远程别名 分支名
    ```

  - 拉取操作 

    ```
    git fetch 远程仓库地址别名 远程分支名
    ```

  - 合并操作 

    ```
    git meger 远程仓库地址别名 远程分支名
    ```

    

  

