---
layout: post
title:  "[MAVEN] 将本地Jar快速导入项目 "
date:   2019-10-23 00:51:12
---

#### 第一种方式

1. 先确认安装好了Maven 环境

   ```
   mvn -v 
   ```

   

2. 安装Jar到本地环境

   ```
    mvn install:install-file -Dfile=<path-to-file> -DgroupId=<group-id> -DartifactId=<artifact-id> -Dversion=<version> -Dpackaging=<packaging>
   
   
    <path-to-file>: 要安装的JAR的本地路径
    <group-id>：要安装的JAR的Group Id
    <artifact-id>: 要安装的JAR的 Artificial Id
    <version>: JAR 版本
    <packaging>: 打包类型，例如JAR
   ```

   

3. 本地引用

   ```
   <dependency>    
   
   <groupId>com.kingdee</groupId>    
   
   <artifactId>kingdee</artifactId>   
   
   <version>1.0.0</version>
   
   </dependency>
   ```
   
   



由于以上具有不方便移植的问题



#### 第二种方式

1. 将Jar包放在与`Pom.xml`的同级目录

2. `Pom.xml`添加一下依赖

   ```xml
   <dependency>
        <groupId>com.xxx</groupId>
        <artifactId>xxx-sdk-java</artifactId>
        <version>x.x.x</version>
        <scope>system</scope>
        <systemPath>${project.basedir}/xxx-sdk-java.jar</systemPath> 
   </dependency>
   ```

   






