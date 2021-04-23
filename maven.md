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
