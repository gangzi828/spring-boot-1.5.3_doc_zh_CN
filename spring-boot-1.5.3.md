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


### 23.1 启动失败

如果您的应用程序启动失败，则spring boot通过注册的FailureAnalyzers来输出错误信息并给出解决该问题的具体操作方法。 例如，如果您在8080端口上启动Web应用程序，并且该端口已在使用中，则应该会看到类似于以下的错误日志信息：

```
***************************
APPLICATION FAILED TO START
***************************

Description:

Embedded servlet container failed to start. Port 8080 was already in use.

Action:

Identify and stop the process that's listening on port 8080 or configure this application to listen on another port.
```
> Spring Boot提供了许多FailureAnalyzer实现，并且您也可以自定义FailureAnalyzer。

如果没有失败分析器能够处理异常，您仍然可以通过显示完整的自动配置报告来更好地了解出现的问题。 为此，您需要启用debug属性或启用DEBUG级别日志：

```
org.springframework.boot.autoconfigure.logging.AutoConfigurationReportLoggingInitializer
```
例如，如果使用java -jar运行应用程序，则可以按如下方式启用调试属性：

```
$ java -jar myproject-0.0.1-SNAPSHOT.jar --debug
```

### 23.2 自定义启动Banner
spring boot应用程序的启动Banner可以通过在的类路径中添加一个banner.txt文件，或者通过banner.location来设置Banner文件的位置来更改启动时打印的Banner。 如果文件中存在特殊的编码，你可以通过banner.charset来设置编码（默认为UTF-8）。 除了文本文件，您还可以将banner.gif，banner.jpg或banner.png图像文件添加到您的类路径中，或者设置一个banner.image.location属性。 图像将被转换成ASCII艺术表现，并打印在任何文字Banner上方。

您可以在banner.txt文件中使用以下任何一个占位符：

###### 表23.1Banner变量
|变量|描述|
|----|----|
|${application.version}|在MANIFEST.MF中声明的应用程序版本号。 例如，Implementation-Version: 1.0被打印为1.0。
${application.formatted-version}|在MANIFEST.MF中声明的格式化显示的应用程序版本号（用括号括起来并以v替代）。 例如（v1.0）。
${spring-boot.version}|您正在使用的Spring Boot版本。 例如1.5.3.RELEASE。
${spring-boot.formatted-version}|您正在使用的spring boot版本的格式化显示（用括号括起来并以v替代）。 例如（v1.5.3.RELEASE）。
${Ansi.NAME}(or${AnsiColor.NAME},${AnsiBackground.NAME},${AnsiStyle.NAME})|其中NAME是ANSI转义码的名称。 有关详细信息，请参阅AnsiPropertySource。
${application.title}|在MANIFEST.MF中声明的应用程序标题。 例如：Implementation-Title：MyAppis打印为MyApp。

> 如果要以编程方式生成Banner，则可以使用SpringApplication.setBanner（...）方法。 实现org.springframework.boot.Banner接口，并实现自己的printBanner（）方法。

您
还可以使用spring.main.banner-mode属性来决定是否必须在System.out（控制台）上打印横幅，使用配置的记录器（log）或根本不打印（关闭）。

打印的Banner将以名称springBootBanner注册为单例bean。

> YAML格式的配置文件用off代表禁止打印Banner，所以如果要禁用应用程序中的Banner，请确保为off添加引号。
> 
 ```
spring:
    main:
        banner-mode: "off"
        
### 23.3 自定义SpringApplication
如果系统默认的SpringApplication不能满足你的需求，你可以自定义SpringApplication。例如：想关闭Banner，你可以通过以下自定义SpringApplication来实现：

```
public static void main(String[] args) {
    SpringApplication app = new SpringApplication(MySpringConfiguration.class);
    app.setBannerMode(Banner.Mode.OFF);
    app.run(args);
}
```
> 在SpringApplication构造函数中传入的变量是spring的资源配置Bean。在大多数情况下，这些Bean都是来自@Configuration注解的类，但也有来自XML配置和包扫描提供的配置Bean。

还可以通过application.properties对SpringApplication进行配置，具体细节请参考第24章，外部化配置。

关于SpringConfiguration的完成配置选项，请参考SpringApplicationJavadoc文档。

### 23.4 流式构建器API
如果你需要建立一个应用程序上下文的层次结构（多个具有父/子关系的上下文结构），或者如果你只是喜欢用“流式”构建器API，你可以使用SpringApplicationBuilder。

SpringApplicationBuilder允许您链式调用父类或者子类中的方法。

例如：

```
new SpringApplicationBuilder()
        .sources(Parent.class)
        .child(Application.class)
        .bannerMode(Banner.Mode.OFF)
        .run(args);
```

> 当创建一个应用程序上下文的层次结构时有一些限制，例如：Web组件必须包含在子范围内，同样的环境将用于父上下文和子上下文。具体可以参考SpringApplicationBuilderJavadoc文档来了解全部细节。

### 23.5 应用程序事件监听器
除了 spring框架的事件，比如ContextRefreshedEvent事件，SpringApplication还发出一些额外的应用程序事件。

> 有些事件是在ApplicationContext创建之前触发的，因此不能通过@Bean的方式注册事件监听器。您可以通过SpringApplication.addListeners（...）或SpringApplicationBuilder.listeners（...）方法来进行注册。如果你想让这些监听在程序创建的时候自动注册，您可以添加一个META-INF/ spring.factories文件到您的项目中，并通过使用org.springframework.context.ApplicationListener键来注册监听器。

org.springframework.context.ApplicationListener= com.example.project.MyListener

随着应用程序的启动，应用程序事件监听器将以如下顺序被触发：

1. 在程序运行开始，但是在注册监听器和初始化之前的所有处理前，发送一个ApplicationStartingEvent事件。
1. 在Environment被应用于已知上下文，但是在上下文创建之前，发送一个ApplicationEnvironmentPreparedEvent事件。
1. 在refresh开始之前，但在Bean定义已被加载之后，发送一个ApplicationPreparedEvent事件。
1. 在refresh执行之后，并且其他相关的回调接口已经准备就绪，程序可以接收请求，发送一个ApplicationReadyEvent事件。
1. 在应用程序启动过程中抛出异常时，发送一个ApplicationFailedEvent事件。

> 你通常不再需要使用应用程序事件，只要知道它存在即可。在内部，spring boot使用应用程序事件来处理各种任务。

### 23.6 Web环境
SpringApplication会尝试根据用户的意图来创建正确类型的应用程序上下文。默认情况下，如果你正在开发的是非Web应用程序，则创建AnnotationConfigApplicationContext，Web应用程序则创建AnnotationConfigEmbeddedWebApplicationContext上下文。

用于确定应用程序是否为“Web环境”的算法是相当简单（基于几个类的存在）。如果你需要覆盖默认设置，可以使setWebEnvironment（boolean webEnvironment）。

因此，可以通过调用setApplicationContextClass（...）来完全控制应用程序的上下文。

> 当JUnit测试中使用SpringApplication时，通常需要调用setWebEnvironment（false)

### 23.7 访问应用程序变量
如果想访问传入SpringApplication.run(…​)中的变量，只需注入一个org.springframework.boot.ApplicationArguments类型的Bean即可。ApplicationArguments接口提供了原生String[]类型变量的功能以及解析选项和非选项参数的功能：

```
import org.springframework.boot.*
import org.springframework.beans.factory.annotation.*
import org.springframework.stereotype.*

@Component
public class MyBean {

    @Autowired
    public MyBean(ApplicationArguments args) {
        boolean debug = args.containsOption("debug");
        List<String> files = args.getNonOptionArgs();
        // if run with "--debug logfile.txt" debug=true, files=["logfile.txt"]
    }

}
```
> spring boot还注册了一个带有spring 环境的CommandLinePropertySource，可以通过@Value进行变量注入。

### 23.8 使用ApplicationRunner和CommandLineRunner
如果某些代码需要在SpringApplication启动时只执行一次，这可以通过实现ApplicationRunner和CommandLineRunner接口来实现。这两个接口的工作方式基本相同，都只包含一个run方法，并且在SpringApplication.run(…​)方法执行之前执行。

CommandLineRunner接口以String数组的形式来访问应用程序变量，而ApplicationRunner通过ApplicationArguments接口来访问应用程序变量。

```
import org.springframework.boot.*
import org.springframework.stereotype.*

@Component
public class MyBean implements CommandLineRunner {

    public void run(String... args) {
        // Do something...
    }

}
```
当程序中有多个CommandLineRunner和ApplicationRunner的Bean的时候，可以通过实现org.springframework.core.Ordered接口活着通过org.springframework.core.annotation.Order这个注解来确定执行的顺序。

### 23.9 退出应用程序

每个SpringApplication都在JVM注册一个关闭的钩子，以确保当应用程序退出时ApplicationContext可以优雅的关闭。所有标准的Spring生命周期回调函数都（如DisposableBean接口或@PreDestroy注解）可被使用。

此外，如果希望在应用程序结束返回一个特定的退出代码，可以通过创建一个实现org.springframework.boot.ExitCodeGenerator接口的Bean。

### 23.10 Admin特性
在spring boot中可以通过设置spring.application.admin.enabled属性来开启Admin相关的特性。这通过MBeanServer平台暴露出一个

SpringApplicationAdminMXBean来实现。

* 可以通过设置local.server.port来查看应用程序运行在哪个HTTP端口。
* 注意当启用Admin特性时，在MBean中暴露了关闭应用程序的方法。

## 24 外部化配置
Spring Boot允许您外部化您的配置，以便您可以在不同的环境中使用相同的应用程序代码。 您可以使用属性文件，YAML文件，环境变量和命令行参数来外部化配置。 可以使用@Value注解将属性值直接注入到您的bean中，该注解可通过Spring环境抽象访问，或通过@ConfigurationProperties绑定到结构化对象。

Spring Boot使用非常特殊的PropertySource命令来覆盖属性值。 属性按以下顺序考虑：

1. 在用户家目录下的Devtools全局配置文件，（当devtools处于活跃状态时，~/.spring-boot-devtools.properties）
1. 在测试类中的@TestPropertySource
1. @SpringBootTest#properties注解属性
1. 命令行参数
1. SPRING_APPLICATION_JSON的属性（）
1. ServletConfig初始化参数
1. ServletContext初始化参数
1. java:comp/env中的JNDI属性
1. Java系统属性（System.getPropertis()）
1. 系统环境变量
1. random.*形式定义的RandomValuePropertySource属性
1. 应用程序的jar包之外通过Profile来指定的application.properties文件（application-{profile}.properties或者 YAML 形式）
1. 应用程序的jar包之内通过Profile来指定的application.properties文件（application-{profile}.properties或者 YAML 形式）
1. 应用程序的jar包之外的application.properties文件（application-{profile}.properties或者 YAML 形式）
1. 应用程序的jar包之内的application.properties文件（application-{profile}.properties或者 YAML 形式）
1. @Configutation注解的配置类中@PropertySource注解的属性
1. 通过 SpringApplication.setDefaultProperties指定的默认配置属性

为了展示一个完整的示例，这里我们假设已经定义了一个@Component注解的Bean，该Bean拥有name属性：

```
import org.springframework.stereotype.*
import org.springframework.beans.factory.annotation.*

@Component
public class MyBean {

    @Value("${name}")
    private String name;

    // ...

}
```

在你的应用程序类路径中（例如jar包中），可以通过application.properties给name属性提供一个默认的值。 在新环境中运行时，可以在您的jar外部提供一个application.properties来覆盖该名称; 对于一次性测试，您可以使用特定的命令行开关启动（例如，java -jar app.jar --name =“Spring”）。

```
可以在命令行上提供一个环境变量SPRING_APPLICATION_JSON属性。 例如在UN * X shell中：

$ SPRING_APPLICATION_JSON ='{“foo”：{“bar”：“spam”}}'java -jar myapp.jar

在本例中，您将在Spring环境中使用foo.bar = spam。 您也可以在系统变量中将JSON作为spring.application.json提供：

$ java -Dspring.application.json ='{“foo”：“bar”}'-jar myapp.jar

或命令行参数：

$ java -jar myapp.jar --spring.application.json ='{“foo”：“bar”}'

或作为JNDI变量java：comp / env / spring.application.json
```
### 24.1 配置随机值
RandomValuePropertySource可用于注入随机值（例如，注入密码或测试用例）。 它可以产生整数，长整数，uuids或字符串，例如:

```
my.secret=${random.value}
my.number=${random.int}
my.bignumber=${random.long}
my.uuid=${random.uuid}
my.number.less.than.ten=${random.int(10)}
my.number.in.range=${random.int[1024,65536]}

```
random.int *语法是OPEN value（，max）CLOSE，其中OPEN，CLOSE是任何字符和值，max是整数。 如果提供max，则value为最小值，max为最大值（不包含最大值）。
### 24.2 访问命令行属性

默认情况下，SpringApplication将任何命令行选项参数（以' -- '开头，例如--server.port = 9000）转换为属性，并将其添加到Spring环境中。 如上所述，命令行属性始终优先于其他属性来源。

如果不希望将命令行属性添加到环境中，可以使用SpringApplication.setAddCommandLineProperties（false）禁用它们。

### 24.3 应用程序属性文件
SpringApplication将从以下位置的application.properties文件中加载属性，并将它们添加到Spring环境中：

1. 当前目录的/config子目录。
1. 当前目录
1. 一个classpath/config包
1. 类路径根

上述列表是按属性文件优先级排序（在高优先级中定义的属性将覆盖在较低优先级中定义的属性）。
> 注意：可以使用YAML(.yml)文件替代.properties文件

如果您不喜欢application.properties作为配置文件名，可以通过指定一个spring.config.name环境属性来指定配置文件名。 您还可以使用spring.config.location环境属性（逗号分隔的目录位置的或文件路径）显式引用配置文件的位置。

```
$ java -jar myproject.jar --spring.config.name=myproject
```
或者

```
$ java -jar myproject.jar --spring.config.location=classpath:/default.properties,classpath:/override.properties
```
> spring.config.name和spring.config.location非常早已被用于确定哪些文件必须被加载，因此必须将它们定义为环境属性（通常是OS env，system属性或命令行参数）。

如
果spring.config.location包含目录（而不是文件），那么它们应该以/结尾，（并追加从spring.config.name配置的文件名称）。 在spring.config.location中指定的文件按原样使用，不支持特定于配置文件的变体，并且将被任何特定于配置文件的属性覆盖。

默认的搜索路径classpath：，classpath：/ config，file：，file：config /，不管spring.config.location的值如何。 该搜索路径是按照优先级排序（file:config 的优先级最高）的。 如果您指定自己的位置，则它们优先于所有默认位置，并使用相同的从最低到最高优先级排序。 这样，您可以在application.properties（或使用spring.config.name选择的任何其他基础名称）中为应用程序设置默认值，并在运行时使用不同的文件覆盖它，并保留默认值。

> 如果您使用环境变量而不是系统属性，大多数操作系统不允许使用周期分隔的键名称，但可以使用下划线（例如SPRING_CONFIG_NAME代替spring.config.name）。

> 如果您运行在容器中，则可以使用JNDI属性（在java:comp / env中）或servlet上下文初始化参数，而不是环境变量或系统属性。

### 24.4 配置文件特定的属性
除了application.properties文件外，还可以使用命名约定application- {profile} .properties定义特定于配置文件的属性。 Environment具有一组默认配置文件(默认为[default])，如果没有设置活动配置文件（即，如果没有显式激活配置文件，则加载了来自application-default.properties的属性）。

特定于配置文件的属性从与标准application.properties相同的位置加载，配置文件特定文件始终覆盖非特定文件，而不管特定于配置文件的文件是否在打包的jar内部或外部。

如果指定了几个配置文件，则应用最后一个。 例如，由spring.profiles.active属性指定的配置文件在通过SpringApplication API配置的配置之后添加，因此具有高的优先级。

> 如果您在spring.config.location中指定了任何文件，则不会考虑这些文件的特定于配置文件的变体。 如果还要使用特定于配置文件的属性，请在spring.config.location中使用目录。

### 24.5 属性文件占位符
application.properties中的值在使用时通过现有环境进行过滤，以便您可以引用回先前定义的值（例如，从系统属性）。

```
app.name=MyApp
app.description=${app.name} is a Spring Boot application
```
> 您也可以使用此技术创建现有Spring Boot属性的“简短”变体。 有关详细信息，请参见第72.4节“使用”短命令行参数“how-to”。

### 24.6 使用YAML配置文件
YAML是JSON的超集，因此在指定分层配置数据时，这是一种非常方便的格式。 每当您的类路径中都有SnakeYAML库时，SpringApplication类将自动支持YAML作为属性的替代方法。

> 如果您使用“Starters”，SnakeYAML将通过spring-boot-starter自动提供。

#### 24.6.1 加载YAML
Spring Framework提供了两个方便的类，可用于加载YAML文档。 YamlPropertiesFactoryBean将YAML作为属性加载，并且YamlMapFactoryBean将加载YAML作为Map集合。

例如，如下的YAML文档：

```
environments:
    dev:
        url: http://dev.bar.com
        name: Developer Setup
    prod:
        url: http://foo.bar.com
        name: My Cool App
```
转换成对应的属性配置文件为：

```
environments.dev.url=http://dev.bar.com
environments.dev.name=Developer Setup
environments.prod.url=http://foo.bar.com
environments.prod.name=My Cool App
```
YAML列表表示为具有[index] 引用的属性键，例如YAML：

```
my:
   servers:
       - dev.bar.com
       - foo.bar.com
```
将被转换为如下属性：

```
my.servers[0]=dev.bar.com
my.servers[1]=foo.bar.com
```
要使用Spring DataBinder实用程序（这是@ConfigurationProperties所做的）绑定到这样的属性，您需要在类型为java.util.List（或Set）的目标bean中具有一个属性，并且您需要提供一个setter，或者用可变值初始化它，例如，这将绑定到上面的属性：

```
@ConfigurationProperties(prefix="my")
public class Config {

    private List<String> servers = new ArrayList<String>();

    public List<String> getServers() {
        return this.servers;
    }
}
```

> 配置列表时，需要特别小心，因为覆盖方式将无法正常工作。 在上面的示例中，当我的几个地方重新定义my.servers时，单个元素的目标是覆盖，而不是列表。 要确保具有较高优先级的PropertySource可以覆盖列表，您需要将其定义为单个属性：
```
my:
   servers: dev.bar.com,foo.bar.com
```

#### 24.6.2 将YAML作为Spring环境中的属性
可以使用YamlPropertySourceLoader类在Spring环境中将YAML作为PropertySource进行公开。 这允许您使用熟悉的@Value注释和占位符语法来访问YAML属性。
#### 24.6.3 Multi-profile YAML文档
您可以使用spring.profiles键指定单个文件中的多个配置文件特定的YAML文档，以指示文档何时应用。 例如：

```
server:
    address: 192.168.1.100
---
spring:
    profiles: development
server:
    address: 127.0.0.1
---
spring:
    profiles: production
server:
    address: 192.168.1.120
```
在上面的示例中，如果开发环境的配置文件处于活动状态，则server.address属性将为127.0.0.1。 如果开发和生产环境的配置文件均未启用，则该属性的值将为192.168.1.100。

如果应用程序上下文启动时没有显式激活，默认配置文件将被激活。 所以在这个YAML中，我们为security.user.password设置一个仅在“默认”配置文件中可用的值：

```
server:
  port: 8000
---
spring:
  profiles: default
security:
  user:
    password: weak
```
而在此示例中，密码始终被设置，因为它没有附加到任何配置文件，并且必须在必要时在所有其他配置文件中显式重置密码：

```
server:
  port: 8000
security:
  user:
    password: weak
```

使用“spring.profiles”元素指定的可以选择使用！ 字符。 如果为单个文档指定了否定和非否定的配置文件，则至少有一个非否定配置文件必须匹配，没有否定配置文件可能匹配。
#### 24.6.4 YAML配置的缺点
YAML文件无法通过@PropertySource注释加载。 因此，在需要以这种方式加载值的情况下，需要使用属性文件。
#### 24.6.5 合并YAML
如上所述，任何YAML内容最终都会转换为属性。 当通过配置文件覆盖“list”属性时，该过程可能是直观的。

例如，假设默认情况下，name和description属性为空的MyPojo对象。 让我们从FooProperties中公开MyPojo列表：

```
@ConfigurationProperties("foo")
public class FooProperties {

    private final List<MyPojo> list = new ArrayList<>();

    public List<MyPojo> getList() {
        return this.list;
    }

}
```

考虑如下配置：

```
foo:
  list:
    - name: my name
      description: my description
---
spring:
  profiles: dev
foo:
  list:
    - name: my another name
```
如果dev配置文件未被激活，FooProperties.list将包含一个如上定义的MyPojo条目。 如果启用了配置文件，列表仍将包含一个条目（名称为“my another name”，描述为null）。 此配置不会将第二个MyPojo实例添加到列表中，并且不会将项目合并。

当在多个配置文件中指定集合时，使用具有最高优先级的集合（并且仅使用该配置文件）：

```
foo:
  list:
    - name: my name
      description: my description
    - name: another name
      description: another description
---
spring:
  profiles: dev
foo:
  list:
     - name: my another name
```
在上面的示例中，考虑到dev配置文件处于活动状态，FooProperties.list将包含一个MyPojo条目（名称为“my another name”和description null）。
### 24.7 类型安全的配置属性
使用@Value(“$ {property}”)注释来注入配置属性有时可能很麻烦，特别是如果您正在使用多个属性或数据是层次结构的属性。 Spring Boot提供了一种处理属性的替代方法，允许强类型的bean来管理和验证应用程序的配置。

```
package com.example;

import java.net.InetAddress;
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

import org.springframework.boot.context.properties.ConfigurationProperties;

@ConfigurationProperties("foo")
public class FooProperties {

    private boolean enabled;

    private InetAddress remoteAddress;

    private final Security security = new Security();

    public boolean isEnabled() { ... }

    public void setEnabled(boolean enabled) { ... }

    public InetAddress getRemoteAddress() { ... }

    public void setRemoteAddress(InetAddress remoteAddress) { ... }

    public Security getSecurity() { ... }

    public static class Security {

        private String username;

        private String password;

        private List<String> roles = new ArrayList<>(Collections.singleton("USER"));

        public String getUsername() { ... }

        public void setUsername(String username) { ... }

        public String getPassword() { ... }

        public void setPassword(String password) { ... }

        public List<String> getRoles() { ... }

        public void setRoles(List<String> roles) { ... }

    }
}
```
上述POJO定义了以下属性：

* foo.enabled，默认为false
* foo.remote-address，具有可以从String强制类型转换的类型
* foo.security.username，具有嵌套的“安全性”，其名称由属性名称决定。 特别是返回类型并没有被使用，可能是SecurityProperties
* foo.security.password
* foo.security.roles，一个String集合

> Getters和setter通常是强制性的，因为绑定是通过标准的Java Beans属性描述符，就像在Spring MVC中一样。在某些情况下可能会省略setter：
Maps，只要它们被初始化，需要一个getter，但不一定是一个setter，因为它们可以被binder修改。
集合和数组可以通过索引（通常使用YAML）或使用单个逗号分隔值（属性）来访问。在后一种情况下，setter是强制性的。我们建议您始终为此类型添加一个setter。如果您初始化集合，请确保它不是不可变的（如上例所示）
如果已初始化嵌套POJO属性（如上例中的Security字段），则不需要setter。如果您希望binder使用其默认构造函数即时创建实例，则需要一个setter。
有些人使用Project Lombok自动添加getter和setter。确保Lombok不会为这种类型生成任何特定的构造函数，因为它将被容器自动用于实例化对象。
 另请参阅@Value和@ConfigurationProperties之间的差异。
 
 您还需要列出在@EnableConfigurationProperties注释中注册的属性类：
 
 ```
@Configuration
@EnableConfigurationProperties(FooProperties.class)
public class MyConfiguration {
}
 ```
 
 当
@ConfigurationProperties bean以这种方式注册时，该bean将具有常规名称：<prefix> - <fqn>，其中<prefix>是@ConfigurationProperties注释中指定的环境密钥前缀，<fqn>是Bean的全限定名称。 如果注解不提供任何前缀，则仅使用该bean的完全限定名称。

上面示例中的bean名称将是foo-com.example.FooProperties。

即使上述配置将为FooProperties创建一个常规bean，我们建议@ConfigurationProperties仅处理环境，特别是不从上下文中注入其他bean。 话虽如此，@EnableConfigurationProperties注释也会自动应用于您的项目，以便使用@ConfigurationProperties注释的任何现有的bean都将从环境配置。 您可以通过确保FooProperties已经是一个bean来快速上面的MyConfiguration。

```
@Component
@ConfigurationProperties(prefix="foo")
public class FooProperties {

    // ... see above

}
```
这种配置方式与SpringApplication外部的YAML配置相当：

```
#application.yml

foo:
    remote-address: 192.168.1.1
    security:
        username: foo
        roles:
          - USER
          - ADMIN

#additional configuration as required
```

要使用@ConfigurationProperties bean，您可以像其他任何bean一样注入它们。

```
@Service
public class MyService {

    private final FooProperties properties;

    @Autowired
    public MyService(FooProperties properties) {
        this.properties = properties;
    }

     //...

    @PostConstruct
    public void openConnection() {
        Server server = new Server(this.properties.getRemoteAddress());
        // ...
    }

}
```

使用@ConfigurationProperties还可以生成IDE可以为自己的密钥提供自动完成的元数据文件，有关详细信息，请参见附录B，配置元数据附录。

#### 24.7.1 第三方配置
除了使用@ConfigurationProperties来注释类，还可以在public @Bean方法中使用它。 当您希望将属性绑定到不受控制的第三方组件时，这可能特别有用。

要从“环境”属性配置一个bean，请将@ConfigurationProperties添加到其Bean注册中：

```
@ConfigurationProperties(prefix = "bar")
@Bean
public BarComponent barComponent() {
    ...
}
```
使用bar前缀定义的任何属性将以与上述FooProperties示例类似的方式映射到该BarComponent bean。

#### 24.7.2 宽松绑定
Spring Boot使用一些宽松的规则将环境属性绑定到@ConfigurationProperties bean，因此不需要在Environment属性名称和bean属性名称之间进行完全匹配。 常用的例子是这样有用的：虚分离（例如上下文路径绑定到contextPath）和大写（例如PORT绑定到端口）环境属性。

例如，给定以下@ConfigurationProperties类：

```
@ConfigurationProperties(prefix="person")
public class OwnerProperties {

    private String firstName;

    public String getFirstName() {
        return this.firstName;
    }

    public void setFirstName(String firstName) {
        this.firstName = firstName;
    }

}
```
可以使用以下属性名称：
#####表24.1 宽松绑定

属性|表示方式
----|------
person.firstName|	标准驼峰命名方式
person.first-name|	虚拟符号，建议使用in.properties和.xml文件。
person.first_name|	下划线符号，用于in.properties和.xml文件的替代格式。
PERSON_FIRST_NAME|	大写格式 使用系统环境变量时推荐这种方式。

#### 24.7.3 属性转换
当Spring绑定到@ConfigurationProperties bean时，Spring将尝试将外部应用程序属性强制转换为正确的类型。 如果需要自定义类型转换，您可以提供ConversionService bean（使用bean id conversionService）或自定义属性编辑器（通过CustomEditorConfigurer bean）或自定义转换器（使用注释为@ConfigurationPropertiesBinding的bean定义）。

> 由于在应用程序生命周期期间非常早请求此Bean，请确保限制ConversionService正在使用的依赖关系。 通常，您需要的任何依赖关系可能无法在创建时完全初始化。 如果配置密钥强制不需要，只需依赖使用@ConfigurationPropertiesBinding限定的自定义转换器，就可以重命名自定义ConversionService。

#### 24.7.4 @ConfigurationProperties验证
当Spring的@Validated注释注释时，Spring Boot将尝试验证@ConfigurationProperties类。 您可以直接在配置类上使用JSR-303 javax.validation约束注释。 只需确保您的类路径中符合JSR-303实现，然后在您的字段中添加约束注释：

```
@ConfigurationProperties(prefix="foo")
@Validated
public class FooProperties {

    @NotNull
    private InetAddress remoteAddress;

    // ... getters and setters

}

```
为了验证嵌套属性的值，您必须将关联字段注释为@Valid以触发其验证。 例如，基于上述FooProperties示例：

```
@ConfigurationProperties(prefix="connection")
@Validated
public class FooProperties {

    @NotNull
    private InetAddress remoteAddress;

    @Valid
    private final Security security = new Security();

    // ... getters and setters

    public static class Security {

        @NotEmpty
        public String username;

        // ... getters and setters

    }

}
```

您还可以通过创建名为configurationPropertiesValidator的bean定义来添加自定义的Spring Validator。 @Bean方法应声明为静态。 配置属性验证器在应用程序的生命周期早期创建，并声明@Bean方法，因为static允许创建bean，而无需实例化@Configuration类。 这避免了早期实例化可能引起的任何问题。 有一个属性验证样本，所以你可以看到如何设置。

> spring-boot-actuator模块包括一个暴露所有@ConfigurationProperties bean的端点。 只需将您的Web浏览器指向/ configprops或使用等效的JMX端点。 具体细节请参阅生产就绪功能那一章。

#### 24.7.5 @ConfigurationProperties和 @Value比较

Feature|	@ConfigurationProperties|	@Value
-------|--------------------------|-------
Relaxed binding	|Yes|	No
Meta-data support	|Yes|	No
SpELevaluation|	No|	Yes
如果您为自己的组件定义了一组配置keys，我们建议您将它们分组到使用@ConfigurationProperties注释的POJO中。 还请注意，由于@Value不支持轻松的绑定，如果您需要使用环境变量提供值，那么它不是一个很好的候选人。

最后，当您可以在@Value中编写一个SpEL表达式时，这些表达式不会从应用程序属性文件中处理。

## 25 Profile配置
spring boot Profile配置提供了隔离应用程序部分配置的方法，并使其仅在某些环境中可用。 任何@Component或@Configuration都可以使用@Profile进行标记，以限制其加载时间：

```
@Configuration
@Profile("production")
public class ProductionConfiguration {

    // ...

}
```
以普通的Spring方式，您可以使用spring.profiles.active Environment属性来指定哪些配置文件处于活动状态。 您可以以任何常规方式指定属性，例如，您可以将其包含在您的application.properties中：

```
spring.profiles.active=dev,hsqldb
```
或者使用命令行--spring.profiles.active = dev，hsqldb在命令行中指定。
#### 25.1 添加激活的profiles
spring.profiles.active属性遵循与其他属性相同的优先级排序规则，PropertySource的优先级最高。 这意味着您可以在application.properties中指定活动配置文件，然后使用命令行开关替换它们。

有时，将特定于配置文件的属性添加到活动配置文件而不是替换它们是有用的。 spring.profiles.include属性可用于无条件添加活动配置文件。 SpringApplication入口点还有一个用于设置其他配置文件的Java API（即，在由spring.profiles.active属性激活的配置文件之上）：请参阅setAdditionalProfiles（）方法。

例如，当使用switch -spring.profiles.active = prod运行具有以下属性的应用程序时，proddb和prodmq配置文件也将被激活：

```
---
my.property: fromyamlfile
---
spring.profiles: prod
spring.profiles.include:
  - proddb
  - prodmq
```

> 请记住，可以在YAML文档中定义spring.profiles属性，以确定此特定文档何时包含在配置中。 有关详细信息，请参见第72.7节“根据环境更改配置”。

### 25.2 通过编程设置profiles
您可以通过在应用程序运行之前调用SpringApplication.setAdditionalProfiles（...）以编程方式设置活动配置文件。 也可以使用Spring的ConfigurableEnvironment接口来激活配置文件。

### 25.3 Profile-specific配置文件
通过@ConfigurationProperties引用的application.properties（或application.yml）和文件的配置文件特定变体都被视为加载文件。 有关详细信息，请参见第24.4节“特定于配置文件的属性”。
## 26 日志
Spring Boot使用Commons Logging进行所有内部日志记录，但底层日志实现确实开放的。 默认的日志实现为Java Util Logging，Log4J2和Logback提供。 在每种情况下，记录器都预配置为使用控制台输出和可选文件输出。

默认情况下，如果使用'Starters'，spring boot将使用Logback记录日志。 还包括适当的Logback路由，以确保使用Java Util Logging，Commons Logging，Log4J或SLF4J的依赖库都能正常工作。

> 有很多可用于Java的日志记录框架。 如果上面的列表看起来很混乱，别担心。 一般来说，您不需要更改日志依赖关系，并且一般情况下Spring Boot的默认日志配置将正常工作。

### 26.1 日志格式
Spring Boot的默认日志输出格式如下：

```
2014-03-05 10:57:51.112  INFO 45469 --- [           main] org.apache.catalina.core.StandardEngine  : Starting Servlet Engine: Apache Tomcat/7.0.52
2014-03-05 10:57:51.253  INFO 45469 --- [ost-startStop-1] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring embedded WebApplicationContext
2014-03-05 10:57:51.253  INFO 45469 --- [ost-startStop-1] o.s.web.context.ContextLoader            : Root WebApplicationContext: initialization completed in 1358 ms
2014-03-05 10:57:51.698  INFO 45469 --- [ost-startStop-1] o.s.b.c.e.ServletRegistrationBean        : Mapping servlet: 'dispatcherServlet' to [/]
2014-03-05 10:57:51.702  INFO 45469 --- [ost-startStop-1] o.s.b.c.embedded.FilterRegistrationBean  : Mapping filter: 'hiddenHttpMethodFilter' to: [/*]
```

输出的日志包括如下几个部分：
* 日期和时间 - 毫秒精度和容易排序。
* 日志级别 - ERROR、WARN、INFO、DEGUB和TRACE。
* 进程ID。
* A ---分隔符来区分实际日志消息的开始。
* 线程名称 - 括在方括号中（可能会截断控制台输出）。
* 记录器名称 - 这通常是源类名（通常缩写）。
* 日志消息。

> 注意：Logback没有FATAL日志级别（映射到ERROR级别）

### 26.2 控制台输出日志
默认的日志配置将在写入控制台时回显消息。 默认情况下会记录ERROR，WARN和INFO级别的消息。 您还可以通过启动您的应用程序--debug标志来启用“调试”模式。

```
$ java -jar myapp.jar --debug
```

> 您还可以在application.properties中指定debug = true。

当启用调试模式时，配置核心记录器（嵌入式容器，Hibernate和Spring Boot）的选择可以输出更多信息。 启用调试模式不会将应用程序配置为使用DEBUG级别记录所有消息。

或者，您可以使用--trace标志启动应用程序（或在您的application.properties中为trace = true）启用“跟踪”模式。 这将为选择的核心记录器（嵌入式容器，Hibernate模式生成和整个Spring组合）启用跟踪记录。

#### 26.2.1 日志彩色编码输出

如果您的终端支持ANSI，日志将会以彩色编码的形式输出，这将有助于可读性。 您可以将spring.output.ansi.enabled设置为支持的值来覆盖自动检测。

使用％clr转换字配置色彩编码。 在最简单的形式下，转换器将根据日志级别对输出进行着色，例如：

```
%clr(%5p)
```

日志级别映射到颜色如下：

Level  |	Color
-------|-----
FATAL	|Red
ERROR	|Red
WARN	|Yellow
INFO	|Green
DEBUG	|Green
TRACE	|Green
或者，您可以通过将其提供为转换选项来指定应使用的颜色或样式。 例如，要使文本变黄：

```
%clr(%d{yyyy-MM-dd HH:mm:ss.SSS}){yellow}
```

spring boot支持以下颜色和样式：

* blue
* cyan
* faint
* green
* magenta
* red
* yellow

### 26.3 文件日志输出
默认情况下，Spring Boot只是将日志输出到控制台，不会写入到日志文件中。 如果需要除控制台输出之外的日志文件，则需要设置logging.file或logging.path属性（例如在application.properties中）。

下表显示了如何一起使用logging.*属性：

logging.file	|logging.path|	Example|	Description
----------|---------------|----------|-------------
(none)|	(none)	||只输出到控制台.
Specific file	|(none)	|my.log	|写入指定的日志文件。 名称可以是确切的位置或相对于当前目录。
(none)	|Specific directory|	/var/log|	将spring.log写入指定的目录。 名称可以是确切的位置或相对于当前目录。
日志文件将在10 MB时旋转，默认情况下会记录控制台输出，ERROR，WARN和INFO级别的消息。

> 日志记录系统在应用程序生命周期早期初始化，并且在通过@PropertySource注释加载的属性文件中将不会找到记录属性。

> 日志属性独立于实际的日志底层实现。 因此，特定配置key（如Logback的logback.configurationFile）不受spring boot管理。

### 26.4 日志级别
所有支持的日志记录系统都可以在Spring环境中设置记录级别（例如在application.properties中），使用'logging.level.* = LEVEL'，其中'LEVEL'是TRACE，DEBUG，INFO，WARN，ERROR，FATAL, OFF之一 。 可以使用logging.level.root配置根记录器。 示例application.properties：

```
logging.level.root=WARN
logging.level.org.springframework.web=DEBUG
logging.level.org.hibernate=ERROR
```

默认情况下，Spring Boot会重新映射Thymeleaf INFO消息，以便它们以DEBUG级别进行记录。 这有助于降低标准日志输出中的噪音。 有关如何在自己的配置中应用重映射的详细信息，请参阅LevelRemappingAppender。

### 26.5 自定义日志配置
可以通过在类路径中包含相应的库来激活各种日志记录系统，并通过在类路径的根目录中提供合适的配置文件，或在Spring Environment属性logging.config指定的位置进一步定制。

您可以强制Spring Boot使用org.springframework.boot.logging.LoggingSystem系统属性使用特定的日志记录系统。 该值应该是LoggingSystem实现的全限定类名。 您还可以使用无值的值完全禁用Spring Boot的日志记录配置。

> 由于在创建ApplicationContext之前初始化日志记录，因此无法在Spring @Configuration文件中控制@PropertySources的日志记录。 系统属性和常规的Spring Boot外部配置文件工作正常。）

根据您的日志记录系统，将会加载以下文件：

Logging| SystemCustomization
-------|-------------------
Logback|logback-spring.xml,logback-spring.groovy,logback.xmlorlogback.groovy
Log4j2|log4j2-spring.xmlorlog4j2.xml
JDK (Java Util Logging)|logging.properties
> 如果可能，我们建议您使用-spring变体进行日志记录配置（例如logback-spring.xml而不是logback.xml）。 如果使用标准配置位置，则Spring无法完全控制日志初始化。

> Java Util Logging存在已知的类加载问题，从“可执行jar”运行时会导致问题。 我们建议您尽可能避免。

为了帮助定制，一些其他属性从Spring环境转移到系统属性：

Spring Environment|	System Property|	Comments
-------------------|---------------|---------
logging.exception-conversion-word|	LOG_EXCEPTION_CONVERSION_WORD	|当日志出现异常时的conversion word
logging.file	|LOG_FILE|	如果定义，用于默认日志配置。
logging.path	|LOG_PATH|	如果定义，用于默认日志配置。
logging.pattern.console	|CONSOLE_LOG_PATTERN	|在控制台上使用的日志模式（stdout）。 （仅支持默认logbach设置。）
logging.pattern.file|	FILE_LOG_PATTERN	|在文件中使用的日志模式（如果LOG_FILE已启用）。 （仅支持默认logback设置。）
logging.pattern.level	|LOG_LEVEL_PATTERN	|用于呈现日志级别的格式（默认％5p）。 （仅支持默认logback设置。）
PID|	PID	|当前进程ID（如果可能的话，当未被定义为OS环境变量时）被发现。
支持的所有日志记录系统在分析其配置文件时可以查看系统属性。 有关示例，请参阅spring-boot.jar中的默认配置。

## 27 开发Web应用
Spring Boot非常适合Web应用程序开发。 您可以使用嵌入式Tomcat，Jetty或Undertow轻松创建自包含的HTTP服务器。 大多数Web应用程序将使用spring-boot-starter-web模块快速启动和运行。

如果您尚未开发Spring Boot Web应用程序，则可以按照“Hello World！”进行操作。 在“入门”部分中的示例。

### 27.1 Spring Web MVC框架
Spring Web MVC框架（通常简称为“Spring MVC”）是一个丰富的“模型视图控制器”Web框架。 Spring MVC允许您创建特殊的@Controller或@RestController bean来处理传入的HTTP请求。 您的控制器中的方法将使用@RequestMapping注释映射到HTTP。

以下是@RestController用于提供JSON数据的典型示例：

```
@RestController
@RequestMapping(value="/users")
public class MyRestController {

    @RequestMapping(value="/{user}", method=RequestMethod.GET)
    public User getUser(@PathVariable Long user) {
        // ...
    }

    @RequestMapping(value="/{user}/customers", method=RequestMethod.GET)
    List<Customer> getUserCustomers(@PathVariable Long user) {
        // ...
    }

    @RequestMapping(value="/{user}", method=RequestMethod.DELETE)
    public User deleteUser(@PathVariable Long user) {
        // ...
    }

}
```

Spring MVC是核心Spring Framework的一部分，详细信息可参阅参考文档。 Spring.io / guide中还有几个指南可供Spring MVC使用。

#### 27.1.1 Spring MVC自动配置
Spring Boot提供了适用于大多数应用程序的Spring MVC的自动配置。

* 自动配置在Spring的默认值之上添加以下功能：
* 包含ContentNegotiatingViewResolver和BeanNameViewResolver bean。
* 支持提供静态资源，包括对WebJars的支持（见下文）。
* Converter，GenericConverter，Formatter beans的自动注册。
* 支持HttpMessageConverters（见下文）。
* 自动注册MessageCodesResolver（见下文）。
* 静态index.html支持。
* 自定义Favicon支持（见下）。
* 自动使用ConfigurableWebBindingInitializer bean（见下文）。


如果要保留Spring Boot MVC功能，并且您只需要添加其他MVC配置（拦截器，格式化程序，视图控制器等），则可以添加自己的WebConfigurerAdapter类型的@Configuration类，但不能使用@EnableWebMvc。 如果要提供RequestMappingHandlerMapping，RequestMappingHandlerAdapter或ExceptionHandlerExceptionResolver的自定义实例，您可以声明一个提供此类组件的WebMvcRegistrationsAdapter实例。

如果要完全控制Spring MVC，可以使用@EnableWebMvc添加您自己的@Configuration注释。

#### 27.1.2 HttpMessageConverters
Spring MVC使用HttpMessageConverter接口转换HTTP请求和响应。 spring boot 提供了开箱即用的默认值，例如对象可以自动转换为JSON（使用Jackson库）或XML（使用Jackson XML扩展，如果可用，否则使用JAXB）。 字符串默认使用UTF-8进行编码。

如果需要添加或自定义转换器，可以使用Spring Boot的HttpMessageConverters类：

```
import org.springframework.boot.autoconfigure.web.HttpMessageConverters;
import org.springframework.context.annotation.*;
import org.springframework.http.converter.*;

@Configuration
public class MyConfiguration {

    @Bean
    public HttpMessageConverters customConverters() {
        HttpMessageConverter<?> additional = ...
        HttpMessageConverter<?> another = ...
        return new HttpMessageConverters(additional, another);
    }

}
```
上下文中存在的任何HttpMessageConverter bean将被添加到转换器列表中。 您也可以以这种方式覆盖默认转换器。

#### 27.1.3 自定义JSON序列化和反序列化
如果您使用Jackson序列化和反序列化JSON数据，则可能需要编写自己的JsonSerializer和JsonDeserializer类。 自定义序列化程序通常通过一个模块注册到Jackson，但是Spring Boot提供了一个备用的@JsonComponent注释，可以更容易地直接注册Spring Bean。

您可以直接在JsonSerializer或JsonDeserializer实现中使用@JsonComponent。 您也可以将它用于包含序serializers/deserializers的类作为内部类。 例如：

```
import java.io.*;
import com.fasterxml.jackson.core.*;
import com.fasterxml.jackson.databind.*;
import org.springframework.boot.jackson.*;

@JsonComponent
public class Example {

    public static class Serializer extends JsonSerializer<SomeObject> {
        // ...
    }

    public static class Deserializer extends JsonDeserializer<SomeObject> {
        // ...
    }

}
```
ApplicationContext中的所有@JsonComponent bean将自动注册到Jackson，并且由于@JsonComponent是使用@Component进行元注释的，所以常规的组件扫描规则适用。

Spring Boot还提供了JsonObjectSerializer和JsonObjectDeserializer基类，它们在序列化对象时为标准的Jackson版本提供了有用的替代方法。 有关详细信息，请参阅Javadoc。

#### 27.1.4 MessageCodesResolver
Spring MVC有一个生成错误代码的策略，用于从绑定错误中提取错误消息：MessageCodesResolver。 如果您设置spring.mvc.message-codes-resolver.format属性PREFIX_ERROR_CODE或POSTFIX_ERROR_CODE（请参阅DefaultMessageCodesResolver.Format中的枚举），Spring Boot将为您创建一个。

#### 27.1.5 静态内容
默认情况下，Spring Boot从classpath下的`/static`（`/public`，`/resources`或`/META-INF/resources`）文件夹，或从`ServletContext`根目录提供静态内容。这是通过Spring MVC的`ResourceHttpRequestHandler`实现的，你可以自定义`WebMvcConfigurerAdapter`并覆写`addResourceHandlers`方法来改变该行为（加载静态文件）。

在单机web应用中，容器会启动默认的servlet，并用它加载`ServletContext`根目录下的内容以响应那些Spring不处理的请求。大多数情况下这都不会发生（除非你修改默认的MVC配置），因为Spring总能够通过`DispatcherServlet`处理这些请求。

默认情况下，资源映射到/ **，但可以通过spring.mvc.static-path-pattern来设置。 例如，将所有资源重定位到/ resources / **可以实现如下：

```
spring.mvc.static-path-pattern=/resources/**
```

您还可以使用spring.resources.static-locations（使用目录位置列表替换默认值）来自定义静态资源位置。 如果这样做，默认的欢迎页面检测将切换到您的自定义位置，因此，如果在启动时您的任何位置中有一个index.html，它将是应用程序的主页。

除了上述“标准”静态资源位置之外，还提供了一个特殊情况用于Webjars内容。 如果使用Webjars格式打包，则/ jarjars / **中具有路径的资源将从jar文件中提供。

> 如果您的应用程序将被打包为jar，请不要使用src/main/webapp目录。 虽然这个目录是一个通用的标准，但它只适用于war包，如果生成一个jar，它将被大多数构建工具忽略。

Spring Boot也支持Spring MVC提供的高级资源处理特性，可用于清除缓存的静态资源或对WebJar使用版本无感知的URLs。

如果想使用针对WebJars版本无感知的URLs（version agnostic），只需要添加`webjars-locator`依赖，然后声明你的Webjar。以jQuery为例，`"/webjars/jquery/dist/jquery.min.js"`实际为`"/webjars/jquery/x.y.z/dist/jquery.min.js"`，`x.y.z`为Webjar的版本。

如果使用JBoss，你需要声明`webjars-locator-jboss-vfs`依赖而不是`webjars-locator`，否则所有的Webjars将解析为`404`。

要使用缓存清除功能，以下配置将为所有静态资源配置缓存清除解决方案，该方案通过在URL中添加哈希值来实现，例如：

```
<link href="/css/spring-2a2d595e6ed9a0b24f027f2b63b134d6.css"/>:
spring.resources.chain.strategy.content.enabled=true
spring.resources.chain.strategy.content.paths=/**
```

对于Thymeleaf和FreeMarker模版引擎来说，在模版运行时会进行资源链接重写，这通过spring boot自动配置的ResourceUrlEncodingFilter来实现。当使用JSP时，应手动声明此过滤器。 其他模板引擎现在不会自动支持，但可以使用自定义模板宏/帮助程序和使用ResourceUrlProvider。

当使用比如JavaScript模块加载器动态加载资源时，重命名文件是不行的，这也是提供其他策略并能结合使用的原因。下面是一个"fixed"策略，在URL中添加一个静态version字符串而不需要改变文件名：

```
spring.resources.chain.strategy.content.enabled=true
spring.resources.chain.strategy.content.paths=/**
spring.resources.chain.strategy.fixed.enabled=true
spring.resources.chain.strategy.fixed.paths=/js/lib/
spring.resources.chain.strategy.fixed.version=v12
```
使用以上策略，JavaScript模块加载器加载`"/js/lib/"`下的文件时会使用一个固定的版本策略`"/v12/js/lib/mymodule.js"`，其他资源仍旧使用内容hash的方式`<link href="/css/spring-2a2d595e6ed9a0b24f027f2b63b134d6.css"/>`。查看[ResourceProperties](https://github.com/spring-projects/spring-boot/tree/v1.5.3.RELEASE/spring-boot-autoconfigure/src/main/java/org/springframework/boot/autoconfigure/web/ResourceProperties.java)获取更多支持的选项。

此功能已在专门的博客文章和Spring Framework参考文档中进行了详细描述。

#### 27.1.6 自定义ICON
Spring Boot在配置的静态内容位置和类路径的根目录（按顺序）中查找favicon.ico。 如果这样的文件存在，它将被自动用作应用程序的图标。
#### 27.1.7 ConfigurableWebBindingInitializer
Spring MVC使用WebBindingInitializer为特定请求初始化WebDataBinder。 如果您创建自己的ConfigurableWebBindingInitializer @Bean，Spring Boot将自动配置Spring MVC以使用它。

#### 27.1.8 模版引擎
除了REST Web服务，您还可以使用Spring MVC来提供动态HTML内容。 Spring MVC支持各种模板技术，包括Thymeleaf，FreeMarker和JSP。 许多其他模板引擎也运行自己的Spring MVC集成。

Spring Boot包括对以下模板引擎的自动配置支持：

* FreeMarker
* Groovy
* Thymeleaf
* Mustache
如果可能，当使用嵌入式servlet容器时，应避免使用JSP，JSP在jar包运行时有几个的限制。

当您使用默认配置的模板引擎之一时，您的模板将从src / main / resources / templates自动获取。

> IntelliJ IDEA根据运行应用程序的方式对类路径进行不同的排序。 通过其主要方法在IDE中运行应用程序将导致使用Maven或Gradle或其打包的jar运行应用程序时的不同顺序。 这可能会导致Spring Boot找不到类路径上的模板。 如果您受到此问题的影响，您可以重新排序IDE中的类路径，以便首先放置模块的类和资源。 或者，您可以配置模板前缀以搜索类路径上的每个模板目录：classpath *：/ templates /。

#### 27.1.9 错误处理
默认情况下，Spring Boot提供/error映射，以合理的方式处理所有错误，并在servlet容器中注册为“全局”错误页面。 对于机器客户端，它将产生一个JSON响应，其中包含错误，HTTP状态和异常消息的详细信息。 对于浏览器客户端，有一个“whitelabel”错误视图，以HTML格式呈现相同的数据（以自定义它，只需添加一个解析为“错误”的视图）。 要完全替换默认行为，您可以实现ErrorController并注册该类型的bean定义，或者简单地添加一个类型为ErrorAttributes的bean来使用现有机制，但是替换内容。

> BasicErrorController可以用作自定义ErrorController的基类。 如果要添加新内容类型的处理程序（默认情况下是专门处理text / html并为其他内容提供后备,这一点尤其有用）。 要实现自定义错误处理功能，只需扩展BasicErrorController并添加一个带有 @RequestMapping注解和produces属性的公共方法，并创建一个新类型的bean。

你还可以定义一个@ControllerAdvice来为特定控制器和/或异常类型返回JSON格式的文档。

```
@ControllerAdvice(basePackageClasses = FooController.class)
public class FooControllerAdvice extends ResponseEntityExceptionHandler {

    @ExceptionHandler(YourException.class)
    @ResponseBody
    ResponseEntity<?> handleControllerException(HttpServletRequest request, Throwable ex) {
        HttpStatus status = getStatus(request);
        return new ResponseEntity<>(new CustomErrorType(status.value(), ex.getMessage()), status);
    }

    private HttpStatus getStatus(HttpServletRequest request) {
        Integer statusCode = (Integer) request.getAttribute("javax.servlet.error.status_code");
        if (statusCode == null) {
            return HttpStatus.INTERNAL_SERVER_ERROR;
        }
        return HttpStatus.valueOf(statusCode);
    }

}
```
在上面的示例中，如果在与FooController相同的包中定义的控件抛出了YourException，则将使用CustomerErrorType POJO的json表示法而不是ErrorAttributes表示形式。

##### 自定义错误页面
如果要显示给定状态代码的自定义HTML错误页面，请将文件添加到/ error文件夹。 错误页面可以是静态HTML（即添加在任何静态资源文件夹下）或使用模板构建。 该文件的名称应该是确切的状态代码或一个系列掩码。

例如，要将404映射到静态HTML文件，您的文件夹结构将如下所示：

```
src/
 +- main/
     +- java/
     |   + <source code>
     +- resources/
         +- public/
             +- error/
             |   +- 404.html
             +- <other public assets>
```
要使用FreeMarker模板映射所有5xx错误，您的文件夹结构将如下所示：

```
src/
 +- main/
     +- java/
     |   + <source code>
     +- resources/
         +- templates/
             +- error/
             |   +- 5xx.ftl
             +- <other templates>
```

对于更复杂的错误映射，您还可以添加实现ErrorViewResolver接口的bean。

```
public class MyErrorViewResolver implements ErrorViewResolver {

    @Override
    public ModelAndView resolveErrorView(HttpServletRequest request,
            HttpStatus status, Map<String, Object> model) {
        // Use the request or status to optionally return a ModelAndView
        return ...
    }

}
```
您还可以使用常规Spring MVC功能，如@ExceptionHandler方法和@ControllerAdvice。 然后，ErrorController将接收任何未处理的异常。

##### 非Spring MVC程序的错误映射
对于不使用Spring MVC的应用程序，可以使用ErrorPageRegistrar接口直接注册ErrorPages。 这个抽象直接与底层的嵌入式servlet容器一起工作，即使没有Spring MVC DispatcherServlet也可以工作。

```
@Bean
public ErrorPageRegistrar errorPageRegistrar(){
    return new MyErrorPageRegistrar();
}

// ...

private static class MyErrorPageRegistrar implements ErrorPageRegistrar {

    @Override
    public void registerErrorPages(ErrorPageRegistry registry) {
        registry.addErrorPages(new ErrorPage(HttpStatus.BAD_REQUEST, "/400"));
    }

}
```
注： 如果您注册一个最终由Filter过滤的路径的ErrorPage（例如，与某些非Spring Web框架（例如Jersey和Wicket）相同），则必须将Filter显式注册为ERROR调度程序。

```
@Bean
public FilterRegistrationBean myFilter() {
    FilterRegistrationBean registration = new FilterRegistrationBean();
    registration.setFilter(new MyFilter());
    ...
    registration.setDispatcherTypes(EnumSet.allOf(DispatcherType.class));
    return registration;
}
```
（默认的FilterRegistrationBean不包括ERROR调度程序类型）。
##### WebSphere服务器的错误处理
当部署到servlet容器时，Spring Boot使用其错误页面过滤器将具有错误状态的请求转发到相应的错误页面。 如果响应尚未提交，则该请求只能转发到正确的错误页面。 默认情况下，WebSphere Application Server 8.0和更高版本在成功完成servlet的服务方法后提交响应。 您应该通过将com.ibm.ws.webcontainer.invokeFlushAfterService设置为false来禁用此行为。

#### 27.1.10 Spring HATEOAS
如果您正在开发一种利用超媒体的RESTful API，Spring Boot可为Spring HATEOAS提供自动配置，适用于大多数应用程序。 自动配置取代了使用@EnableHypermediaSupport的需要，并注册了一些Bean来简化构建基于超媒体的应用程序，包括LinkDiscoverers（用于客户端支持）和配置为将响应正确地组织到所需表示中的ObjectMapper。 ObjectMapper将根据spring.jackson。*属性或Jackson2ObjectMapperBuilder bean（如果存在）进行自定义。

您可以使用@EnableHypermediaSupport控制Spring HATEOAS的配置。 请注意，这将禁用上述的ObjectMapper自定义。

#### 27.1.11 CORS的支持
跨域资源共享（CORS）是大多数浏览器支持的W3C规范，允许您以灵活的方式指定什么样的跨域请求被授权，而不是使用如IFRAME或JSONP等一些不太安全和不太强大的方法。

从版本4.2起，Spring MVC支持CORS开箱即用。 在Spring Boot应用程序中使用@CrossOrigin注解标记控制器中的方法即可实现CORS配置，这里不需要任何额外的配置。 可以通过使用自定义的addCorsMappings（CorsRegistry）方法注册WebMvcConfigurer bean来定义全局CORS配置：

```
@Configuration
public class MyConfiguration {

    @Bean
    public WebMvcConfigurer corsConfigurer() {
        return new WebMvcConfigurerAdapter() {
            @Override
            public void addCorsMappings(CorsRegistry registry) {
                registry.addMapping("/api/**");
            }
        };
    }
}
```

### 27.2 JAX-RS和Jersey
如果您喜欢用于REST端点的JAX-RS编程模型，则可以使用其中一个可用的实现而不是Spring MVC。 如果您只是在应用程序上下文中注册他们的Servlet或Filter 作为@Bean，那么Jersey 1.x和Apache CXF的功能非常出色。 Jersey2.x有一些本地Spring支持，所以我们也提供自动配置支持在Spring Boot与相应的starter。

要开始使用Jersey 2.x，只需将spring-boot-starter-jersey作为依赖项，然后需要一个@Bean类型的ResourceConfig，您可以在其中注册所有端点：

```
@Component
public class JerseyConfig extends ResourceConfig {

    public JerseyConfig() {
        register(Endpoint.class);
    }

}
```
> Jersey对扫描可执行文件的支持是相当有限的。 例如，当运行可执行的war文件时，它无法扫描在WEB-INF / classes中找到的包中的端点。 为了避免这种限制，不应使用软件包方法，并且应使用上述寄存器方法单独注册端点。

您还可以注册任意数量的Bean，实现ResourceConfigCustomizer以实现更高级的自定义。

所有注册的端点都应为具有HTTP资源注释（@GET等）的@Components，例如。

```
@Component
@Path("/hello")
public class Endpoint {

    @GET
    public String message() {
        return "Hello";
    }

}
```

由于Endpoint是一个Spring @Component，它的生命周期由Spring管理，您可以使用@Autowired进行依赖注入或者使用@Value注入外部配置。默认情况下，Jersey servlet将被注册并映射到/ *。您可以通过将@ApplicationPath添加到ResourceConfig来更改映射。

默认情况下，Jersey将以名为jerseyServletRegistration的ServletRegistrationBean类型的@Bean中设置为Servlet。默认情况下，servlet将被初始化，但是您可以使用spring.jersey.servlet.load-on-startup进行自定义。您可以通过创建自己的同一个名称来禁用或覆盖该bean。您也可以通过设置spring.jersey.type = filter（在这种情况下，@Bean来替换或替换为jerseyFilterRegistration），使用Filter代替Servlet。 servlet有一个@Order，您可以使用spring.jersey.filter.order设置。可以使用spring.jersey.init。*来指定Servlet和过滤器注册初始化参数，以指定属性的映射。

这里有一个Jersey示例，所以你可以看到如何设置。还有一个Jarsey1.x示例。请注意，在Jersey1.x示例中，spring-boot maven插件已经被配置为打开一些Jersey jar，以便可以通过JAX-RS实现扫描（因为示例要求它们在其Filter注册中进行扫描） 。如果您的任何JAX-RS资源被打包为嵌套的jar，您可能需要执行相同操作。

### 27.3 嵌入式Servlet容器
Spring Boot支持嵌入式Tomcat，Jetty和Undertow服务器。 大多数开发人员将简单地使用适当的“Starter”来获取完全配置的实例。 默认情况下，嵌入式服务器将侦听端口8080上的HTTP请求。

> 如果您选择在CentOS上使用Tomcat，请注意，默认情况下，临时目录用于存储编译的JSP，文件上传等。当您的应用程序运行时导致故障时，该目录可能会被tmpwatch删除。 为了避免这种情况，您可能需要自定义tmpwatch配置，以便tomcat *目录不被删除，或配置server.tomcat.basedir，以便嵌入式Tomcat使用不同的位置。

#### 27.3.1 Servlets, Filters, and listeners
使用嵌入式servlet容器时，可以通过使用Spring bean或通过扫描Servlet组件从Servlet规范（例如HttpSessionListener）注册Servlet，过滤器和所有监听器。

##### 注册Servlets, Filters, and listeners作为 Spring beans
任何Servlet，Filter或Servlet *作为Spring bean的Listener实例将被注册到嵌入式容器中。 如果要在配置过程中引用application.properties中的值，这可能会特别方便。

默认情况下，如果上下文只包含一个Servlet，它将映射到/。 在多个Servlet bean的情况下，bean名称将被用作路径前缀。 过滤器将映射到/ *。

如果基于约定的映射不够灵活，可以使用ServletRegistrationBean，FilterRegistrationBean和ServletListenerRegistrationBean类进行完全控制。

#### 27.3.2 Servlet Context初始化
嵌入式servlet容器不会直接执行Servlet 3.0+ javax.servlet.ServletContainerInitializer接口或Spring的org.springframework.web.WebApplicationInitializer接口。 这种设计旨在降低war包中运行的第三方库的风险，从而不破坏Spring Boot应用程序。

如果您需要在Spring Boot应用程序中执行servlet上下文初始化，则应注册一个实现org.springframework.boot.context.embedded.ServletContextInitializer接口的bean。 单个onStartup方法提供对ServletContext的访问，并且如果需要，可以轻松地用作现有WebApplicationInitializer的适配器。

##### 扫描Servlets, Filters, and listeners
使用嵌入式容器时，可以使用@ServletComponentScan启用@WebServlet，@WebFilter和@WebListener注释类的自动注册。

> @ServletComponentScan将在独立容器中不起作用，其中将使用容器的内置发现机制。

#### 27.3.3 EmbeddedWebApplicationContext
在引导下，Spring Boot使用一种新型的ApplicationContext来嵌入式的servlet容器支持。 EmbeddedWebApplicationContext是一种特殊类型的WebApplicationContext，它通过搜索单个EmbeddedServletContainerFactory bean来引导自身。 通常，TomcatEmbeddedServletContainerFactory，JettyEmbeddedServletContainerFactory或UndertowEmbeddedServletContainerFactory将被自动配置。

> 您通常不需要知道这些实现类。 大多数应用程序将被自动配置，并将创建适当的ApplicationContext和EmbeddedServletContainerFactory。

#### 27.3.4 自定义嵌入式servlet容器
可以使用Spring Environment属性配置常见的servlet容器设置。 通常您可以在application.properties文件中定义属性。

常用服务器设置包括：

* 网络设置：监听HTTP请求的端口（server.port），绑定到server.address的接口地址等
* 会话设置：会话是否持久（server.session.persistence），会话超时（server.session.timeout），会话数据的位置（server.session.store-dir）和会话cookie配置（server.session.cookie。*）。
* 错误管理：错误页面的位置（server.error.path）等
* SSL
* HTTP压缩
Spring Boot尝试尽可能公开常见的设置，但并不总是可能的。 对于这些情况，专用命名空间提供服务器特定的定制（请参阅server.tomcat和server.undertow）。 例如，可以使用嵌入式servlet容器的特定功能来配置访问日志。

有关完整列表，请参阅ServerProperties类。

程序化定制
如果您需要以编程方式配置嵌入式servlet容器，则可以注册实现EmbeddedServletContainerCustomizer接口的Spring bean。 EmbeddedServletContainerCustomizer提供对ConfigurableEmbeddedServletContainer的访问，其中包含许多自定义设置器方法。

```
import org.springframework.boot.context.embedded.*;
import org.springframework.stereotype.Component;

@Component
public class CustomizationBean implements EmbeddedServletContainerCustomizer {

    @Override
    public void customize(ConfigurableEmbeddedServletContainer container) {
        container.setPort(9000);
    }

}
```
##### 自定义ConfigurableEmbeddedServletContainer容器
如果上述定制技术太有限，您可以自己注册TomcatEmbeddedServletContainerFactory，JettyEmbeddedServletContainerFactory或UndertowEmbeddedServletContainerFactory bean。

```
@Bean
public EmbeddedServletContainerFactory servletContainer() {
    TomcatEmbeddedServletContainerFactory factory = new TomcatEmbeddedServletContainerFactory();
    factory.setPort(9000);
    factory.setSessionTimeout(10, TimeUnit.MINUTES);
    factory.addErrorPages(new ErrorPage(HttpStatus.NOT_FOUND, "/notfound.html"));
    return factory;
}
```
spring boot提供了许多配置选项。 如果您需要做更多的配置，spring boot还提供几种保护方法“钩子”。 有关详细信息，请参阅源代码文档。

### 27.3.5 JSP的局限
当运行使用嵌入式servlet容器（并打包为可执行jar）的Spring Boot应用程序时，JSP支持有一些限制。

使用Tomcat，如果您使用war包装，即可执行的war将会起作用，并且还可以部署到标准容器（不限于但包括Tomcat），那么它应该可以工作。 由于Tomcat中的硬编码文件模式，可执行的jar将无法正常工作。

对于Jetty，如果您使用war包，即可执行的war将会起作用，并且还可以部署到任何标准的集装箱，它应该可以工作。

Undertow不支持JSP。

创建自定义的error.jsp页面不会覆盖错误处理的默认视图，而应该使用自定义错误页面。

有一个JSP示例，所以你可以看到如何设置。

## 28 Security
如果Spring Security位于类路径上，则默认情况下，Web应用程序将在所有HTTP端点上使用“basic”身份验证。 要向Web应用程序添加方法级安全性，您还可以使用所需的设置添加@EnableGlobalMethodSecurity。 有关更多信息，请参见“Spring Security Reference”。

默认的AuthenticationManager有一个用户（'user'用户名和随机密码，该随机密码在应用程序启动时以INFO级别打印）

```
Using default security password: 78fa095d-3f4c-48b1-ad50-e24c31d5cf35
```
如果您修改了日志记录配置，请确保将org.springframework.boot.autoconfigure.security的日志级别设置为记录INFO级别，否则将不会打印默认密码。

您可以通过提供security.user.password来更改密码。 这个属性和其的属性一样可以通过SecurityProperties（属性前缀“security”）进行外部化配置。

默认的安全配置在SecurityAutoConfiguration和从那里导入的类中实现（SpringBootWebSecurityConfiguration用于Web安全性和AuthenticationManagerConfiguration用于认证配置，这在非Web应用程序中也是相关的）。要完全关闭默认Web应用程序安全配置，您可以使用@EnableWebSecurity添加一个bean（这不会禁用身份验证管理器配置或Actuator的安全性）。要定制它，您通常使用WebSecurityConfigurerAdapter类型的外部属性和bean（例如添加基于表单的登录）。要关闭身份验证管理器配置，您可以添加AuthenticationManager类型的bean，或者通过将AuthenticationManagerBuilder自动连接到您的一个@Configuration类中的方法来配置全局AuthenticationManager。 Spring Boot示例中有几个安全应用程序可以让您开始使用常见的用例。

您在Web应用程序中获得的基本功能包括：

* 具有内存存储和单个用户的AuthenticationManager Bean（请参阅用于用户属性的SecurityProperties.User）。
* 常见静态资源位置（/ css / **，/ js / **，/ images / **，/ webjars / **和** / favicon.ico）的忽略（不安全）路径。
* HTTP所有其他端点的基本安全性。
* 安全事件发布到Spring的ApplicationEventPublisher（成功和不成功的身份验证和访问被拒绝）。
* 默认情况下，Spring Security提供的常见的低级功能（HSTS，XSS，CSRF，缓存）都是打开的。

所有上述可以使用外部属性（security.*）打开和关闭或修改。要覆盖访问规则而不更改任何其他自动配置的功能，请使用@Order（SecurityProperties.ACCESS_OVERRIDE_ORDER）添加一个类型为WebSecurityConfigurerAdapter的@Bean，并配置它以满足您的需要。

> 默认情况下，WebSecurityConfigurerAdapter将匹配任何路径。 如果您不想完全覆盖Spring Boot自动配置的访问规则，则适配器必须显式配置您要覆盖的路径。

### 28.1 OAuth2
# 第五部分 spring boot 执行器：产品上线特性
# 第六部分 部署spring boot应用程序
Spring Boot灵活的打包命令选项为部署应用程序提供了很多便利的选择。 您可以轻松地将Spring Boot应用程序部署到各种云平台，容器映像（如Docker）或虚拟/真实机器上。

本节介绍一些更常见的部署方案。
## 58 部署到云端
Spring Boot的可执行jar是为大多数流行的云PaaS（平台即服务）提供商而准备的。这些提供者往往要求你“带自己的容器”;他们管理应用程序进程（而不是Java应用程序），因此他们需要一些中间层，使您的应用程序适应云计算流程的概念。

两个流行的云供应商Heroku和Cloud Foundry采用“buildpack”方式。buildpack将您部署的代码封装在启动应用程序所需的任何内容中：它可能是JDK和对java的调用，它可能是嵌入式Web服务器，也可能是一个成熟的应用程序服务器。 buildpack是可插拔的，但理想情况下，您应该能够尽可能少的自定义。这减少了不受您控制的功能的占用。它最大限度地减少开发和生产环境之间的差异。

理想情况下，您的应用程序，像一个Spring Boot可执行jar，具有在其中运行打包所需的一切。

在本节中，我们将介绍如何获取我们在“入门”部分中开发的简单应用程序，并在云中运行。

### 58.1 Cloud Foundry
Cloud Foundry提供默认的buildpacks，如果没有指定其他buildpack，则可以使用默认buildpacks。 Cloud Foundry Java buildpack为Spring应用程序提供了极好的支持，包括Spring Boot。 您可以部署独立的可执行jar应用程序，以及传统的.war包应用程序。

一旦构建了应用程序（使用例如mvn clean package）并安装了cf命令行工具，只需使用cf push命令部署应用程序，将其替换为编译的.jar路径。 在推送应用程序之前，请务必使用您的cf命令行客户端登录。

```
$ cf push acloudyspringtime -p target/demo-0.0.1-SNAPSHOT.jar
```

有关更多选项，请参阅cf push文档。 如果在同一目录中存在Cloud Foundry manifest.yml文件，那么将会被查阅。

> 在这里我们将acloudyspringtime作为您应用程序名，你也可以使用其他任何值作为应用程序名。

此时，cf将开始上传您的应用程序：

```
Uploading acloudyspringtime... OK
Preparing to start acloudyspringtime... OK
-----> Downloaded app package (8.9M)
-----> Java Buildpack source: system
-----> Downloading Open JDK 1.7.0_51 from .../x86_64/openjdk-1.7.0_51.tar.gz (1.8s)
       Expanding Open JDK to .java-buildpack/open_jdk (1.2s)
-----> Downloading Spring Auto Reconfiguration from  0.8.7 .../auto-reconfiguration-0.8.7.jar (0.1s)
-----> Uploading droplet (44M)
Checking status of app 'acloudyspringtime'...
  0 of 1 instances running (1 starting)
  ...
  0 of 1 instances running (1 down)
  ...
  0 of 1 instances running (1 starting)
  ...
  1 of 1 instances running (1 running)

App started
```
恭喜！ 该应用程序现在已经运行了！

然后验证部署的应用程序的状态也很容易：

```
$ cf apps
Getting applications in ...
OK

name                 requested state   instances   memory   disk   urls
...
acloudyspringtime    started           1/1         512M     1G     acloudyspringtime.cfapps.io
...
```
一旦Cloud Foundry确认您的应用程序已部署，您应该能够以给定的URI访问应用程序，在本例URI为http://acloudyspringtime.cfapps.io/。

#### 58.1.1 绑定服务
默认情况下，有关正在运行的应用程序的元数据以及服务连接信息作为环境变量（例如：$ VCAP_SERVICES）作为环境变量显示给应用程序。 这种架构决定是由于Cloud Foundry的多沟槽（任何语言和平台都可以作为buildpack支持）性质; 过程范围的环境变量是语言无关的。

环境变量并不总是为最简单的API而设计，因此Spring Boot自动提取它们并将数据平坦化为可通过Spring环境抽象访问的属性：

```
@Component
class MyBean implements EnvironmentAware {

    private String instanceId;

    @Override
    public void setEnvironment(Environment environment) {
        this.instanceId = environment.getProperty("vcap.application.instance_id");
    }

    // ...

}
```
所
有Cloud Foundry属性都以vcap为前缀。 您可以使用vcap属性来访问应用程序信息（如应用程序的公共URL）和服务信息（如数据库凭据）。 有关完整的详细信息，请参阅CloudFoundryVcapEnvironmentPostProcessor Javadoc文档。

> Spring Cloud Connectors项目更适合配置DataSource等任务。Spring Boot包括自动配置支持和Spring Boot启动器 - spring-boot-starter-cloud-connectorsstarter。

### 58.2 Heroku
Heroku是另一个受欢迎的PaaS平台。 为了自定义Heroku构建，需要提供一个Procfile配置文件，它提供部署应用程序所需的指令。 Heroku为Java应用程序分配一个端口，然后确保到外部URI的路由工作。

您必须将应用程序配置为监听正确的端口。 以下是我们的初始化REST应用程序的Procfile：

```
web: java -Dserver.port=$PORT -jar target/demo-0.0.1-SNAPSHOT.jar
```

Spring Boot通过-D参数来访问Spring Environment实例的属性。 将server.port配置属性提供给嵌入式Tomcat，Jetty或Undertow实例，然后在启动时使用它。 $ PORT环境变量由Heroku PaaS分配给我们。

Heroku默认使用Java 1.8。 只要您的Maven或Gradle构建设置为使用相同的版本（Maven用户可以使用java.version属性），这是很好的。 如果要使用JDK 1.7，请在您的pom.xml和Procfile旁边创建一个名为system.properties的新文件。 在此文件中添加以下内容：

```
java.runtime.version=1.7
```

这应该是你需要的一切。 Heroku部署最常见的工作流程是将代码推送到生产。

```
$ git push heroku master

Initializing repository, done.
Counting objects: 95, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (78/78), done.
Writing objects: 100% (95/95), 8.66 MiB | 606.00 KiB/s, done.
Total 95 (delta 31), reused 0 (delta 0)

-----> Java app detected
-----> Installing OpenJDK 1.8... done
-----> Installing Maven 3.3.1... done
-----> Installing settings.xml... done
-----> Executing: mvn -B -DskipTests=true clean install

       [INFO] Scanning for projects...
       Downloading: http://repo.spring.io/...
       Downloaded: http://repo.spring.io/... (818 B at 1.8 KB/sec)
        ....
       Downloaded: http://s3pository.heroku.com/jvm/... (152 KB at 595.3 KB/sec)
       [INFO] Installing /tmp/build_0c35a5d2-a067-4abc-a232-14b1fb7a8229/target/...
       [INFO] Installing /tmp/build_0c35a5d2-a067-4abc-a232-14b1fb7a8229/pom.xml ...
       [INFO] ------------------------------------------------------------------------
       [INFO] BUILD SUCCESS
       [INFO] ------------------------------------------------------------------------
       [INFO] Total time: 59.358s
       [INFO] Finished at: Fri Mar 07 07:28:25 UTC 2014
       [INFO] Final Memory: 20M/493M
       [INFO] ------------------------------------------------------------------------

-----> Discovering process types
       Procfile declares types -> web

-----> Compressing... done, 70.4MB
-----> Launching... done, v6
       http://agile-sierra-1405.herokuapp.com/ deployed to Heroku

To git@heroku.com:agile-sierra-1405.git
 * [new branch]      master -> master
```

您的应用程序现在应该在Heroku上运行了。
### 58.3 OpenShift
OpenShift是RedHat公共（和企业）PaaS解决方案。 像Heroku一样，它通过运行由git提交触发的脚本来起作用，因此，只要Java运行时可用，您就可以按照任何您喜欢的方式来编写Spring Boot应用程序的启动（这是您可以要求的标准功能OpenShift）。 为了做到这一点，你可以使用自己的盒子和钩子在你的仓库.openshift / action_hooks：

基本模式是：

1. 确保Java和您的构建工具远程安装，例如 使用pre_build钩子（Java和Maven默认情况下安装，Gradle不是）
1. 使用构建钩来构建您的jar（使用Maven或Gradle），例如：

```
#!/bin/bash
cd $OPENSHIFT_REPO_DIR
mvn package -s .openshift/settings.xml -DskipTests=true
```

 3.添加一个调用java -jar的启动钩子...
 
 ```
 #
!/bin/bash
cd $OPENSHIFT_REPO_DIR
nohup java -jar target/*.jar --server.port=${OPENSHIFT_DIY_PORT} --server.address=${OPENSHIFT_DIY_IP} &
 ```
 4.使用停止钩（因为开始应该是干净地返回），例如:
 
 ```
 #!/bin/bash
source $OPENSHIFT_CARTRIDGE_SDK_BASH
PID=$(ps -ef | grep java.*\.jar | grep -v grep | awk '{ print $2 }')
if [ -z "$PID" ]
then
    client_result "Application is already stopped"
else
    kill $PID
fi
 ```
 
 5.从您的application.properties中的平台提供的环境变量嵌入服务绑定，例如:
 
 ```
 spring.datasource.url: jdbc:mysql://${OPENSHIFT_MYSQL_DB_HOST}:${OPENSHIFT_MYSQL_DB_PORT}/${OPENSHIFT_APP_NAME}
spring.datasource.username: ${OPENSHIFT_MYSQL_DB_USERNAME}
spring.datasource.password: ${OPENSHIFT_MYSQL_DB_PASSWORD}
 ```
 在Openshift的网站上有一篇[running Gradle in Openshift](https://www.openshift.com/blogs/run-gradle-builds-on-openshift)博客，如果想使用gradle构建运行的应用可以参考它。
###  58.4 Amazon Web Services (AWS)
Amazon Web Services提供多种方式来安装基于Spring Boot的应用程序，无论是传统的Web应用程序（war）还是具有嵌入式Web服务器的 可执行jar文件，包括如下几种运行方式：

* AWS Elastic Beanstalk
* AWS Code Deploy
* AWS OPS Works
* AWS Cloud Formation
* AWS Container Registry
每个都有不同的功能和定价模式，这里我们将仅描述最简单的方式：AWS Elastic Beanstalk。
### 58.4.1 AWS Elastic Beanstalk
正如Elastic Beanstalk Java指南中所述，部署Java应用程序有两个主要方式： 您可以使用“Tomcat平台”或“Java SE平台”。

#### 使用 Tomcat平台
此选项适用于生成war文件的Spring Boot项目。 没有任何特殊配置，只需按照官方指南即可。

#### 使用Java SE平台
此种方式适用于生成jar文件并运行嵌入式Web容器的Spring Boot项目。 Elastic Beanstalk环境在端口80上运行一个nginx实例来代理在端口5000上运行的实际应用程序。要配置它，请将以下内容添加到您的application.properties中：

```
server.port=5000
```
#### 最佳实践
#####上传二进制jar而不是源文件

默认情况下，Elastic Beanstalk上传源码并在AWS中编译它们。 要上传二进制文件，请将以下内容添加到.elasticbeanstalk / config.yml文件中：

```
deploy:
    artifact: target/demo-0.0.1-SNAPSHOT.jar
    
```

通过设置环境类型降低系统开销

默认情况下，Elastic Beanstalk环境是负载均衡的。 负载平衡器有系统资源消耗，为避免这种情况，将环境类型设置为“单例模式”，如Amazon文档中所述。 使用CLI也可以使用以下命令创建单一实例环境：

```
eb create -s
```

#### 58.4.2 Summary
这是访问AWS的最简单的方法之一，但是还有更多的东西要覆盖，例如：如何将Elastic Beanstalk整合到任何CI / CD工具中，使用Elastic Beanstalk maven插件而不是CLI等。 更详细地介绍这些主题的博客（https://exampledriven.wordpress.com/2017/01/09/spring-boot-aws-elastic-beanstalk-example/）。

### 58.5 Boxfuse和Amazon Web Services
[Boxfuse](https://boxfuse.com/)的工作机制是将你的Spring Boot可执行jar或war转换进一个最小化的VM镜像，该镜像不需改变就能部署到VirtualBox或AWS。Boxfuse深度集成Spring Boot并使用你的Spring Boot配置文件自动配置端口和健康检查URLs，它将该信息用于产生的镜像及它提供的所有资源（实例，安全分组，可伸缩的负载均衡等）。

一旦创建一个[Boxfuse account](https://console.boxfuse.com/)，并将它连接到你的AWS账号，安装最新版Boxfuse客户端，你就能按照以下操作将Spring Boot应用部署到AWS（首先要确保应用被Maven或Gradle构建过，比如`mvn clean package`）：

```
$ boxfuse run myapp-1.0.jar -env=prod
```

有
关更多选项，请参阅boxfuse运行文档。 如果当前目录中存在一个boxfuse.com/docs/commandline/#configuration [boxfuse.conf]文件，boxfuse将使用这个文件。

> 如果你的可执行jar或war包含[`application-boxfuse.properties`](https://boxfuse.com/docs/payloads/springboot.html#configuration)文件，Boxfuse默认在启动时会激活一个名为`boxfuse`的Spring profile，然后在该profile包含的属性基础上构建自己的配置。

此刻`boxfuse`将为你的应用创建一个镜像并上传到AWS，然后配置并启动需要的资源：

```
Fusing Image for myapp-1.0.jar ...
Image fused in 00:06.838s (53937 K) -> axelfontaine/myapp:1.0
Creating axelfontaine/myapp ...
Pushing axelfontaine/myapp:1.0 ...
Verifying axelfontaine/myapp:1.0 ...
Creating Elastic IP ...
Mapping myapp-axelfontaine.boxfuse.io to 52.28.233.167 ...
Waiting for AWS to create an AMI for axelfontaine/myapp:1.0 in eu-central-1 (this may take up to 50 seconds) ...
AMI created in 00:23.557s -> ami-d23f38cf
Creating security group boxfuse-sg_axelfontaine/myapp:1.0 ...
Launching t2.micro instance of axelfontaine/myapp:1.0 (ami-d23f38cf) in eu-central-1 ...
Instance launched in 00:30.306s -> i-92ef9f53
Waiting for AWS to boot Instance i-92ef9f53 and Payload to start at http://52.28.235.61/ ...
Payload started in 00:29.266s -> http://52.28.235.61/
Remapping Elastic IP 52.28.233.167 to i-92ef9f53 ...
Waiting 15s for AWS to complete Elastic IP Zero Downtime transition ...
Deployment completed successfully. axelfontaine/myapp:1.0 is up and running at http://myapp-axelfontaine.boxfuse.io/
```

你的应用现在应该已经在AWS上启动并运行了。

这里有篇[在EC2部署Spring Boot应用](https://boxfuse.com/blog/spring-boot-ec2.html)的博客，Boxfuse官网也有[Boxfuse集成Spring Boot文档](https://boxfuse.com/docs/payloads/springboot.html)，你可以拿来作为参考。
### 58.6 Google App Engine
Google App Engine与Servlet 2.5 API绑定在一起，因此您无法在某些情况下部署Spring应用程序。 请参阅本指南的Servlet 2.5部分。
##59 安装Spring Boot应用
除了使用java -jar运行Spring Boot应用程序外，还可以为Unix系统完成可执行的应用程序。 这使得在常见的生产环境中安装和管理Spring Boot应用程序非常容易。

要使用Maven创建“完全可执行”的jar，请使用以下插件配置：

```
<plugin>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-maven-plugin</artifactId>
    <configuration>
        <executable>true</executable>
    </configuration>
</plugin>
```
使用Gradle，等效配置将是：

```
springBoot {
    executable = true
}
```
然后，您可以通过键入./my-application.jar（其中my-application是您的工件的名称）来运行应用程序。

> 完全可执行的jar通过在文件的前面嵌入一个额外的脚本来工作。 并不是所有的工具目前都接受这种格式，所以你可能并不总是能够使用这种技术。 
> 默认脚本支持大多数Linux发行版，并在CentOS和Ubuntu上进行测试。 其他平台，如OS X和FreeBSD，将需要使用自定义的嵌入式LunchScript。 
> 当运行完全可执行的jar时，它将使用jar的目录作为工作目录。

### 59.1 Unix/Linux服务
你可以使用`init.d`或`systemd`启动Spring Boot应用，就像其他Unix/Linux服务那样。
#### 59.1.1 安装为init.d服务(System V)
如果您配置了Spring Boot的Maven或Gradle插件来生成完全可执行的jar，并且您没有使用自定义的embeddedLaunchScript，那么您的应用程序可以用作init.d服务。 简单地将jar链接到init.d以支持标准的start，stop，restart和status命令。

该脚本支持以下功能：

* 以拥有该jar文件的用户启动服务
* 使用/var/run/<appname>/<appname>.pid跟踪应用程序的PID
* 将控制台日志写入/var/log/<appname>.log


假设你在`/var/myapp`目录安装了一个Spring Boot应用，只需要建立符号连接就能将Spring Boot应用安装成`init.d`服务：
```
$ sudo ln -s /var/myapp/myapp.jar /etc/init.d/myapp
```
一旦安装成功，你就可以像平常那样启动和停止服务，例如，在一个基于Debian的系统：

```
$ service myapp start
```
> 如果应用启动失败，检查下`/var/log/<appname>.log`中的错误日志。

你也可以标识应用使用标准的操作系统工具自启动，例如，在Debian上：

```
$ update-rc.d myapp defaults <priority>
```
##### 保护init.d服务
> 以下是关于如何保护作为init.d服务运行的Spring引导应用程序的一组指导。 它并不是为了强化应用程序和运行环境而应该做的所有事情的详尽列表。

当使用`root`用户启动`init.d`服务时，默认的执行脚本将以拥有该jar文件的用户来运行应用。你最好不要使用`root`启动Spring Boot应用，也就是你的应用jar文件拥有者不能是`root`，而是创建一个特定用户运行应用，并使用`chown`指定该用户拥有jar文件，示例：

```
$ chown bootapp:bootapp your-app.jar
```
本示例中，默认执行脚本将使用`bootapp`用户运行应用。

你也要采取措施防止修改应用jar文件，首先配置jar文件权限只能被拥有者读取和执行，不能写入：

```
$ chmod 500 your-app.jar
```
然后，你也应该采取措施限制应用或账号运行时的冲突造成的损坏。如果攻击者获取访问权，他们可能会让jar文件可写并改变它的内容，使用`chattr`让它变为不可变是唯一的保护措施：

```
$ sudo chattr +i your-app.jar
```

这会防止任何用户修改jar文件，包括root。

如果root用户用来控制应用服务，并且你使用[.conf文件](http://docs.spring.io/spring-boot/docs/1.4.1.RELEASE/reference/htmlsingle/#deployment-script-customization-conf-file)自定义它的启动，该`.conf`文件将被root用户读取和评估，因此它也需要保护。使用`chmod`改变文件权限只能被拥有者读取，然后使用`chown`改变文件拥有者为root：

```
$ chmod 400 your-app.conf
$ sudo chown root:root your-app.conf
```

#### 59.1.2 安装为Systemd服务
Systemd是System V init系统的继任者，很多现代Linux分发版本都在使用，尽管你可以继续使用`init.d`脚本，但使用`systemd` ‘service’脚本启动Spring Boot应用是有可能的。

假设你在`/var/myapp`目录下安装一个Spring Boot应用，为了将它安装为一个`systemd`服务，你需要按照以下示例创建一个脚本，比如命名为`myapp.service`，然后将它放到`/etc/systemd/system`目录下：

```
[Unit]
Description=myapp
After=syslog.target

[Service]
User=myapp
ExecStart=/var/myapp/myapp.jar
SuccessExitStatus=143

[Install]
WantedBy=multi-user.target
```

> 记得根据你的应用改变`Description`，`User`和`ExecStart`字段。 
> 请注意，ExecStart字段不声明脚本操作命令，这意味着默认情况下使用run命令。

注意跟作为`init.d`服务运行不同，使用`systemd`这种方式运行应用，PID文件和控制台日志文件表现是不同的，必须在‘service’脚本配置正确的字段，具体参考[service unit configuration man page](http://www.freedesktop.org/software/systemd/man/systemd.service.html)。

```
$ systemctl enable myapp.service
```

有关详细信息，请参阅man systemctl。

#### 59.1.3 自定义启动脚本
Maven或Gradle插件生成的默认内嵌启动脚本可以通过很多方法自定义，对于大多数开发者，使用默认脚本和一些自定义脚本通常就足够了。如果发现不能自定义需要的东西，你可以使用`embeddedLaunchScript`选项生成自己的文件。

###### 在脚本生成时自定义

自定义写入jar文件的启动脚本元素是有意义的，例如，为`init.d`脚本提供`description`，既然知道这会展示到前端，你可能会在生成jar时提供它。

为了自定义写入的元素，你需要为Spring Boot Maven或Gradle插件指定`embeddedLaunchScriptProperties`选项。

以下是默认脚本支持的可代替属性：

名称|描述
----|---
mode|脚本模式，默认为`auto`

在脚本运行时自定义
对于需要在jar文件生成后自定义的项目，你可以使用环境变量或配置文件。

默认脚本支持以下环境变量：




#### 59.2 Microsoft Windows服务
在Window上，你可以使用[winsw](https://github.com/kohsuke/winsw)启动Spring Boot应用。这里有个单独维护的[示例](https://github.com/snicoll-scratches/spring-boot-daemon)为你演示了怎么一步步为Spring Boot应用创建Windows服务。









## 60 接下来阅读什么
打开[Cloud Foundry](http://www.cloudfoundry.com/)，[Heroku](https://www.heroku.com/)，[OpenShift](https://www.openshift.com/)和[Boxfuse](https://boxfuse.com/)网站获取更多Paas能提供的特性信息。这里只提到4个比较流行的Java PaaS提供商，由于Spring Boot遵从基于云的部署原则，所以你也可以自由考虑其他提供商。

下章节将继续讲解[Spring Boot CLI](http://docs.spring.io/spring-boot/docs/1.5.3.RELEASE/reference/htmlsingle/#cli)，你也可以直接跳到[build tool plugins](http://docs.spring.io/spring-boot/docs/1.5.3.RELEASE/reference/htmlsingle/#build-tool-plugins)。

# 第七部分 spring boot命令行客户端工具（CLI）
# 第八部分 spring boot 构建工具插件
# 第九部分 How-to参考手册
# 第十部分 附录
# 关于本翻译
###翻译者：gangzi828

###联系方式：QQ-1139872666

译者简介：本人是一个对新技术的热爱者，平时喜欢翻译一些国外技术资料，是开源技术的热衷者。现就职于杭州一家网络与信息安全公司，负责公司项目组的java开发和android开发。

声明：这个本人业余时间的翻译作品，任何组织和个人不得以商业利益进行非法传播。如有翻译不正确之处，请多多指正，喷子请远离。若您对本翻译计划感兴趣，欢迎您的加入，共同为开源界做贡献。
























