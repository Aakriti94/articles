# PWD - Print Work Directory

## What is the pwd command?
The ```pwd``` command is a command line utility for printing the current working directory.

## Syntax
```
pwd [OPTION]...
```

## Contents
| Options                                                 | command |
| :-------	                                              |   :--   |
|**[Print the current working directory]()**|```pwd```||**[Print the current working directory]()**|```pwd```|
|**[Display the logical current working directory]()**|```pwd```|
|**[Avoid symlinks]()**|```pwd -P```|
|**[Reference ```pwd``` in shell scripts]()**|```echo $PWD```|
|**[Display ```pwd``` command version]()**|```pwd --version```|
|**[Information about pwd]()**|```pwd --help```|
|**[Display in command line prompt]()**| |
|**[Set multi-line command line prompt]()**| |
|**[One Liners]()**| |
|**[Notes]()**| |



## Exit Status
|Exit Status |	Message|
|  :----: | :----: |
|   0     |	Success|
| Non-zero| Failure|

## Options
#### Print the current working directory: ```pwd```
```
pwd
/cos/home3/akashyap
```

#### Display the logical current working directory: ```pwd -L```, ```--logical```
The ```-L``` option stands for Logical Links. It cause ```pwd``` to use ```$PWD``` from environment, even if it contains symlinks. It do not resolve symlinks.
```
-bash-4.2$ pwd -L
/cos/home3/akashyap
```

#### Avoid symlinks: ```pwd -P```, ```--physical```
The ```-P``` option stands for Physical Links. It will cause ```pwd``` to show the physical location rather than a symlink.
```
-bash-4.2$ cd /
-bash-4.2$ ll | grep bin
lrwxrwxrwx    1 root root     7 Apr 24  2018 bin -> usr/bin
lrwxrwxrwx    1 root root     8 Apr 24  2018 sbin -> usr/sbin
-bash-4.2$ cd bin/
-bash-4.2$ pwd
/bin
-bash-4.2$ pwd -P
/usr/bin
```

- If no options are given at run-time does “pwd” takes option -P into account or not, automatically.
  ```
  -bash-4.2$ pwd
  /cos/home3/akashyap
  -bash-4.2$ pwd -P
  /cos/home3/akashyap
  ```

#### Reference ```pwd``` in shell scripts:
In most shells the $PWD variable is available and is set each time a user or in script changes directory. As such this variable can be referenced to show the current working directory.
```
-bash-4.2$ cd /cos/home3/akashyap/
-bash-4.2$ echo $PWD
/cos/home3/akashyap
```
 - ```pwd``` command could be stored in a variable.
  ```
  -bash-4.2$ CWD=$(pwd)
  -bash-4.2$ echo $CWD
  /cos/home3/akashyap

  -bash-4.2$ echo "Current working directory is : $PWD"
  Current working directory is : /cos/home3/akashyap
  ```
 - Is it better to use ```$(pwd)``` or ```$PWD```? - https://unix.stackexchange.com/questions/173916/is-it-better-to-use-pwd-or-pwd

#### Display ```pwd``` command version: ```/bin/pwd --version```
```
/bin/pwd --version
pwd (GNU coreutils) 8.22
Copyright (C) 2013 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>.
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.

Written by Jim Meyering.
```

#### To see information about pwd, enter: ```/bin/pwd --help```

#### Display in command line prompt:
```
-bash-4.2$ PS1='$pwd> '
> ls
backup  id_rsa      mywebproject  new-apache-project  opt        web
demo    id_rsa.pub  my_work       newport             scripting  z.sh
> pwd
/cos/home3/akashyap
```

#### Set multi-line command line prompt:
```
-bash-4.2$ PS1='
> $PWD
> 123#Hello#!
> '

/cos/home3/akashyap
123#Hello#!
ls
backup  id_rsa      mywebproject  new-apache-project  opt        web
demo    id_rsa.pub  my_work       newport             scripting  z.sh

/cos/home3/akashyap
123#Hello#!
pwd
/cos/home3/akashyap
```

## One Liners:
  - What is the absolute path (starting from /) of the ```pwd``` source file? <br>
    ```/usr/include/pwd.h```

  - What is the absolute path (starting from /) of the pwd binary file? <br>
    ```/bin/pwd ```

  - Print the absolute path (starting from /) of the pwd manual pages file. <br>
    ```/usr/share/man/man1/pwd.1.gz```

## Notes:

 - #### ```pwd``` is normally a shell builtin
    In most shells pwd is a shell builtin. This means the command is present in the shell rather than calling an external program. This means that the code will run significantly faster than calling an external executable.
    ```
    which pwd
    pwd: shell builtin command
    ```

    Whilst most shells have pwd as a shell builtin the command also exists on systems as an executable.
    ```
    -bash-4.2$ which pwd
    /usr/bin/pwd
    ```

    To see all locations containing an executable named pwd, enter:
    ```
    -bash-4.2$ type -a pwd
    pwd is a shell builtin
    pwd is /usr/bin/pwd
    ```
    - By typing ```pwd```, you end up using the shell builtin provided by bash: ```pwd```
      ```
      -bash-4.2$ pwd
      /cos/home3/akashyap
      ```
    - To use the binary version, type full path ```/bin/pwd```: ```/usr/bin/pwd```
      ```
      -bash-4.2$ /usr/bin/pwd
      /cos/home3/akashyap
      ```
