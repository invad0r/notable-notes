---
tags: [buildsystem, java]
title: mvn
created: '2019-07-30T06:19:49.084Z'
modified: '2023-04-11T11:54:25.409Z'
---

# mvn

> `maven`, yiddish word meaning `accumulator of knowledge`, began as an attempt to simplify the build processes in the Jakarta Turbine project

## install

```sh
sdk install maven
```

## env

```sh
MAVEN_CLI_OPTS        # used to pass options to the Maven CLI
MAVEN_OPTS            # used to configure the JVM that runs Maven
MAVEN_ARGS            # contains args passed to maven before cli args, e.g. options and goals could be defined with the value -B -V checkstyle:checkstyle

MVNW_REPOURL          # e.g. when using a mirror
MVNW_USERNAME
MVNW_PASSWORD
```

## option

```sh
-am,  --also-make                       # If project list is specified, also build projects required by the list
-amd, --also-make-dependents            # If project list is specified, also build projects that depend on projects on the list
-B,   --batch-mode                      # Run in non-interactive (batch) mode (disables output color)
-b,   --builder ARG                     # The id of the build strategy to use
-C,   --strict-checksums                # Fail the build if checksums don't match
-c,   --lax-checksums                   # Warn if checksums don't match
      --color ARG                       # Defines the color mode of the output. Supported are 'auto', 'always', 'never'.
-cpu, --check-plugin-updates            # Ineffective, only kept for backward compatibility
-D,   --define ARG                      # Define a user property
-e,   --errors                          # Produce execution error messages
-emp, --encrypt-master-password ARG     # Encrypt master security password
-ep,  --encrypt-password ARG            # Encrypt server password
-f,   --file ARG                        # Force the use of an alternate POM file (or directory with pom.xml)
-fae, --fail-at-end                     # Only fail the build afterwards; allow all non-impacted builds to continue
-ff,  --fail-fast                       # Stop at first failure in reactorized builds
-fn,  --fail-never                      # NEVER fail the build, regardless of project result
-gs,  --global-settings ARG             # Alternate path for the global settings file
-gt,  --global-toolchains ARG           # Alternate path for the global toolchains file
-h,   --help                            # Display help information
-l,   --log-file ARG                    # Log file where all build output will go (disables output color)
-llr, --legacy-local-repository         # Use Maven 2 Legacy Local Repository behaviour, ie no use of _remote.repositories. Can also be activated by using -Dmaven.legacyLocalRepo=true
-N,   --non-recursive                   # Do not recurse into sub-projects
-npr, --no-plugin-registry              # Ineffective, only kept for backward compatibility
-npu, --no-plugin-updates               # Ineffective, only kept for backward compatibility
-nsu, --no-snapshot-updates             # Suppress SNAPSHOT updates
-ntp, --no-transfer-progress            # Do not display transfer progress when downloading or uploading
-o,   --offline                         # Work offline
-P,   --activate-profiles ARG           # Comma-delimited list of profiles to activate
-pl,  --projects ARG                    # Comma-delimited list of specified reactor projects to build instead of all projects. A project can be specified by [groupId]:artifactId or by its relative path
-q,   --quiet                           # Quiet output - only show errors
-rf,  --resume-from ARG                 # Resume reactor from specified project
-s,   --settings ARG                    # Alternate path for the user settings file
-t,   --toolchains ARG                  # Alternate path for the user toolchains file
-T,   --threads ARG                     # Thread count, for instance 4 (int) or 2C/2.5C (int/float) where C is core multiplied
-U,   --update-snapshots                # Forces a check for missing releases and updated snapshots on remote repositories
-up,  --update-plugins                  # Ineffective, only kept for backward compatibility
-v,   --version                         # Display version information
-V,   --show-version                    # Display version information WITHOUT stopping build
-X,   --debug                           # Produce execution debug output
```

## usage

```sh
mvn help:active-profiles 	    # displays a list of the profiles which are currently active for this build.
mvn help:all-profiles 	      # displays a list of available profiles under the current project.
mvn -B help:all-profiles      # list profiles
mvn help:describe 	          # displays a list of the attributes for a Maven Plugin and/or goals (aka Mojo - Maven plain Old Java Object).
mvn help:describe -Dcmd=compile
mvn help:effective-pom 	      # displays the effective POM as an XML for this build, with the active profiles factored in, or a specified artifact. If verbose, a comment is added to each XML element describing the origin of the line.
mvn help:effective-pom -Doutput=effective-pom.xml
mvn help:effective-settings 	# displays the calculated settings as XML for this project, given any profile enhancement and the inheritance of the global settings into the user-level settings.
mvn help:evaluate 	          # evaluates Maven expressions given by the user in an interactive mode.
mvn help:help 	              # display help information on maven-help-plugin.
mvn help:help -Ddetail=true -Dgoal=GOAL # to display parameter details.
mvn help:system 	            # displays a list of the platform details like system properties and environment variables.


# commands will automatically download and install the plugin if it hasn't already been installed
mvn fr.jcgay.maven.plugins:buildplan-maven-plugin:list            # list  goals by the order they will execute
mvn fr.jcgay.maven.plugins:buildplan-maven-plugin:list-phase      # group goals by phase
mvn fr.jcgay.maven.plugins:buildplan-maven-plugin:list-plugin     # group goals by plugin
# default: goals search for tasks that run on `mvn deploy`, phases such as `clean` not included
mvn fr.jcgay.maven.plugins:buildplan-maven-plugin:list -Dbuildplan.tasks=clean,install,deploy

mvn clean install

mvn clean deploy        # builds artefact and deploys to repository

mvn generate-sources

mvn clean install -DskipTests

mvn docker:push

mvn dependency:list > dependencies.txt`


# encryption
mvn --encrypt-master-password    
#   this goes into .m2/settings-security.xml
#   <settingsSecurity>
#     <master>{Pf5qrzaQNlMHkzYc74qsZ+bhvXmZj268aPdygg4YgF0=}</master>
#   </settingsSecurity>
mvn --encrypt-password          # server pass


# multi-module
mvn versions:set -newVersion=1.2.3


mvn archetype:generate -DgroupId=com.mycompany.app -DartifactId=my-app \
  -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false

mvn package

# get version from pom.xml
mvn org.apache.maven.plugins:maven-help-plugin:2.1.1:evaluate -Dexpression=project.version \
  | grep -Ev "(^\[|Download[ed]\w+:)"
mvn --no-transfer-progress org.apache.maven.plugins:maven-help-plugin:2.1.1:evaluate -Dexpression=project.version \
  | grep -Ev "^\["
```

## see also

- [maven-in-five-minutes - apache.org](https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html)
- [Maven – Password Encryption](https://maven.apache.org/guides/mini/guide-encryption.html)
- [[sdk]]
- [[java]]
- [[gradle]]
- [[xmllint]]
- [[sbt]]
