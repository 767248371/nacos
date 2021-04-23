[参考](https://xkcoding.com/2018/09/18/how-to-update-the-fork-project.html)
在 github 上 fork 了一个项目之后，如何使自己 fork 的项目和原先作者的项目分支保持同步呢，下面我使用 hutool 的项目做示范，手摸手示范如何使 fork 的项目与原项目分支保持同步。
 
 查看远程的版本库地址
 
 $ git remote -v 
origin  git@github.com:767248371/nacos.git (fetch)
origin  git@github.com:767248371/nacos.git (push)
 添加原项目 git 地址到本地版本库
  
 $ git remote add upstream https://github.com/alibaba/nacos.git
 检查版本库是否添加成功
  
 $ git remote -v
```shell script
➜  nacos git:(develop) ✗  git remote -v
origin  git@github.com:767248371/nacos.git (fetch)
origin  git@github.com:767248371/nacos.git (push)
upstream        https://github.com/alibaba/nacos.git (fetch)
upstream        https://github.com/alibaba/nacos.git (push)

```
 原项目更新内容同步到本地
 
 $ git fetch upstream                             

 查看本地分支
 
 $ git branch -a 
 ```
* develop
  remotes/origin/0.2.1
  remotes/origin/0.2.2
  remotes/origin/0.3.0
  remotes/origin/0.6.1
  remotes/origin/0.7.0
  remotes/origin/1.0.0-RC1
  remotes/origin/1.0.0-RC2
  remotes/origin/1.0.0-RC3
  remotes/origin/2.0.0
  remotes/origin/client-1.3.3
  remotes/origin/develop
  remotes/origin/develop4commerce
  remotes/origin/develop_1.2.0
  remotes/origin/feature_ServiceMesh
  remotes/origin/feature_address_server
  remotes/origin/feature_ans
  remotes/origin/feature_mesh_patch
  remotes/origin/feature_multiple_datasource_support
  remotes/origin/feature_nacos_swift
  remotes/origin/feature_naming_ap
  remotes/origin/feature_selector

```
 同步更新内容到本地对应分支
 
```
➜  nacos git:(develop) ✗ git merge upstream/develop
Already up to date.
➜  nacos git:(develop) ✗ 
```
 提交更新内容到 fork 地址
  git push

