# Go Native with Spring Boot 3 and GraalVM

## Introduction

There has been a lot of interest in the past few years about "native Java".  You've probably read articles or seen conference talks on the subject.

### TL;DR - "native Java"
Traditionally Java programs are compiled to bytecode that is then interpreted by a JVM.

Native Java is the idea of using ahead-of-time (AOT) compilation to produce a native executable or "native image" for a Java application.

A native image can run standalone without relying on a JVM.

This approach potentially offers advantages in terms of:
- faster application startup
- lower latency
- reduced infrastructure footprint and cost

[GraalVM](https://www.graalvm.org) is an open source JDK that can compile Java applications to native images, as well as bytecode in the traditional way.

### Native Java and Spring
Spring is the most popular Java application framework used today.

Over the last three years, the Spring and GraalVM teams have been working to make it easier for developers to deliver their Spring applications as native images.

_Experimental_ support for native image was achieved via the [Spring Native](https://docs.spring.io/spring-native/docs/current/reference/htmlsingle/) project.

With Spring Boot 3 and Spring 6 (due to be released November 24, 2022), support for native image will be available as a core feature.

Since the release candidate for Spring Boot 3 is [now available](https://spring.io/blog/2022/10/20/spring-boot-3-0-0-rc1-available-now), this seems a good time to try out the native image support.

## Trying it out
So lets have a go at using the Spring Boot 3 release candidate and GraalVM to create a simple web application, compiled to a native executable.

### Pre - requisites