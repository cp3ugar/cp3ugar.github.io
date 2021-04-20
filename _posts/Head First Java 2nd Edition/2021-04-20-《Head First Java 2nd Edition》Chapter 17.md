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

![image-20210420133957122](../../assets/img/image-20210420133957122.png)

1. **Local**

   The entire application runs on the end-user’s computer,as a stand-alone,probably GUI,program,deployed as an executable JAR

2. **Combination of local and remote**

   The application is distributed with a client portion running on the user’s local system,connected to a server where other parts of the application are running

3. **Remote**

   The entire Java application runs on a server system,with the client accessing the system through some ono-Java means,probably a web brower

# Separate souece code and class file

***The key is a combination of directory structure organization and the -d compiler option.***

### Compiling with the -d (directory) flag

![image-20210420133927883](../../assets/img/image-20210420133927883.png)

![image-20210420133940756](../../assets/img/image-20210420133940756.png)

# Put your Java in a <u>JAR</u>

A **JAR** file is a **J**ava **AR**chive.

### Making an executable JAR

1. **Make sure all of your class files are in the <u>classes</u> directory**

   ![image-20210420134444626](../../assets/img/image-20210420134444626.png)

2. **Create a manifest.txt file that states which class has the main() method**

   ![image-20210420134517378](../../assets/img/image-20210420134517378.png)

3. **Run the jar tool to create a JAR file that contains everything in the classes directory,plus the mainfest**

   ![image-20210420134604417](../../assets/img/image-20210420134604417.png)

   ```
   cd MiniProject/classes
   jar -cvmf manifest.txt app.jar *.class
   OR
   jar -cvmf manifest.txt app.jar MyApp.class
   ```

# Running (executing) the JAR

![image-20210420140223115](../../assets/img/image-20210420140223115.png)

# Put your classes in packages

![image-20210420141053685](../../assets/img/image-20210420141053685.png)

### Packages prevent class name conflicts

**Packages can prevent name conflicts,but only if you choose a packeage name that’s guaranteed to be unique. The best way to do that is to preface your packages with your reverse domain name.**

![image-20210420141518651](../../assets/img/image-20210420141518651.png)

### To put your class in a package:

1. **Choose a package name**

2. **Put a package statement in your class**

   It must be the first statement in the source code file,above any import statements. There can be only one package statement per souece code file,so **all classes in a source file must be in the same package**. That includes inner classes,of course.

   ![image-20210420141718754](../../assets/img/image-20210420141718754.png)

3. **Set up a matching directory structure**

You <u>must</u> put a class into a directory structure that matches the package hierarchy.

![image-20210420142140609](../../assets/img/image-20210420142140609.png)

# Compiling and running with packages

### Compiling with the -d(directory) flag

![image-20210420142342082](../../assets/img/image-20210420142342082.png)

![image-20210420142512641](../../assets/img/image-20210420142512641.png)

### Running your code

![image-20210420142531097](../../assets/img/image-20210420142531097.png)

### The -d flag tells the compiler,”Put the class into its package directory structure,using the class specified after the -d has the root directory.But…if the directories aren’t there,create them first and then put the class in the right place!”

# Making an executable JAR with packages

1. **Make sure all of your class files are within the correct package structure under the classes directory**
2. **Create a manifest.txt file that states which class has the main() method,adn be sure to use the fully-qualified class name!**
3. **Run the jar tool to create a JAR file taht contains the package directories plus the manifest**

# So where did the manifest file go?

- **List the contents of a JAR**

  ![image-20210420150204585](../../assets/img/image-20210420150204585.png)

- **Extract the contents of a JAR**

  ![image-20210420155642775](../../assets/img/image-20210420155642775.png)

![image-20210420155747247](../../assets/img/image-20210420155747247.png)

# Java Web Start

### End-users launch a Java Web Start app by clicking in a link in a web page. But once the app downloads,it runs outside the brower,just like any other stand-alone Java application. In fact,a Java Web Start app is just an executable JAR that’s distributed over the web.

# How Java Web Start works

1. The client clicks on a Web page link to your JWS application

   ![image-20210420160714334](../../assets/img/image-20210420160714334.png)

2. The Web Server gets the request and sends back a .jnlp file

   ![image-20210420160823133](../../assets/img/image-20210420160823133.png)

3. Java Web Start is started up by the brower. The JWS helper app reads the .jnlp file,and asks the server for the MyApp.jar file

   ![image-20210420160930461](../../assets/img/image-20210420160930461.png)

4. The Web server ‘serves’ up the requested .jar file

   ![image-20210420160955013](../../assets/img/image-20210420160955013.png)

5. Java Web Start gets the JAR and starts the application by calling the specified main() method

   ![image-20210420161255893](../../assets/img/image-20210420161255893.png)

# The .jnlp(Java Network Launch Protocol) file

A .jnlp file is a simple XML document that has serveral different things you can put in,but as a minimum,it should look like this:

![image-20210420162001312](../../assets/img/image-20210420162001312.png)

# Step for making and deploying a Java Web Start app

1. **Make an executable JAR for your application**

   ![image-20210420162344316](../../assets/img/image-20210420162344316.png)

2. **Write a .jnlp file**

   ![image-20210420162354165](../../assets/img/image-20210420162354165.png)

3. **Place your JAR and .jnlp files on your Web server**

   ![image-20210420162422667](../../assets/img/image-20210420162422667.png)

4. **Add a new mime type to your Web server**

   This causes the server to send the .jnlp file with the correct header,so that when the brower receives the .jnlp file it knows what it is and knows to start the JWS helper app

   ![image-20210420162558923](../../assets/img/image-20210420162558923.png)

5. **Create a Web page with a link to your .jnlp file**

   ![image-20210420162634501](../../assets/img/image-20210420162634501.png)



