Testing with Spring Boot 3 Release Candidate and Native image.

Make sure that you are using GraalVM 22.3.0 or better and equivalent version of native-image.

The initializr folder contains screenshots of parameters used with the Spring initializr and the resulting zip files.

Links to configurations:
Maven: https://start.spring.io/#!type=maven-project&language=java&platformVersion=3.0.0-RC1&packaging=jar&jvmVersion=17&groupId=com.example&artifactId=vanilla&name=vanilla&description=Demo%20project%20for%20Spring%20Boot&packageName=com.example.vanilla&dependencies=native,web
Gradle: https://start.spring.io/#!type=gradle-project&language=java&platformVersion=3.0.0-RC1&packaging=jar&jvmVersion=17&groupId=com.example&artifactId=vanilla&name=vanilla&description=Demo%20project%20for%20Spring%20Boot&packageName=com.example.vanilla&dependencies=native,web

The code folder contains Hello.java (Controller for the sample app).  This had been added to the src tree under each of the builds.

The builds folder contains folders for maven and gradle.  Each of these contains the 'vanilla' app and the files for the appropriate build engine.

For Maven
- to build and run the application in one go `./mvnw spring-boot:run`
- to build the jar `./mvnw package`
- to run the jar `java -jar target/vanilla-0.0.1-SNAPSHOT.jar`
- to compile to a native image `./mvnw -Pnative native:compile`
- to run the executable `./target/vanilla`

For Gradle:
- to build and run the application in one go `./gradlew bootRun`
- to build the jar `./gradlew assemble`
- to run the jar `java -jar build/libs/vanilla-0.0.1-SNAPSHOT.jar`
- to compile to a native image `./gradlew nativeCompile`
- to run the executable `./build/native/nativeCompile/vanilla`