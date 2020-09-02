---
tags: [java]
title: java
created: '2019-07-30T06:19:49.143Z'
modified: '2020-09-02T08:49:06.022Z'
---

# java

> `java virtual machine` - java application launcher

## usage
```sh
java                                # lists all standard options

java \
  -Dlogging.level.root=DEBUG \
  -Dlogging.level.org.springframework.web=DEBUG \
  -Dlogging.level.org.hibernate=ERROR \
  -Djavax.net.ssl.trustStorePassword=PASS \
  -jar -Xmx6144m file.jar

mvn spring-boot:run \
  -Dspring-boot.run.arguments=--spring.main.banner-mode=off,--customArgument=custom

# flags
#    -version                           current version
#    -cp                                class path
#    -Dblog=RebelLabs                   Sets a ‘blog’ system property to ‘RebelLabs’. `System.getProperty("blog");`
#    -javaagent:/path/to/agent.jar      Loads the java agent in agent.jar
#    -agentpath:pathname                Loads the native agent library specified by the absolute path name
#    -verbose:[class/gc/jni]            Displays information about each loaded class/gc event/JNI activity
#    -X                                 List all non-standard options
#    -Xint                              Runs the application in interpreted-only mode
#    -Xbootclasspath:path               Path and archive list of boot class files
#    -Xloggc:filename                   Log verbose GC events to filename
#    -Xms1g                             initial size of heap
#    -Xmx8g                             max size of heap
#    -Xnoclassgc                        disables class gc
#    -Xprof                             profiles running program
# advanced opts - behavior
#    -XX:+UseConcMarkSweepGC              enables CMS gc
#    -XX:+UseParallelGC                   enables parallel gc
#    -XX:+UseSerialGC                     enables serial gc
#    -XX:+UseG1GC                         enables G1GC gc
#    -XX:+FlightRecorder                  requires   UnlockCommercialFeatures
#    -XX:+UnlockCommercialFeatures        enables the use of the Java Flight Recorder
# advanced opts - debugging
#    -XX:ErrorFile=file.log               Save the error data to file.log
#    -XX:+HeapDumpOnOutOfMemory           enables heap dump when OutOfMemoryError is thrown
#    -XX:+PrintGC                         enables printing messages during gc
#    -XX:+TraceClassLoading               enables Trace loading of classes
#    -XX:+PrintClassHistogram             enables printing of a class instance histogram after a Control+C event (SIGTERM)
# advanced opts - performance
#    -XX:MaxPermSize=128m (Java 7 or earlier)   Sets the max perm space size (bytes)
#    -XX:ThreadStackSize=256k                   Sets Thread Stack Size (bytes) (same as -Xss256k)
#    -XX:+UseStringCache                        enables caching of commonly allocated strings
#    -XX:G1HeapRegionSize=4m                    Sets the sub-division size of G1 heap (bytes)
#    -XX:MaxGCPauseMillis=n                     Sets a target for the maximum GC pause time
#    -XX:MaxNewSize=256m                        Max size of new generation (bytes)
#    -XX:+AggressiveOpts                        enables the use of aggressive performance optimization features
#    -XX:OnError="cmd args"                     Run user-defined commands on fatal error
```

## see also
- [[jps]]
- [[jar]]
- [[javac]]
- [[sdk]]
- [[kafka]]
- [[python]]
- [[ulimit]]



