---
layout: post
title: "《Head First Java 2nd Edition》Chapter 17"
date: 2021-04-20
excerpt: "Release Your Code"
tags: [reading notes,Head First Java,Java]
comments: true




---

# Deploying your application

### A Java program is a bunch of classes. That’s the output of your development. The real question is what to do with those classes when you’re done.

![image-20210420111905900](C:\Users\雷霆世纪\AppData\Roaming\Typora\typora-user-images\image-20210420111905900.png)

1. **Local**

   The entire application runs on the end-user’s computer,as a stand-alone,probably GUI,program,deployed as an executable JAR

2. **Combination of local and remote**

   The application is distributed with a client portion running on the user’s local system,connected to a server where other parts of the application are running

3. **Remote**

   The entire Java application runs on a server system,with the client accessing the system through some ono-Java means,probably a web brower

# Separate souece code and class file

***The key is a combination of directory structure organization and the -d compiler option.***

### Compiling with the -d (directory) flag

![image-20210420113911963](D:\Nicholas\Project\cp3ugar.github.io\assets\img\image-20210420113911963.png)

![image-20210420114011921](D:\Nicholas\Project\cp3ugar.github.io\assets\img\image-20210420114011921.png)



