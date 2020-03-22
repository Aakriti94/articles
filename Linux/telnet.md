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
 - Telnet can be used to test or troubleshoot remote web or mail servers.

## Syntax
 - Telnet to the default port of a host:
    ```
    telnet [host]
    ```
  - Telnet to a specific port of a host:
    ```
    telnet [hostname/ip address] [port] <br>
    telnet www.host.com 8090
    ```

## Usage
The user executes commands on the server by using specific Telnet commands into the Telnet prompt. To end a session and log off, the user ends a Telnet command with Telnet.

- Port used by TCP - port 23
- Port used by SSH - port 22

## Installation:

 - Run the following command: ```yum install telnet```

## Check wheather telnet client is installed in your server or not:

```
which telnet
/usr/bin/telnet

-bash-4.1$ rpm -qa |grep telnet
telnet-0.17-48.el6.x86_64

```

## Notes

- we should have a telnet client to access telnet over a machine or a server.
- Telnet Package must be installed in your system.
- If telnet package isn't installed in your system, it would give error like:

  ```
  telnet some.host.com
  bash: telnet: command not found
  ```
  

## Important Links:
  - https://www.computerhope.com/unix/utelnet.htm
