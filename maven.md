## 插件学习
### 版本控制
没有什么用，已经提取version到properties里边：
<revision>1.4.2-SNAPSHOT</revision>
```shell script
    <!--
    执行版本控制命令：mvn versions:set -DnewVersion=1.0.3-SNAPSHOT
    -->
 <plugin>
    <groupId>org.codehaus.mojo</groupId>
    <artifactId>versions-maven-plugin</artifactId>
    <version>${versions-maven-plugin.version}</version>
</plugin>
```
### 依赖控制
[参考](https://github.com/vongosling/dependency-mediator)
mvn mediator:check，没啥用，可以在idea使用maven helper插件检测
```shell script
<plugin>
    <groupId>com.github.vongosling</groupId>
    <artifactId>dependency-mediator-maven-plugin</artifactId>
    <version>${dependency-mediator-maven-plugin.version}</version>
</plugin>
```
```shell script
<parent>
    <groupId>com.alibaba.nacos</groupId>
    <artifactId>nacos-all</artifactId>
    <version>${revision}</version>
    <!--
      <relativePath/>设定一个空值默认值为../pom.xml 表示将始终从父级仓库中获取，不从本地路径获取
      MAVEN构建jar包时候查找顺序：relativePath元素中的地址–本地仓库–远程仓库
    -->
    <relativePath>../pom.xml</relativePath>
</parent>
```
#### 所有的父级项目的packaging都为pom，packaging默认类型jar类型，
#### 如果不做配置，maven会将该项目打成jar包。

      
```text
maven-surefire-plugin，可以称之为测试运行器（Test Runner），他能很好的兼容JUnit 3、JUnit 4以及TestNG。

versions-maven-plugin：在项目的POM文件中管理工件的版本

dependency-mediator-maven-plugin：解决依赖冲突问题；

clirr-maven-plugin：在项目中运行Clirr框架

maven-enforcer-plugin：控制项目环境约束，例如maven版本、OS以及jdk等

maven-compiler-plugin:编译项目源码

maven-javadoc-plugin：使用jdoc工具为项目生成javadocs

maven-source-plugin：为当前的项目源码生成jar包

maven-help-plugin：获取项目或系统关联信息

maven-checkstyle-plugin：生成代码风格的报告

maven-resources-plugin：处理项目资源拷贝到输出目录中；

coveralls-maven-plugin：提交代码覆盖率报告到 Coveralls web服务；

jacoco-maven-plugin：单测生成覆盖率报告

maven-surefire-plugin：执行单元测试

findbugs-maven-plugin：查找系统中bug插件

```
