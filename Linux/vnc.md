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

```
yum install tigervnc-server
Loaded plugins: enabled_repos_upload, langpacks, package_upload, product-id,
              : search-disabled-repos, subscription-manager
rhel-7-server-extras-rpms                                | 2.0 kB     00:00
rhel-7-server-optional-rpms                              | 1.8 kB     00:00
rhel-7-server-rh-common-rpms                             | 2.1 kB     00:00
rhel-7-server-rpms                                       | 2.0 kB     00:00
rhel-7-server-satellite-tools-6.6-rpms                   | 2.1 kB     00:00
rhel-7-server-supplementary-rpms                         | 2.0 kB     00:00
Resolving Dependencies
--> Running transaction check
---> Package tigervnc-server.x86_64 0:1.8.0-17.el7 will be installed
--> Processing Dependency: xorg-x11-xinit for package: tigervnc-server-1.8.0-17.el7.x86_64
--> Processing Dependency: tigervnc-server-minimal for package: tigervnc-server-1.8.0-17.el7.x86_64
--> Processing Dependency: libgnutls.so.28(GNUTLS_2_12)(64bit) for package: tigervnc-server-1.8.0-17.el7.x86_64
--> Processing Dependency: libgnutls.so.28(GNUTLS_1_4)(64bit) for package: tigervnc-server-1.8.0-17.el7.x86_64
--> Processing Dependency: libgnutls.so.28()(64bit) for package: tigervnc-server-1.8.0-17.el7.x86_64
--> Running transaction check
---> Package gnutls.x86_64 0:3.3.29-9.el7_6 will be installed
--> Processing Dependency: trousers >= 0.3.11.2 for package: gnutls-3.3.29-9.el7_6.x86_64
--> Processing Dependency: libnettle.so.4()(64bit) for package: gnutls-3.3.29-9.el7_6.x86_64
--> Processing Dependency: libhogweed.so.2()(64bit) for package: gnutls-3.3.29-9.el7_6.x86_64
---> Package tigervnc-server-minimal.x86_64 0:1.8.0-17.el7 will be installed
--> Processing Dependency: xorg-x11-xkb-utils for package: tigervnc-server-minimal-1.8.0-17.el7.x86_64
--> Processing Dependency: xkeyboard-config for package: tigervnc-server-minimal-1.8.0-17.el7.x86_64
--> Processing Dependency: tigervnc-license for package: tigervnc-server-minimal-1.8.0-17.el7.x86_64
--> Processing Dependency: mesa-dri-drivers for package: tigervnc-server-minimal-1.8.0-17.el7.x86_64
--> Processing Dependency: libXfont2.so.2()(64bit) for package: tigervnc-server-minimal-1.8.0-17.el7.x86_64
--> Processing Dependency: libXdmcp.so.6()(64bit) for package: tigervnc-server-minimal-1.8.0-17.el7.x86_64
---> Package xorg-x11-xinit.x86_64 0:1.3.4-2.el7 will be installed
--> Running transaction check
---> Package libXdmcp.x86_64 0:1.1.2-6.el7 will be installed
---> Package libXfont2.x86_64 0:2.0.3-1.el7 will be installed
---> Package mesa-dri-drivers.x86_64 0:18.3.4-6.el7_7 will be installed
--> Processing Dependency: mesa-filesystem(x86-64) for package: mesa-dri-drivers-18.3.4-6.el7_7.x86_64
--> Processing Dependency: libLLVM-7-rhel.so(LLVM_7)(64bit) for package: mesa-dri-drivers-18.3.4-6.el7_7.x86_64
--> Processing Dependency: libLLVM-7-rhel.so()(64bit) for package: mesa-dri-drivers-18.3.4-6.el7_7.x86_64
---> Package nettle.x86_64 0:2.7.1-8.el7 will be installed
---> Package tigervnc-license.noarch 0:1.8.0-17.el7 will be installed
---> Package trousers.x86_64 0:0.3.14-2.el7 will be installed
---> Package xkeyboard-config.noarch 0:2.24-1.el7 will be installed
---> Package xorg-x11-xkb-utils.x86_64 0:7.7-14.el7 will be installed
--> Processing Dependency: libxkbfile.so.1()(64bit) for package: xorg-x11-xkb-utils-7.7-14.el7.x86_64
--> Running transaction check
---> Package libxkbfile.x86_64 0:1.0.9-3.el7 will be installed
---> Package llvm-private.x86_64 0:7.0.1-1.el7 will be installed
---> Package mesa-filesystem.x86_64 0:18.3.4-6.el7_7 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

================================================================================
 Package                   Arch     Version          Repository            Size
================================================================================
Installing:
 tigervnc-server           x86_64   1.8.0-17.el7     rhel-7-server-rpms   215 k
Installing for dependencies:
 gnutls                    x86_64   3.3.29-9.el7_6   rhel-7-server-rpms   681 k
 libXdmcp                  x86_64   1.1.2-6.el7      rhel-7-server-rpms    34 k
 libXfont2                 x86_64   2.0.3-1.el7      rhel-7-server-rpms   143 k
 libxkbfile                x86_64   1.0.9-3.el7      rhel-7-server-rpms    83 k
 llvm-private              x86_64   7.0.1-1.el7      rhel-7-server-rpms    23 M
 mesa-dri-drivers          x86_64   18.3.4-6.el7_7   rhel-7-server-rpms   7.2 M
 mesa-filesystem           x86_64   18.3.4-6.el7_7   rhel-7-server-rpms    18 k
 nettle                    x86_64   2.7.1-8.el7      rhel-7-server-rpms   327 k
 tigervnc-license          noarch   1.8.0-17.el7     rhel-7-server-rpms    29 k
 tigervnc-server-minimal   x86_64   1.8.0-17.el7     rhel-7-server-rpms   1.0 M
 trousers                  x86_64   0.3.14-2.el7     rhel-7-server-rpms   289 k
 xkeyboard-config          noarch   2.24-1.el7       rhel-7-server-rpms   834 k
 xorg-x11-xinit            x86_64   1.3.4-2.el7      rhel-7-server-rpms    59 k
 xorg-x11-xkb-utils        x86_64   7.7-14.el7       rhel-7-server-rpms   103 k

Transaction Summary
================================================================================
Install  1 Package (+14 Dependent packages)

Total download size: 34 M
Installed size: 114 M
Is this ok [y/d/N]: y
Downloading packages:
(1/15): libXdmcp-1.1.2-6.el7.x86_64.rpm                    |  34 kB   00:00
(2/15): gnutls-3.3.29-9.el7_6.x86_64.rpm                   | 681 kB   00:00
(3/15): libXfont2-2.0.3-1.el7.x86_64.rpm                   | 143 kB   00:00
(4/15): libxkbfile-1.0.9-3.el7.x86_64.rpm                  |  83 kB   00:00
(5/15): mesa-dri-drivers-18.3.4-6.el7_7.x86_64.rpm         | 7.2 MB   00:00
(6/15): mesa-filesystem-18.3.4-6.el7_7.x86_64.rpm          |  18 kB   00:00
(7/15): nettle-2.7.1-8.el7.x86_64.rpm                      | 327 kB   00:00
(8/15): tigervnc-license-1.8.0-17.el7.noarch.rpm           |  29 kB   00:00
(9/15): tigervnc-server-1.8.0-17.el7.x86_64.rpm            | 215 kB   00:00
(10/15): tigervnc-server-minimal-1.8.0-17.el7.x86_64.rpm   | 1.0 MB   00:00
(11/15): trousers-0.3.14-2.el7.x86_64.rpm                  | 289 kB   00:00
(12/15): xkeyboard-config-2.24-1.el7.noarch.rpm            | 834 kB   00:00
(13/15): xorg-x11-xinit-1.3.4-2.el7.x86_64.rpm             |  59 kB   00:00
(14/15): xorg-x11-xkb-utils-7.7-14.el7.x86_64.rpm          | 103 kB   00:00
(15/15): llvm-private-7.0.1-1.el7.x86_64.rpm               |  23 MB   00:05
--------------------------------------------------------------------------------
Total                                              4.8 MB/s |  34 MB  00:07
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  Installing : nettle-2.7.1-8.el7.x86_64                                   1/15
  Installing : llvm-private-7.0.1-1.el7.x86_64                             2/15
  Installing : libXdmcp-1.1.2-6.el7.x86_64                                 3/15
  Installing : tigervnc-license-1.8.0-17.el7.noarch                        4/15
  Installing : libXfont2-2.0.3-1.el7.x86_64                                5/15
  Installing : mesa-filesystem-18.3.4-6.el7_7.x86_64                       6/15
  Installing : mesa-dri-drivers-18.3.4-6.el7_7.x86_64                      7/15
  Installing : xkeyboard-config-2.24-1.el7.noarch                          8/15
groupadd: GID '59' already exists
useradd: group 'tss' does not exist
  Installing : trousers-0.3.14-2.el7.x86_64                                9/15
warning: user tss does not exist - using root
warning: group tss does not exist - using root
warning: user tss does not exist - using root
warning: group tss does not exist - using root
  Installing : gnutls-3.3.29-9.el7_6.x86_64                               10/15
  Installing : libxkbfile-1.0.9-3.el7.x86_64                              11/15
  Installing : xorg-x11-xkb-utils-7.7-14.el7.x86_64                       12/15
  Installing : tigervnc-server-minimal-1.8.0-17.el7.x86_64                13/15
  Installing : xorg-x11-xinit-1.3.4-2.el7.x86_64                          14/15
  Installing : tigervnc-server-1.8.0-17.el7.x86_64                        15/15
Uploading Package Profile
Loaded plugins: langpacks, product-id, subscription-manager
Loaded plugins: langpacks, product-id, subscription-manager
Loaded plugins: langpacks, product-id, subscription-manager
Loaded plugins: langpacks, product-id, subscription-manager
Loaded plugins: langpacks, product-id, subscription-manager
Loaded plugins: langpacks, product-id, subscription-manager
  Verifying  : xorg-x11-xinit-1.3.4-2.el7.x86_64                           1/15
  Verifying  : mesa-dri-drivers-18.3.4-6.el7_7.x86_64                      2/15
  Verifying  : libxkbfile-1.0.9-3.el7.x86_64                               3/15
  Verifying  : trousers-0.3.14-2.el7.x86_64                                4/15
  Verifying  : xkeyboard-config-2.24-1.el7.noarch                          5/15
  Verifying  : mesa-filesystem-18.3.4-6.el7_7.x86_64                       6/15
  Verifying  : libXfont2-2.0.3-1.el7.x86_64                                7/15
  Verifying  : tigervnc-license-1.8.0-17.el7.noarch                        8/15
  Verifying  : xorg-x11-xkb-utils-7.7-14.el7.x86_64                        9/15
  Verifying  : tigervnc-server-minimal-1.8.0-17.el7.x86_64                10/15
  Verifying  : libXdmcp-1.1.2-6.el7.x86_64                                11/15
  Verifying  : tigervnc-server-1.8.0-17.el7.x86_64                        12/15
  Verifying  : nettle-2.7.1-8.el7.x86_64                                  13/15
  Verifying  : gnutls-3.3.29-9.el7_6.x86_64                               14/15
  Verifying  : llvm-private-7.0.1-1.el7.x86_64                            15/15

Installed:
  tigervnc-server.x86_64 0:1.8.0-17.el7

Dependency Installed:
  gnutls.x86_64 0:3.3.29-9.el7_6
  libXdmcp.x86_64 0:1.1.2-6.el7
  libXfont2.x86_64 0:2.0.3-1.el7
  libxkbfile.x86_64 0:1.0.9-3.el7
  llvm-private.x86_64 0:7.0.1-1.el7
  mesa-dri-drivers.x86_64 0:18.3.4-6.el7_7
  mesa-filesystem.x86_64 0:18.3.4-6.el7_7
  nettle.x86_64 0:2.7.1-8.el7
  tigervnc-license.noarch 0:1.8.0-17.el7
  tigervnc-server-minimal.x86_64 0:1.8.0-17.el7
  trousers.x86_64 0:0.3.14-2.el7
  xkeyboard-config.noarch 0:2.24-1.el7
  xorg-x11-xinit.x86_64 0:1.3.4-2.el7
  xorg-x11-xkb-utils.x86_64 0:7.7-14.el7

Complete!
Uploading Enabled Repositories Report
Loaded plugins: langpacks, product-id, subscription-manager

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
