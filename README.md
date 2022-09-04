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
