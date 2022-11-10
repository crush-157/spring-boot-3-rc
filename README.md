# Testing with Spring Boot 3 Release Candidate and Native image.


## Pre - Requisites

Make sure that you are using GraalVM 22.3.0 or better and equivalent version of native-image.

## Spring Initializr
Use [Spring Initializr](https://start.spring.io/) to get started.

Links to configurations used in this example:

[Maven](https://start.spring.io/#!type=maven-project&language=java&platformVersion=3.0.0-RC1&packaging=jar&jvmVersion=17&groupId=com.example&artifactId=vanilla&name=vanilla&description=Demo%20project%20for%20Spring%20Boot&packageName=com.example.vanilla&dependencies=native,web)

[Gradle](https://start.spring.io/#!type=gradle-project&language=java&platformVersion=3.0.0-RC1&packaging=jar&jvmVersion=17&groupId=com.example&artifactId=vanilla&name=vanilla&description=Demo%20project%20for%20Spring%20Boot&packageName=com.example.vanilla&dependencies=native,web)

## What's in the folders?

### [initializr](./initializr/)

A folder for each of the build engines
- [gradle](./initializr/gradle/)
- [maven](./initializr/maven/)

Each folder contains:
- generated skeleton application (vanilla.zip)
- screenshot of the configuration used

### [code](./code/)
Contains a simple controller for the sample app [Hello.java](./code/Hello.java) (404 is not a great respoonse).

`Hello.java` has been added to the src tree under each of the [builds](./builds/).

### [builds](./builds/)

Contains unzipped builds of the `vanilla` application for `maven` and `gradle` in respectively named folders:
- [gradle](./builds/gradle/vanilla/)
- [maven](./builds/maven/vanilla/)

Each of these contains the 'vanilla' app and the files for the appropriate build engine.

### Running the builds

#### Gradle:
- from the command line, `cd` to the [vanilla application folder](./builds/gradle/vanilla/)
- to build and run the application in one go `./gradlew bootRun`
- to build the jar `./gradlew assemble`
- to run the jar `java -jar build/libs/vanilla-0.0.1-SNAPSHOT.jar`
- to compile to a native image `./gradlew nativeCompile`
- to run the executable `./build/native/nativeCompile/vanilla`

#### Maven

Make sure that `$JAVA_HOME` has been to point to the `GraalVM` installation

- from the command line, `cd` to the [vanilla application folder](./builds/maven/vanilla/)
- to build and run the application in one go `./mvnw spring-boot:run`
- to build the jar `./mvnw package`
- to run the jar `java -jar target/vanilla-0.0.1-SNAPSHOT.jar`
- to compile to a native image `./mvnw -Pnative native:compile`
- to run the executable `./target/vanilla`
