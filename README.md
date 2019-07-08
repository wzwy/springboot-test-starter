# springboot-test-starter

package com.wz.springboot;

import lombok.extern.slf4j.Slf4j;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;

@SpringBootApplication//springboot主启动类
@Slf4j
@RestController
public class SpringbootApplication {

	public static void main(String[] args) {
		SpringApplication.run(SpringbootApplication.class, args);
	}

	@Autowired
	private Hello hello;

	//使用
	@GetMapping("/hello")
	public String hello(){
		log.info("hello："+hello);
		return hello.sayHello();
	}

}

hello:
  enabled: true
  msg: wz
debug: true

<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
		 xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">

	<!--springboot最终打的jar包-->
	<modelVersion>4.0.0</modelVersion>

	<groupId>com.wz</groupId>
	<artifactId>springboot-test-starter</artifactId>
	<version>0.0.1-SNAPSHOT</version>
	<packaging>jar</packaging>

	<name>springboot-test-starter</name>
	<description>Spring Boot</description>

	<!--springboot父jar包-->
	<parent>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-parent</artifactId>
		<version>2.0.5.RELEASE</version>
		<relativePath/> <!-- lookup parent from repository -->
	</parent>

	<properties>
		<!--jar版本-->
		<project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
		<project.reporting.outputEncoding>UTF-8</project.reporting.outputEncoding>
		<java.version>1.8</java.version>
	</properties>

	<dependencies>
		<!--springmvc-->
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-web</artifactId>
		</dependency>
		<!--lombok-->
		<dependency>
			<groupId>org.projectlombok</groupId>
			<artifactId>lombok</artifactId>
			<version>1.18.2</version>
			<optional>true</optional>
		</dependency>
		<dependency>
			<groupId>com.wz</groupId>
			<artifactId>springboot-custom-starter</artifactId>
			<version>0.0.1-SNAPSHOT</version>
		</dependency>

	</dependencies>

</project>


