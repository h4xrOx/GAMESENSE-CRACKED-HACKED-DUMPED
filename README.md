# Gamesense.pub cracked Loader, cheat engine & scripting CLI
### For help or more tutorials, leaks, cheats, hacks & h4xr0x join the community or follow here:
#### */* https://gamesense.cloud
#### */* https://h4xr0x.cc
#### */* https://discord.gg/EYCBURUPcm

# Tutorial: How to build gamesense.pub's loader

# Prerequisites 

#### */* --you will need to install WSL2: https://ubuntu.com/tutorials/working-with-visual-studio-code-on-ubuntu-on-wsl2#1-overview 
#### */* --you will need Ubuntu 20.04:  https://apps.microsoft.com/store/detail/ubuntu-20044-lts/9MTTCL66CPXJ
#### */* --you will need to install NodeJS: https://ubuntu.com/tutorials/working-with-visual-studio-code-on-ubuntu-on-wsl2#5-install-nodejs-and-create-a-new-project
#### */* --you will need to install sdkman: ``curl -s "https://get.sdkman.io" | bash``
#### */* --you will need to then install ``sdk install maven`` ``sdk instal spring-boot`` ``sdk isntall java`` ``sdk install quarkus``
#### */* --you will need to install: Visual Studio Code https://code.visualstudio.com/
#### */* --you will need to install the Remote Development extention: https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-   extensionpack
#### */* --you will need to install docker desktop: https://docs.docker.com/desktop/install/windows-install/
-----------------------------------------------------------------------------------------------------------------------------------------------------------
# Building the GameSense.pub Loader from source
## table of contents
#### */* --Installation of Prerequisites
#### */* --Setting up your enviorment
#### */* --updating and applying configurations
#### */* --compiling the loader with openapi and COR services
#### */* --Building the Gamesense.pub Loader with Gamesense Docs: ``https://github.com/h4xrOx/docs``
#### */* **note: you could use any documentation for use with any cheat, this is a class loader at base, includes multiple plugins, easy to customize & integrate CORS**
------------------------------------------------------------------------------------------------------------------------------------------------------------
# Installing OpenSSH Server on Ubuntu 20.04

### First of all, as always, make sure that your current packages are up to date for security purposes.

```
sudo apt-get update
```

### Now that all packages are up-to-date, run the “apt-get install” command in order to install OpenSSH.

```
sudo apt-get install openssh-serve
```

### From steps displayed on your console, you should see A configuration file is created in the `/etc/ssh` a folder named `sshd_config`. Symbolic links are created. One named `sshd.service` (your systemd service) and one in the multi-user target (to boot SSH when you log in).

```
sudo systemctl status sshd
```

```
netstat -tulpn | grep 22^
```

### if you don't have netstat by default

 ```
 sudo apt-get install net-tools
 ```

-------------------------------------------------------------------------------------------------------------------------------------------------------------

# Enabling SSH traffic on your firewall settings

### To enable SSH connections on your host, run the following command

```
sudo ufw allow ssh
```

### To check if you are using UFW firewall

```
sudo ufw status
```

### If not enabled, run the following command

```
sudo ufw enable
``` 

```
sudo ufw reset
```

## Enable SSH server on system boot

```
sudo systemctl list-unit-files | grep enabled | grep ssh
```

### If you have no results on your terminal, you should “enable” the service in order for it to be launched at boot time.

```
sudo systemctl enable ssh
```

### Restarting your SSH server to apply the changes

```
sudo systemctl restart sshd
```

```
sudo systemctl status sshd
```

### Enabling port 8080 for the API, enter the following command:

```
netstat -tulpn | grep
```

### If you are doing this on LAN to use locally make sure to get the local IP by

```
sudo ifconfig
```

### In order to connect to your SSH server, you will use your username and ip address

```
ssh -p <port> <username>@<ip_address>
```

### DISABLING your SSH server, for any reason you type the following commands

```
sudo systemctl stop sshd
```

```
sudo systemctl status sshd
```
-------------------------------------------------------------------------------------------------------------------------------------------------------------

# Fork this repo and load the project in Visual Studio Code to create the Hello World Quarkus app, also known as the Gamesense.pub reflective class loader. During this part of the tutorial we will be completing the following tasks:

#### */* -- Bootstrapping an application

#### */* -- Creating a JAX-RS endpoint

#### */* -- Injecting beans

#### */* -- Functional tests

#### */* -- Packaging of the application

## Prerequisites To complete this guide, you need:

#### */* -- Roughly 15 minutes
#### */* -- Visual Studio Code or another IDE
#### */* -- JDK 11+ installed with JAVA_HOME configured appropriately
#### */* -- Apache Maven 3.8.1+
#### */* -- Optionally the Quarkus CLI if you want to use it & it: https://quarkus.io/guides/cli-tooling

#### open an integrated terminal in WSL Ubuntu from the `/demo/gs/` directory. Type the following command and make sure to follow any instructions that may pop up due to dependancies to install sdkman:

```
curl -s "https://get.sdkman.io" | bash
```

#### open a new terminal in the same directory and type the following commands to finish the installation of sdkman:

```
source "$HOME/.sdkman/bin/sdkman-init.sh"
```
 ``sdk install maven`` ``sdk instal spring-boot`` ``sdk isntall java`` ``sdk install quarkus``
*/* 

#### As root user type the following command:

```
mvn io.quarkus.platform:quarkus-maven-plugin:2.12.0.Final:create \
    -DprojectGroupId=gamesense.org.acme \
    -DprojectArtifactId=gs
```
  
 #### */* -- If you have all dependancies, followed the instructions and your screen mirrors the image below, congradulations!! You are on you way to owning gamesense.pub!

![image](https://user-images.githubusercontent.com/65768277/188302306-47028f3e-209c-483a-a5dd-08963db39880.png)

# the Maven structure 

 #### */* -- an org.gamesense.acme.GreetingResource resource exposed on /hello

 #### */* -- an associated unit test

 #### */* -- a landing page that is accessible on http://localhost:8080 after starting the application

 #### */* -- example Dockerfile files for both native and jvm modes in `src/main/docker`

 #### */* -- the application configuration file

####Once generated, look at the pom.xml. You will find the import of the Quarkus BOM, allowing you to omit the version of the different Quarkus ####dependencies. In addition, you can see the quarkus-maven-plugin responsible of the packaging of the application and also providing the development mode. ####I had you navigate to `/demo/gs/` so you could this. I have already buildt the application in the main directory which has all dependancies and structure ####as a to guide you at any point you feel you need a reference.

# The JAX-RS resources

#### During the project creation, the src/main/java/org/acme/GreetingResource.java file has been created with the following content:

```
package org.gamesense.acme;

import javax.ws.rs.GET;
import javax.ws.rs.Path;
import javax.ws.rs.Produces;
import javax.ws.rs.core.MediaType;

@Path("/hello")
public class GreetingResource {

    @GET
    @Produces(MediaType.TEXT_PLAIN)
    public String hello() {
        return "Hello from RESTEasy Reactive";
    }
}
```

### It’s a very simple REST endpoint, returning "Hello from RESTEasy Reactive" to requests on "/hello".

# Now we are ready to run our application, type the following command:

```
./mvnw quarkus:dev
```

#### Your IDE should give you a simular output as the image below:

![image](https://user-images.githubusercontent.com/65768277/188303464-8c4ef7dc-8f4b-4cbd-aaa4-7d73d6600d4f.png)

#### Once started, you can request the provided endpoint:

```
$ curl -w "\n" http://localhost:8080/hello

Hello from RESTEasy Reactive
```

 #### */* -- We are using curl -w "\n" in this example to avoid your terminal printing a '%' or put both result and next command prompt on the same line.

 #### */* --  Hit CTRL+C to stop the application, or keep it running and enjoy the blazing fast hot-reload.

 #### */* -- Automatically add newline with curl -w "\n"
 
# Using injection

#### */* -- Dependency injection in Quarkus is based on ArC which is a CDI-based dependency injection
#### */* -- ArC comes as a dependency of quarkus-resteasy-reactive so you already have it handy. 

### if you stopped the application, restart it with the following command:

```
./mvnw quarkus:dev
```

### Then check that the endpoint returns hello quarkus as expected:

```
$ curl -w "\n" http://localhost:8080/hello/greeting/quarkus
hello quarkus
```

#### Normally you have to Modify the application and add a companion bean. Create the src/main/java/org/acme/GreetingService.java, navigate to it, here is where we can add import dependancies and features we want to add for testing or updates.



# Development Mode

## All that Gamesense.pub and cheat documentation. How does it work? How did I hack it? I'll tell you. RESTful API's use whats known as The OAS contract describes what the API does, it’s request parameters and response objects, all without any indication of code implementation. Web services defined with OAS can communicate with each other irrespective of the language they’re built in, since OAS is language agnostic and machine readable. 

## OAS Generation During Runtime

#### Swagger-core is the Java implementation of Swagger. Current version supports JAX-RS and plain servlets.
In this method, the Swagger/OAS contract is generated from an API based on the meta-data added against the various resources, methods and controllers. This meta-data will generate the contract, client-side code, and other artifacts during runtime. Typically, this meta-data will be in the form of code annotations. The tools trigger as the various methods and functions are called against their resources, and produces the OAS contract from the metadata defined in the API.

## There are three steps required to generate an OAS document from an existing API:

#### */* --  Adding dependencies to your application
#### */* --  Hooking Swagger Core to the Application
#### */* --  Initialize the OAS Contract

#### The Swagger project uses maven for build and deployment of artifacts, available on Maven Central. Maven dependencies need JAX-RS coded API for Swagger Core to run. We hooked Swagger Core into the API with spring to get the dependancies. OAS definition can be initialized within an application during its runtime. The generated OAS definition will be in two files, defined in JSON and YAML. Take a look at swagger inspector https://swagger.io/tools/swagger- and insert the end point of the resource you want to have documented. You can then navigate to the right panel from the History section of Swagger Inspector, and click "Create API definition" to create the OAS definition.

![image](https://user-images.githubusercontent.com/65768277/188306662-47be1365-ad39-459a-be89-c85a815cb8a6.png)




The cool thing about Inspector is that you can select multiple end points and consolidate their documentation in one single OpenAPI file through a Collection.

 mvnw compile quarkus:dev


#### quarkus:dev runs Quarkus in development mode. This enables live reload with background compilation, which means that when you modify your Java files and/or your resource files and refresh your browser, these changes will automatically take effect. This works too for resource files like the configuration property file. Refreshing the browser triggers a scan of the workspace, and if any changes are detected, the Java files are recompiled and the application is redeployed; your request is then serviced by the redeployed application. If there are any issues with compilation or deployment an error page will let you know.

#### This will also listen for a debugger on port 5005. If you want to wait for the debugger to attach before running you can pass -Dsuspend on the command line. If you don’t want the debugger at all you can use -Ddebug=false.


https://gamesensical.gitbook.io/docs/developers/globals/bit




