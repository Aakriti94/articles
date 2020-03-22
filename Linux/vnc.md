# VNC
VNC stands for Virtual Network Computing. <br>
If you need to login as remote into a GUI-enabled Linux server, your fastest, cheapest option is VNC.

TigerVNC (Tiger Virtual Network Computing) is a system for graphical desktop sharing which allows you to remotely control other computers.
TigerVNC works on the client-server principle: a server shares its output (vncserver) and a client (vncviewer) connects to the server.

## Install and Configure VNC Server in RHEL 7

#### Install Tigervnc and other dependency packages

```
yum install tigervnc-server
```

#### See if Tigervnc and other dependency packages are installed

```
rpm -qa | grep  tigervnc-server
tigervnc-server-module-1.1.0-24.el6.x86_64
tigervnc-server-1.1.0-24.el6.x86_64
tigervnc-server-applet-1.1.0-24.el6.noarch
```

## How can I verify which vncserver version is installed on my computer?

You should see the following Output when running the following commands.
```
which vncserver
/usr/bin/vncserver

rpm -qa | grep tigervnc-server
tigervnc-server-module-1.1.0-24.el6.x86_64
tigervnc-server-1.1.0-24.el6.x86_64
tigervnc-server-applet-1.1.0-24.el6.noarch

rpm -qa | grep -i vnc
tigervnc-1.1.0-24.el6.x86_64
tigervnc-server-module-1.1.0-24.el6.x86_64
tigervnc-server-1.1.0-24.el6.x86_64
tigervnc-server-applet-1.1.0-24.el6.noarch
```

## How to run vncserver for a host?

  1. Open your terminal and type command: ```vncserver```

      ```
      -bash-4.1$ vncserver

      New 'hotsname:5 (akashyap)' desktop is hotsname:5

      Starting applications specified in /home/akashyap/.vnc/xstartup
      Log file is /home/akashyap/.vnc/hotsname:5.log
      ```

      - ```hotsname``` is the hostname of my server.
      - ```akashyap``` is my username through which I am logged in.
      - You would be promted to set the VNC password for the User, if you are logging in for the first time.


  2. Download VNC-Viewer windows application and run it. [Download here.](https://www.realvnc.com/en/connect/download/vnc/linux/)

  3. Enter the full hostname (whatever.hotsname.com) in the column that says "Enter a VNC Server address or search" and a no. mentioned after colon in step 1.
  ```
  full hostname:no.
  whatever.hotsname.com:5
  ```
  4. Click "continue" when they ask the session will not be encrypted.
  5. Enter the password. The password here asked is the password you kept when you first attempted to connect to VNCserver. (Step 1)
  6. It would establish a connection and ask for password for the user you are logging in with.
  7. The password asked in step 6 is the password for the user on the server (whatever.hotsname.com).
  8. And the graphical view of your server is successfully started.
  9. **Open terminal view of your server:** Applications -> System Tools -> terminal.


## Important Links
  - ep.ph.bham.ac.uk/general/support/vncsetup.html
  - https://www.stuartellis.name/articles/vnc-on-linux/
