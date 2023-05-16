---
title: native-image
created: '2023-05-11T10:44:23.796Z'
modified: '2023-05-11T11:03:08.873Z'
---

# native-image

> [[graalvm]] native image - compiles ahead-of-timejava code to native executables

```sh
sdk install java 22.3.r19-grl
sdk use     java 22.3.r19-grl
```

## env

```sh
GRAALVM_HOME=$HOME/Development/graalvm/Contents/Home/
```

## option

```sh
-cp PATH, -classpath PATH, --class-path PATH       # : separated list of directories, JAR archives, and ZIP archives to search for class files
                           --native-image-info     # show native-toolchain information and image-build settings
```

## usage

```sh
native-image --native-image-info ..
native-image -cp bcprov-jdk15on-164.jar:. -H:ReflectionConfigurationFiles=reflection-config.json test
```

## compile example

```java
public class HelloWorld {
  public static void main(String[] args) {
    System.out.println("Hello, World!");
  }
}
```

```sh
javac HelloWorld.java

java  HelloWorld

native-image HelloWorld
```

## see also

- [[sdk]], [[java]], [[mvn]]
- [[quarkus]]
- [[graalvm]]
- [graalvm.org/native-image/](https://www.graalvm.org/native-image/)
