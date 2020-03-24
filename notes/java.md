---
tags: [java]
title: java
created: '2019-07-30T06:19:49.143Z'
modified: '2020-03-18T15:53:23.781Z'
---

# java

> `jvm - java virtual machine`

## usage
```sh
java                                # List all standard options.
#    -version                           current version
#    -cp                                class path
#    -Dblog=RebelLabs                   Sets a ‘blog’ system property to ‘RebelLabs’. `System.getProperty("blog");`
#    -javaagent:/path/to/agent.jar      Loads the java agent in agent.jar.
#    -agentpath:pathname                Loads the native agent library specified by the absolute path name.
#    -verbose:[class/gc/jni]            Displays information about each loaded class/gc event/JNI activity.
#    -X                                 List all non-standard options.
#    -Xint                              Runs the application in interpreted-only mode.
#    -Xbootclasspath:path               Path and archive list of boot class files.
#    -Xloggc:filename                   Log verbose GC events to filename.
#    -Xms1g                             Set the initial size (in bytes) of the heap.
#    -Xmx8g                             Specifies the max size (in bytes) of the heap.
#    -Xnoclassgc                        Disables class garbage collection.
#    -Xprof                             Profiles the running program.
# advanced opts: behavior
#    -XX:+UseConcMarkSweepGC              Enables CMS garbage collection.
#    -XX:+UseParallelGC                   Enables parallel garbage collection.
#    -XX:+UseSerialGC                     Enables serial garbage collection.
#    -XX:+UseG1GC                         Enables G1GC garbage collection.
#    -XX:+FlightRecorder                  requires   UnlockCommercialFeatures
#    -XX:+UnlockCommercialFeatures)       Enables the use of the Java Flight Recorder.
# advanced opts: debugging
#    -XX:ErrorFile=file.log               Save the error data to file.log.
#    -XX:+HeapDumpOnOutOfMemory           Enables heap dump when OutOfMemoryError is thrown.
#    -XX:+PrintGC                         Enables printing messages during garbage collection.
#    -XX:+TraceClassLoading               Enables Trace loading of classes.
#    -XX:+PrintClassHistogram             Enables printing of a class instance histogram after a Control+C event (SIGTERM).
# advanced opts: performance
#    -XX:MaxPermSize=128m (Java 7 or earlier)   Sets the max perm space size (in bytes).
#    -XX:ThreadStackSize=256k                   Sets Thread Stack Size (in bytes). (Same as -Xss256k)
#    -XX:+UseStringCache                        Enables caching of commonly allocated strings.
#    -XX:G1HeapRegionSize=4m                    Sets the sub-division size of G1 heap (in bytes).
#    -XX:MaxGCPauseMillis=n                     Sets a target for the maximum GC pause time.
#    -XX:MaxNewSize=256m                        Max size of new generation (in bytes).
#    -XX:+AggressiveOpts                        Enables the use of aggressive performance optimization features.
#    -XX:OnError="cmd args"                     Run user-defined commands on fatal error.
```

## see also
- [[javac]]
- [[sdk]]
- [[python]]
- [[ulimit]]



