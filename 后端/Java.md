# Java

## 安装及环境配置

### Windows

安装 JDK 的过程中会同时安装 JRE，但是 JDK 中已经包含了 JRE，所以最后提示安装 JRE 就不需要了。

环境变量配置两个地方，一个是 Java 的目录，名称为 `JAVA_HOME`，另一个是在 `PATH` 中加入 JDK 和 JRE 的执行目录。在 JDK5 之后就不需要配置 `classpath` 了。

- JAVA_HOME: C:\Program Files\Java\jdk1.8.0_221
- %JAVA_HOME%\bin
- %JAVA_HOME%\jre\bin
