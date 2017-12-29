关于本翻译
翻译者：gangzi828

联系方式：QQ-1139872666

译者简介：本人是一个对新技术的热爱者，平时喜欢翻译一些国外技术资料，是开源技术的热衷者。现就职于杭州一家网络与信息安全公司，负责公司项目组的java开发和android开发。

声明：这个本人业余时间的翻译作品，任何组织和个人不得以商业利益进行非法传播。如有翻译不正确之处，请多多指正，喷子请远离。若您对本翻译计划感兴趣，欢迎您的加入，共同为开源界做贡献。

# 第一部分 spring boot 文档结构

第一部分简要介绍Spring Boot参考文档的组成结构。 可以将第一部分视为文档其余部分的地图。 您可以从头到尾以线性方式阅读本参考指南，或者可以跳过您不感兴趣的部分。

## 1.关于此文档

Spring Boot提供了三种格式的参考指南，分别是：html，pdf和epub的文档。 最新的版本可在https://docs.spring.io/spring-boot/docs/current/reference中找到。

本文档的副本供您自己或者给其他人使用都是免费的，并且进一步规定，无论是以印刷版还是电子版形式共享给其他人都必须包含本版权声明。

## 2.获取帮助

如果您在使用spring boot过程中遇到任何问题，可以通过以下方式获得帮助：

参考spring boot 文档第九部分，这里有关于spring boot的常见问题的解决办法
学习spring框架基础知识—Spring Boot建立在许多其他Spring项目上，请查看spring.io网站以获取大量参考文档。 如果您是Spring新手，请学习其中一个指南。

提交问题—我们在stackoverflow.com上发起了一个关于spring boot的问题讨论，标签是：spring-boot

通过https://github.com/spring-projects/spring-boot/issues提交spring boot的bugs。

## 3.第一步

如果你初次使用Spring Boot，或者简单的说是“Spring”，应该从这里开始

从零开始：spring boot概述| 系统要求| 环境安装

参考手册：第1部分| 第2部分

运行你的spring boot程序：第1部分| 第2部分

## 4.使用spring boot

准备使用spring boot了吗？请参考这里

构建系统：Maven | Gradle | Ant | Starter

最佳实践：代码结构| @Configuration | @EnableAutoConfiguration | Bean和依赖注入

运行代码：IDE | 打包| Maven | Gradle

打包应用程序：生产环境的可执行jar包

Spring Boot CLI：使用CLI

## 5.学习spring boot 特性

需要有关Spring Boot的核心功能的更多细节？ 请看这里！

核心功能：SpringApplication | 外部配置| Profiles| 日志

Web应用程序：MVC | 嵌入式容器

使用数据：SQL | NO-SQL

消息：概述| JMS

测试：概述| 启动应用程序| 工具

扩展：自动配置| 条件注解

## 6.生产环境

当您将开发好的Spring Boot应用程序部署到生产环境时，spring boot还提供了一些更加便利的使用技巧！

管理端点：概述 | 定制端点

连接选项：HTTP | JMX | SSH

监控：指标| 审计| 跟踪| 处理

## 7.spring boot 高级话题

最后，我们为更高级的用户提供了几个主题。

部署Spring boot应用程序：云部署| OS服务

构建工具插件：Maven | Gradle

附录：应用程序属性| 自动配置类| 可执行jar

# 第二部分 spring boot 入门

如果你初次使用Spring Boot，或者简单的说是“Spring”，应该从这里开始。在这里我们为您解答spring boot是什么，spring boot如何使用和为什么使用spring boot等一系列基本的问题，以及关于Spring Boot的简要介绍和安装说明。 然后，我们将构建我们的第一个Spring Boot应用程序，并且逐步探讨spring boot 的一些核心理念。

## 8.spring boot 简介

Spring Boot可以轻松创建独立运行的，生产级的基于Spring的应用程序。 由于开发者对Spring平台和第三方类库都有一定的认识，所以spring boot程序很容易上手，而且大多数Spring Boot应用程序只需要很少的Spring配置。

您可以使用Spring Boot创建基于java -jar命令来运行的可执行jar程序，也可以创建传统的以war包方式运行的java程序。spring boot还提供一个运行“spring脚本”的命令行工具。

Spring Boot的主要目标是：

为所有Spring开发提供一个基本的，更快，更广泛的入门体验。

开箱即用，同时也可以修改默认值来满足特定的需求。

提供了一些大型项目中常见的非功能性特性，如嵌入式服务器、安全、指标，健康检测、外部配置等。

绝对没有代码生成以及不需要XML配置，完全避免XML配置。

## 9.系统环境要求

默认情况下，Spring Boot 1.5.3.RELEASE 需要Java 7和Spring Framework 4.3.8.RELEASE（或更高版本）。 也可以使用java6 进行spring boot开发，但是需要一些额外配置，有关详细信息，请参见第84.11节“如何使用Java 6开发spring boot应用程序”。 spring boot 提供对Maven（3.2+）、Gradle2（2.9或更高版本）和Gradle3等构建工具的支持。

> 注意：尽管spring boot同时间支持java 6 和java 7，在尽可能的情况下，我们推荐使用java8进行spring boot程序开发。

### 9.1 Servlet 容器

spring boot对以下嵌入式servlet容器提供来开箱即用的支持：


| Servlet容器 | Servlet版本 | Java版本|
|------------|-----------|---------|
Tomcat8|3.1|Java7+|
Tomcat7|	3.0|	Java6+
Jetty9.3|	3.0|	Java8+
Jetty9.2|	3.1|	Java7+
Jetty8|	3.0	|Java6+
Undertow1.3|	3.1|	Java7+
Spring Boot还支持任何兼容Servlet 3.0+容器。

# 10.安装spring boot

Spring Boot可以像安装基本Java开发工具一样安装或作为命令行工具安装。 无论如何，您将需要Java SDK v1.6或更高版本。 您应该在安装spring boot之前先通过如下命令检查您当前的JDK安装版本：

`java -version`

如果您是Java开发的新手，或者您只想尝试一下Spring Boot，推荐您使用Spring Boot CLI，否则，请阅读“经典”安装说明。

> 注意：尽管Spring Boot兼容Java 1.6，如果可能，您应该考虑使用最新版本的Java

### 10.1 开发者安装指南

Spring Boot与任何标准Java类库的使用方式相同。 只需在您的类路径中包含对应的spring-boot - * .jar文件即可。 Spring Boot不需要任何特殊的集成开发工具，所以可以使用任何IDE或文本编辑器; 并且Spring Boot应用程序没有什么特别之处，因此您可以像任何其他Java程序一样运行和调试。

尽管您可以使用spring-boot.jar，但我们通常建议您使用支持依赖关系管理的构建工具（如Maven或Gradle）来开发spring boot应用。

#### 10.1.1 Maven 安装

Spring Boot兼容Apache Maven 3.2或者3.2以上的版本。 如果您还没有安装Maven，可以参照maven.apache.org上的说明进行Maven安装。

> 注意：在许多操作系统上，Maven可以通过软件包管理器进行安装。 如果您是Mac OSX 用户，请尝试使用brew install maven来进行Maven安装，如果您是 Ubuntu用户可以通过运行sudo apt-get install maven来进行Maven安装。

Spring boot 使用org.springframework.boot groupId 依赖。 通常，一个spring boot应用的Maven POM文件将从spring-boot-starter-parent项目继承，并声明一个或多个“Starter”的依赖关系。 Spring Boot还提供了一个可选的Maven插件来创建可执行的jar。

下面一个典型的pom.xml文件结构：

```
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>com.example</groupId>
    <artifactId>myproject</artifactId>
    <version>0.0.1-SNAPSHOT</version>

    <!-- Inherit defaults from Spring Boot -->
    <parent>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-parent</artifactId>
        <version>1.5.3.RELEASE</version>
    </parent>

    <!-- Add typical dependencies for a web application -->
    <dependencies>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>
    </dependencies>

    <!-- Package as an executable jar -->
    <build>
        <plugins>
            <plugin>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-maven-plugin</artifactId>
            </plugin>
        </plugins>
    </build>

</project>

```
通常情况下将spring-boot-starter-parent作为spring boot项目的父依赖是推荐做法，但这也可能不适合所有的情况。有时您可能需要从不同的父POM继承，或者您可能不需要spring boot的默认配置，这种情况下， 请参见第13.2.2节“通过设置POM的<scope>import</scope>来使用不带父POM的Spring Boot”作为替代解决方案。

#### 10.1.2 Gradle 安装

Spring Boot与Gradle 2（2.9或更高版本）和Gradle 3兼容。如果您尚未安装Gradle，您可以按照www.gradle.org/上的安装说明进行Gradle安装。

可以使用org.springframework.boot group声明Spring引导依赖项。 通常，您的项目将声明一个或多个“Starter”的依赖关系。 Spring Boot提供了一个有用的Gradle插件，可用于简化依赖关系声明和创建可执行jar文件。

Gradle Wrapper

Gradle Wrapper提供了一种在需要构建项目时“获得”Gradle的好方法。 它是一个小脚本和库，它与代码一起引导构建过程。 有关详细信息，请参阅docs.gradle.org/2.14.1/userguide/gradle_wrapper.html。

下面是一个典型的build.gradle文件：

```
plugins {
    id 'org.springframework.boot' version '1.5.3.RELEASE'
    id 'java'
}


jar {
    baseName = 'myproject'
    version =  '0.0.1-SNAPSHOT'
}

repositories {
    jcenter()
}

dependencies {
    compile("org.springframework.boot:spring-boot-starter-web")
    testCompile("org.springframework.boot:spring-boot-starter-test")
}
```

### 10.2 安装spring boot CLI
Spring Boot CLI是一个命令行工具，用于使用Spring进行快速原型搭建。它允许你运行Groovy脚本，这意味着你可以使用类Java的语法，并且没有那么多的模板代码。

你没有必要为了使用Spring Boot而去用CLI，但它绝对是助力Spring应用的最快方式。

#### 10.2.1 手动安装CLI

你可以从Spring软件仓库下载Spring CLI分发包：

* spring-boot-cli-1.5.3.RELEASE-bin.zip 
* spring-boot-cli-1.5.3.RELEASE-bin.tar.gz

不稳定的snapshot分发包也可以使用。

下载完成后，按照解压包里的INSTALL.txt操作指南进行安装。一般而言，在.zip文件的bin/目录下存在一个spring脚本（Windows下是spring.bat），或者使用java -jar来运行一个.jar文件（该脚本会帮你确定classpath被正确设置）。

#### 10.2.2 使用SDKMAN安装

SDKMAN!（软件开发套件管理器）可用于管理各种二进制SDK的多个版本，包括Groovy和Spring Boot CLI。从sdkman.io获取SDKMAN！并通过下面指令安装Spring Boot：

```
$ sdk install springboot
$ spring --version
Spring Boot v1.5.3.RELEASE
```

如果您正在开发CLI的功能，并希望轻松访问刚创建的版本，请遵循以下额外说明。

```
$ sdk install springboot dev /path/to/spring-boot/spring-boot-cli/target/spring-boot-cli-1.5.3.RELEASE-bin/spring-1.5.3.RELEASE/
$ sdk default springboot dev
$ spring --version
Spring CLI v1.5.3.RELEASE
```
这
将安装一个称为dev的spring的本地实例， 它指向您的目标构建位置，所以每次重建Spring Boot时，Starter将是最新的。

你可以看到它：

```
$ sdk ls springboot

================================================================================
Available Springboot Versions
================================================================================
> + dev
* 1.5.3.RELEASE

================================================================================
+ - local version
* - installed
> - currently in use
================================================================================
```
#### 10.2.3 Mac OSX下通过Homebrew安装

如果您在Mac上使用Homebrew，则可以通过如下指令安装Spring Boot CLI：

```
$ brew tap pivotal/tap
$ brew install springboot
```
Homebrew将Spring boot CLI安装到/ usr / local / bin目录。

> 如果您没有看到上面这种格式，说明您的安装可能会过期。 只需执行brew update，然后重试.

#### 10.2.4 Mac 下通过port 命令安装

如果您在Mac上使用MacPorts，则可以通过如下指令安装Spring Boot CLI：

```
$ sudo port install spring-boot-cli
```
#### 10.2.5 命令行安装
Spring Boot CLI为BASH和zsh shell脚本提供了命令自动补全功能。你可以在任何shell中source脚本（名称也是spring），或将它放到用户或系统范围内的bash初始化脚本里。在Debian系统中，系统级的脚本位于/shell-completion/bash下，当新的shell启动时该目录下的所有脚本都会被执行。如果你已经安装了SDKMAN，可以使用以下命令手动运行脚本：

```
$ . ~/.sdkman/candidates/springboot/current/shell-completion/bash/spring
$ spring <HIT TAB HERE>
  grab  help  jar  run  test  version
```

#### 10.2.6 spring boot CLI 快速入门

下面是一个相当简单的web应用，你可以用它测试Spring CLI安装是否成功。创建一个名叫app.groovy

的文件：

```
@RestController
class ThisWillActuallyRun {

    @RequestMapping("/")
    String home() {
        "Hello World!"
    }

}
```

然后只需在shell中运行以下命令：

```
$ spring run app.groovy
```
> 注：首次运行该应用将会花费一些时间，因为需要下载依赖，后续运行将会快很多。

使用你最喜欢的浏览器打开localhost:8080，然后就可以看到如下输出：

```
Hello World!
```

### 10.3 从spring boot早期版本升级

如果你正在升级Spring Boot的早期发布版本，那最好查看下spring boot工程的project wiki上的"release notes"发布说明，你会发现每次发布对应的升级指南和一个新特性列表。

你可以使用合适的包管理命令升级来升级一个已安装的CLI，例如brew upgrade；如果是手动安装CLI，按照standard instructions操作并记得更新你的PATH环境变量以移除任何老的引用。

## 11.开发你的第一个spring boot应用

我们将使用Java开发一个简单的"Hello World" web应用，以此强调下Spring Boot的一些关键特性。项目采用Maven进行构建，因为大多数IDEs都支持Maven。

> 注：spring.io网站包含很多Spring Boot"入门"指南，如果你正在找特定问题的解决方案，可以去那里查找相关参考指南。你也可以简化下面的步骤，直接从start.spring.io的依赖搜索器选中webstarter，这会自动生成一个新的项目结构，然后你就可以写自己的实现代码了。具体详情参考文档。

在开始前，你需要打开终端检查下安装的Java和Maven版本是否可用：

```
$ java -version
java version "1.7.0_51"
Java(TM) SE Runtime Environment (build 1.7.0_51-b13)
Java HotSpot(TM) 64-Bit Server VM (build 24.51-b03, mixed mode)
```
```
$ mvn -v
Apache Maven 3.2.3 (33f8c3e1027c3ddde99d3cdebad2656a31e8fdf4; 2014-08-11T13:58:10-07:00)
Maven home: /Users/user/tools/apache-maven-3.1.1
Java version: 1.7.0_51, vendor: Oracle Corporation
```
> 注：该示例需要创建单独的文件夹，后续的操作假设你已创建一个合适的文件夹，并且将它当作你的“当前目录”。

## 11.1 创建POM文件

我们从创建Maven的pom.xml开始。因为pom.xml是构建项目的清单。打开你最喜欢的文本编辑器，并添加以下内容：

```
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>com.example</groupId>
    <artifactId>myproject</artifactId>
    <version>0.0.1-SNAPSHOT</version>

    <parent>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-parent</artifactId>
        <version>1.5.3.RELEASE</version>
    </parent>

    <!-- Additional lines to be added here... -->

</project>
```
这
样一个工作目录就构建就完成了，你可以通过运行mvn package测试它（暂时忽略"jar将是空的-没有包含任何内容！"的警告）。

> 注：此刻，你可以将该项目导入到IDE中（大多数现代的Java IDE都包含对Maven的内建支持）。简单起见，我们将继续使用普通的文本编辑器完成该示例。

### 11.2 添加依赖

Spring Boot提供很多"Starters"，用来简化添加jars依赖的操作。示例程序中已经在POM文件的parent节点使用了spring-boot-starter-parent，它是一个特殊的starter，提供了常用的Maven默认设置。同时，它也提供一个dependency-management节点，这样对于期望（”blessed“）的依赖就可以省略version标记了。

其他”Starters“只简单提供开发特定类型应用所需的依赖。由于正在开发web应用，我们将添加spring-boot-starter-web依赖-但在此之前，让我们先看下目前的依赖：

```
$mvn dependency:tree
[INFO] com.example:myproject:jar:0.0.1-SNAPSHOT
```
mvn dependency:tree命令可以将项目依赖以树形方式展现出来，你可以看到spring-boot-starter-parent本身并没有提供依赖。编辑pom.xml，并在parent节点下添加spring-boot-starter-web依赖：

```
<dependencies>
	<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-web</artifactId>
	</dependency>
</dependencies>
```
如果再次运行mvn dependency:tree，你将看到现在多了一些其他依赖，包括Tomcat web服务器和Spring Boot自身。

### 11.3 编写代码

为了完成应用程序，我们需要创建一个单独的Java文件。Maven默认会编译src/main/java下的源码，所以你需要创建那样的文件结构，并添加一个名为src/main/java/Example.java的文件：

```
import org.springframework.boot.*;
import org.springframework.boot.autoconfigure.*;
import org.springframework.stereotype.*;
import org.springframework.web.bind.annotation.*;

@RestController
@EnableAutoConfiguration
public class Example {

    @RequestMapping("/")
    String home() {
        return "Hello World!";
    }

    public static void main(String[] args) throws Exception {
        SpringApplication.run(Example.class, args);
    }

}
```

尽管代码不多，但程序已经可以正确运行来，让我们逐步分析重要的部分吧！
#### 11.3.1 @RestController注解and @RequestMapping注解
Example类上使用的第一个注解是@RestController，这是一个原（stereotype）注解。它为阅读代码的人提供暗示（这是一个支持REST的控制器），对于Spring，该类扮演了一个特殊角色。在本示例中，我们的类是一个web@Controller，所以当web请求进来时，Spring会考虑是否使用它来处理。

@RequestMapping注解提供路由信息，它告诉Spring任何来自"/"路径的HTTP请求都应该被映射到home方法。@RestController注解告诉Spring以字符串的形式渲染结果，并直接返回给调用者。

> 注：@RestController和@RequestMapping是Spring MVC中的注解（它们不是Spring Boot的特定部分），具体参考Spring文档的MVC章节。

#### 11.3.2 @EnableAutoConfiguration注解
第二个类级别的注解是@EnableAutoConfiguration，这个注解告诉Spring Boot根据添加的jar依赖猜测你想如何配置Spring。由于spring-boot-starter-web添加了Tomcat和Spring MVC，所以auto-configuration将假定你正在开发一个web应用，并对Spring进行相应地设置。

> Starters和Auto-Configuration：Auto-configuration设计成可以跟"Starters"一起很好的使用，但这两个概念没有直接的联系。你可以自由地挑选starters以外的jar依赖，Spring Boot仍会尽最大努力去自动配置你的应用。

#### 11.3.3 main方法
应用程序的最后部分是main方法，这是一个标准的方法，它遵循Java对于一个应用程序入口点的约定。我们的main方法通过调用run，将业务委托给了Spring Boot的SpringApplication类。SpringApplication将引导我们的应用，启动Spring，相应地启动被自动配置的Tomcat web服务器。我们需要将Example.class作为参数传递给run方法，以此告诉SpringApplication谁是主要的Spring组件，并传递args数组以暴露所有的命令行参数。

### 11.4 运行示例
现在示例应用可以运行了。由于使用了spring-boot-starter-parentPOM，这样我们就有了一个非常有用的run目标来启动程序。在项目根目录下输入mvn spring-boot:run启动应用：

```
$ mvn spring-boot:run

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::  (v1.5.3.RELEASE)
....... . . .
....... . . . (log output here)
....... . . .
........ Started Example in 2.222 seconds (JVM running for 6.514)
```
如果使用浏览器打开localhost:8080，你应该可以看到如下输出：

```
Hello World!
```

点击ctrl-c温雅地关闭应用程序。

### 11.5 创建一个可执行jar

让我们通过创建一个完全自包含，并可以在生产环境运行的可执行jar来结束示例吧！可执行jars（有时被称为胖jars "fat jars"）是包含编译后的类及代码运行所需依赖jar的存档。

> 可执行jars和Java：Java没有提供任何标准方式，用于加载内嵌jar文件（即jar文件中还包含jar文件），这对分发自包含应用来说是个问题。为了解决该问题，很多开发者采用"共享的"jars。共享的jar只是简单地将所有jars的类打包进一个单独的存档，这种方式存在的问题是，很难区分应用程序中使用了哪些库。在多个jars中如果存在相同的文件名（但内容不一样）也会是一个问题。Spring Boot采取一个不同的方式，允许你真正的直接内嵌jars。

为了创建可执行的jar，我们需要将spring-boot-maven-plugin添加到pom.xml中，在dependencies节点后面插入以下内容：

```
<build>
    <plugins>
        <plugin>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-maven-plugin</artifactId>
        </plugin>
    </plugins>
</build>
```

> 注：spring-boot-starter-parentPOM包含绑定到repackage目标的<executions>配置。如果不使用parent POM，你需要自己声明该配置，具体参考插件文档。

保存pom.xml，并从命令行运行mvn package：

```
$ mvn package

[INFO] Scanning for projects...
[INFO]
[INFO] ------------------------------------------------------------------------
[INFO] Building myproject 0.0.1-SNAPSHOT
[INFO] ------------------------------------------------------------------------
[INFO] .... ..
[INFO] --- maven-jar-plugin:2.4:jar (default-jar) @ myproject ---
[INFO] Building jar: /Users/developer/example/spring-boot-example/target/myproject-0.0.1-SNAPSHOT.jar
[INFO]
[INFO] --- spring-boot-maven-plugin:1.5.3.RELEASE:repackage (default) @ myproject ---
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
```
如果查看target目录，你应该可以看到myproject-0.0.1-SNAPSHOT.jar，该文件大概有10M。想查看内部结构，可以运行jar tvf：

```
$ jar tvf target/myproject-0.0.1-SNAPSHOT.jar
```
在该目录下，你应该还能看到一个很小的名为myproject-0.0.1-SNAPSHOT.jar.original的文件，这是在Spring Boot重新打包前，Maven创建的原始jar文件。可以使用java -jar命令运行该应用程序：

```
$ java -jar target/myproject-0.0.1-SNAPSHOT.jar

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::  (v1.5.3.RELEASE)
....... . . .
....... . . . (log output here)
....... . . .
........ Started Example in 2.536 seconds (JVM running for 2.864)
```
如上所述，点击ctrl-c可以温雅地退出应用。

## 12.接下来阅读什么

希望本章节已为你提供一些Spring Boot的基础知识，并帮你找到开发spring boot应用的方式。如果你是任务驱动型的开发者，那可以直接跳到spring.io，参考一些入门指南，以解决特定的"使用Spring如何做"的问题；我们也有Spring Boot相关的How-to参考文档。Spring Boot仓库有大量可以运行的示例，这些示例代码是彼此独立的(运行或使用示例的时候不需要构建其他示例)。否则，下一步就是阅读III、使用Spring Boot，如果没耐心，可以跳过该章节，直接阅读IV、Spring Boot特性。
# 第三部分 使用spring boot

## 13 构建系统
强烈建议您选择一个支持依赖管理的构建工具，并可以通过该构建工具将应用发布到“Maven Central”仓库。 我们建议您选择Maven或Gradle。 可以让Spring Boot与其他构建系统（例如Ant）配合使用，但是它们不会得到很好的支持。
### 13.1 依赖管理
每个spring boot的发布版本都提供了一个支持的依赖关系列表。在实际应用中，你不需要在你的构建配置文件中提供任何依赖的版本信息，因为Spring Boot会自动管理依赖的版本。当你升级spring Boot版本时，相关的依赖也一起进行升级。

> 注意：必要的时候你也可以自己指定依赖的版本，而不是用Sping Boot推荐的依赖版本。

spring boot依赖关系列表包含了spring的所有组件和精细化的第三方库。该列表可作为标准的BOM依赖清单供Maven或Gradle使用。

> 注意：Spring Boot的每个版本都对应一个Spring框架的基础版本，所以我们强烈建议你不要自己指定Spring Boot所依赖的Spring基础版本。

### 13.2 Maven

# 第四部分 spring boot 特性

本部分深入介绍Spring Boot的细节。 通过本部分的学习，您可以了解在开发过程中即将应用到的spring boot的关键特性。 如果你还没有了解这些特性，您可能需要阅读第二部分“spring boot入门”和第三部分“使用spring boot”部分，以便您对spring boot有一个基础的了解。

## 23 SpringApplication

SpringApplication类提供了一种便捷的方式来启动一个以main()方法为启动入口的Spring应用程序。 在大多数情况下，您只需将启动过程委托给SpringApplication.run这个静态方法：

```
public static void main(String[] args) {
    SpringApplication.run(MySpringConfiguration.class, args);
}
```
当您的应用程序启动时，您将看到类似于以下内容：

```
 .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::   v1.5.3.RELEASE

2013-07-31 00:08:16.117  INFO 56603 --- [           main] o.s.b.s.app.SampleApplication            : Starting SampleApplication v0.1.0 on mycomputer with PID 56603 (/apps/myapp.jar started by pwebb)
2013-07-31 00:08:16.166  INFO 56603 --- [           main] ationConfigEmbeddedWebApplicationContext : Refreshing org.springframework.boot.context.embedded.AnnotationConfigEmbeddedWebApplicationContext@6e5a8246: startup date [Wed Jul 31 00:08:16 PDT 2013]; root of context hierarchy
2014-03-04 13:09:54.912  INFO 41370 --- [           main] .t.TomcatEmbeddedServletContainerFactory : Server initialized with port: 8080
2014-03-04 13:09:56.501  INFO 41370 --- [           main] o.s.b.s.app.SampleApplication            : Started SampleApplication in 2.992 seconds (JVM running for 3.658)
```
默认情况下，spring boot将显示INFO级别的日志，这些日志包括应用程序启动的一些细节信息，例如，启动程序的用户信息。


