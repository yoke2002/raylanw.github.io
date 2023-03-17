# Windows 下 Java 环境配置


## 下载 JDK

> JDK 是 Java 软件开发工具包，供开发人员使用，里面包含 JRE；JRE 是 Java 软件运行环境，如果只需要运行别人开发好的 Java 软件，只需要下载 JRE；JVM 是 Java 虚拟机，是 Java 字节码运行的一个容器。

地址：[Java Downloads](https://www.oracle.com/sg/java/technologies/downloads/)

主流版本：

1. Java 8（目前常用）
2. Java 11
3. Java 17

## 安装

> 我安装的是 JDK 1.8，~~你不升我不升，来世还用 Java 8~~

和安装普通软件一样，选择好路径下一步即可。

## 环境变量配置

1. 新建 JAVA_HOME，值为 JDK 安装路径；
2. 新建 CLASSPATH，值为 `.;%JAVA_HOME%libdt.jar;%JAVA_HOME%libtools.jar`；
3. 在系统 Path 中新建环境变量添加：`%JAVA_HOME%\bin` 和 `%JAVA_HOME%\jre\bin`；

![](https://cdn.jsdelivr.net/gh/raylanw/img-source/java/image-20230309161147051.png)

4. 最后打开终端，输入 `java -version` 测试是否安装成功。

   ![](https://cdn.jsdelivr.net/gh/raylanw/img-source/java/image-20230309161247758.png)

## 第一个 Java 程序

代码如下：

```java
// 注意文件名应该与类名一致
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello World!");
    }
}
```

运行结果：

![](https://cdn.jsdelivr.net/gh/raylanw/img-source/java/image-20230309162006758.png)

编译时带 `.java` 后缀，运行时不要带 `.class` 后缀，也不要写路径，不然会提示**“错误: 找不到或无法加载主类 ..HelloWorld`”**

## 说明

1. 如果直接在终端中输入命令（如 `javac` 和 `java`），如果不是系统自带命令，则会默认从当前目录查找，如果找不到，就会查找系统的环境变量。现在我们想要在任意目录下执行 `javac` 和 `java` 命令，那么就需要在环境变量中添加 jdk 的 bin 目录路径。
2. CLASSPATH 的作用是告诉 JVM 类库的加载位置，也就是执行 `.class` 文件的时候。

## 下载 IntelliJ IDEA

Java 最好用的 IDE，在校带学生可以用一下学校邮箱认证一下，就可以使用 JetBrains 全家桶专业版，后面 JavaWeb 开发时使用专业版的 IDEA 体验会更好。
