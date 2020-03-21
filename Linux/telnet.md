# Telnet Client

## What is Telnet?

Telnet is Teletype Network Protocol (Remote access Protocol). It is a command line interface for communication with a remote device or server.

## What is telnet server and telnet client

 - Telnet’s overall function is to define a means by which a user or process on one machine can access and use another machine as if it were locally connected.
 - This makes Telnet inherently client/server in operation, like so many other application protocols in TCP/IP.
 - Usually, the **Telnet client** is a piece of software that acts as an interface to the user, processing keystrokes and user commands and presenting output from the remote machine. eg: command prompt.
 - The **Telnet server** is a program running on a remote computer that has been set up to allow remote sessions.

 > We would be focusing on installation of telnet client in this article.

## Why do we need telnet?
 - To access remote machine over the internet.

## Syntax
 > telnet hostname port <br>
   telnet www.host.com 8090

## Usage
The user executes commands on the server by using specific Telnet commands into the Telnet prompt. To end a session and log off, the user ends a Telnet command with Telnet.

- Port used by TCP - port 23
- Port used by SSH - port 22

## What are common uses for Telnet?
 - Telnet can be used to test or troubleshoot remote web or mail servers.


## Prerequisites of telent command

- we should have a telnet client to access telnet over a machine or a server.
- Telnet Package must be installed in your system.
- If telnet package isn't installed in your system, it would give error like:

  ```
  telnet some.host.com
  bash: telnet: command not found
  ```

## Installation:

 - Run the following command: ```yum install telnet```
 - You would see a output like below.

```
yum install telnet
Loaded plugins: enabled_repos_upload, langpacks, package_upload, product-id,
             : search-disabled-repos, subscription-manager
rhel-7-server-extras-rpms                                | 2.0 kB     00:00
rhel-7-server-optional-rpms                              | 1.8 kB     00:00
rhel-7-server-rh-common-rpms                             | 2.1 kB     00:00
rhel-7-server-rpms                                       | 2.0 kB     00:00
rhel-7-server-satellite-tools-6.6-rpms                   | 2.1 kB     00:00
rhel-7-server-supplementary-rpms                         | 2.0 kB     00:00
(1/6): rhel-7-server-extras-rpms/x86_64/primary            | 369 kB   00:00
(2/6): rhel-7-server-rpms/7Server/x86_64/updateinfo        | 3.5 MB   00:00
(3/6): rhel-7-server-extras-rpms/x86_64/updateinfo         | 218 kB   00:00
(4/6): rhel-7-server-optional-rpms/7Server/x86_64/primary  | 5.7 MB   00:00
(5/6): rhel-7-server-optional-rpms/7Server/x86_64/updatein | 2.5 MB   00:00
(6/6): rhel-7-server-rpms/7Server/x86_64/primary           |  42 MB   00:00
rhel-7-server-extras-rpms                                             1230/1230
rhel-7-server-optional-rpms                                         19663/19663
rhel-7-server-rpms                                                  27016/27016
Resolving Dependencies
--> Running transaction check
---> Package telnet.x86_64 1:0.17-64.el7 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

================================================================================
Package      Arch         Version               Repository                Size
================================================================================
Installing:
telnet       x86_64       1:0.17-64.el7         rhel-7-server-rpms        64 k

Transaction Summary
================================================================================
Install  1 Package

Total download size: 64 k
Installed size: 113 k
Is this ok [y/d/N]: y
Downloading packages:
telnet-0.17-64.el7.x86_64.rpm                              |  64 kB   00:00
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
Warning: RPMDB altered outside of yum.
 Installing : 1:telnet-0.17-64.el7.x86_64                                  1/1
Uploading Package Profile
Loaded plugins: langpacks, product-id, subscription-manager
Loaded plugins: langpacks, product-id, subscription-manager
Loaded plugins: langpacks, product-id, subscription-manager
Loaded plugins: langpacks, product-id, subscription-manager
Loaded plugins: langpacks, product-id, subscription-manager
Loaded plugins: langpacks, product-id, subscription-manager
 Verifying  : 1:telnet-0.17-64.el7.x86_64                                  1/1

Installed:
 telnet.x86_64 1:0.17-64.el7

Complete!
Uploading Enabled Repositories Report
Loaded plugins: langpacks, product-id, subscription-manager

```

## Check wheather telnet client is installed in your server or not:

```
which telnet
/usr/bin/telnet

-bash-4.1$ rpm -qa |grep telnet
telnet-0.17-48.el6.x86_64

```

## Important Links:
  - https://www.computerhope.com/unix/utelnet.htm
