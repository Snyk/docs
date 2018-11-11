---
title: "Getting started with Java"
---

To start using Snyk Runtime Protection for your Java applications, [download the agent](https://static.snyk.io/resources/runtime/agent/java/snyk-java-runtime-agent.zip) and unzip the archive.

* Copy `snyk-java-runtime-agent.jar` alongside your application.
* Create a `snyk-agent.properties` file at the location of the agent jar file, containing the project ID of your Snyk project like so: `projectId=0462e42b-c92f-4b48-bac8-81eb3ff7f43e`
* Add the agent as a command-line argument to the Java command used to start your application, for example: `java -javaagent:path/to/snyk-java-runtime-agent.jar -jar my-app.jar`
  - If you are using Apache Maven, add `-javaagent:path/to/snyk-java-runtime-agent.jar` to your `MAVEN_OPTS` environment variable.
  - If you are using JavaEE containers such as GlassFish, locate the JVM Options and add `-javaagent:path/to/snyk-java-runtime-agent.jar` as an option.

If you have successfully added the agent, you should see logging like the following on stderr very early after JVM startup:

```
snyk-agent initialisation: startup
snyk-agent initialisation: trying: /opt/app-1/agent/snyk-agent.properties
snyk-agent initialisation: switching logging to: /opt/app-1/agent/snyk-logs/agent-log-2001-02-03T04:05:06.log
```
