# Hello Java Maven Build with Jenkins

This project demonstrates a **simple Java application build using Maven** in Jenkins, as part of learning CI/CD.

---

## **Project Structure**

hello-java-maven/
├── pom.xml
└── src
└── main
└── java
└── HelloWorld.java

## Java
package com.example;

public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, Jenkins + Maven!");
    }
}
------
## pom.xml
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0
                             http://maven.apache.org/xsd/maven-4.0.0.xsd">

    <modelVersion>4.0.0</modelVersion>

    <groupId>com.example</groupId>
    <artifactId>hello-java-maven</artifactId>
    <version>1.0-SNAPSHOT</version>

    <properties>
        <maven.compiler.source>1.8</maven.compiler.source>
        <maven.compiler.target>1.8</maven.compiler.target>
    </properties>

    <build>
        <plugins>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <version>3.8.1</version>
            </plugin>

            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-jar-plugin</artifactId>
                <version>3.2.0</version>
                <configuration>
                    <archive>
                        <manifest>
                            <mainClass>com.example.HelloWorld</mainClass>
                        </manifest>
                    </archive>
                </configuration>
            </plugin>
        </plugins>
    </build>

</project>
-----
## Jenkins Setup

Install Jenkins locally or via Docker:

docker run -p 8080:8080 -p 50000:50000 jenkins/jenkins:lts


Go to Manage Jenkins → Global Tool Configuration and add Maven (e.g., Maven 3.8.6).

Create a Freestyle Job in Jenkins:

Build → Invoke top-level Maven targets

Goal: clean package

Select Maven installation

Click Build Now and check Console Output.
----
## Build Output

The build was successful as shown in the console output screenshot:

<img width="1327" height="231" alt="jenkins screenshot" src="https://github.com/user-attachments/assets/00dcd326-99a0-400c-9842-c26b554f7d2f" />

[INFO] BUILD SUCCESS
Finished: SUCCESS
----
## Deliverables

Java source code (HelloWorld.java)

Maven pom.xml

Jenkins Freestyle job configured with Maven

Screenshot of successful build console output

Author : Divyanshu Sharma
----



