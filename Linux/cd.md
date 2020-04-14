# CD - Change Directory

## What is the cd command?
The cd command is used to change the current directory.

## Syntax
```sh
cd [option] [directory]
```
The items in square brackets are optional.

## Contents
| Options                                                 | command |
| :-------	                                              |   :--   |
|[Change to home directory](https://github.com/Aakriti94/articles/blob/master/Linux/cd.md#change-to-home-directory-cd)|```cd```|
|[Follow symbolic links](https://github.com/Aakriti94/articles/blob/master/Linux/cd.md#follow-symbolic-links-cd--l)|```cd -L```|
|[Don’t follow symbolic links](https://github.com/Aakriti94/articles/blob/master/Linux/cd.md#dont-follow-symbolic-links-cd--p)|```cd -P```|
|[Change the path to root directory](https://github.com/Aakriti94/articles/blob/master/Linux/cd.md#change-the-path-to-root-directory-cd-)|```cd /```|
|[Change to the parent of the current directory](https://github.com/Aakriti94/articles/blob/master/Linux/cd.md#change-to-the-parent-of-the-current-directory-cd-)|```cd ..```|
|[Return directly to its home directory](https://github.com/Aakriti94/articles/blob/master/Linux/cd.md#return-directly-to-its-home-directory-cd--)|```cd ~```|
|[Return to the previous current directory](https://github.com/Aakriti94/articles/blob/master/Linux/cd.md#return-to-the-previous-current-directory-cd--)|```cd -```|
|[Show last working directory from where we moved](https://github.com/Aakriti94/articles/blob/master/Linux/cd.md#show-last-working-directory-from-where-we-moved-cd---)|```cd --```|
|[Absolute and Relative Path Names](https://github.com/Aakriti94/articles/blob/master/Linux/cd.md#absolute-and-relative-path-names)||
|[Directories with Space in Their Names](https://github.com/Aakriti94/articles/blob/master/Linux/cd.md#directories-with-space-in-their-names-cd-dir-name-with-space-cd-dir-name-with-space)|```cd 'Dir name with space'```|
|[Change from current working directory to a particular directory and list all its settings in one go](https://github.com/Aakriti94/articles/blob/master/Linux/cd.md#change-from-current-working-directory-to-a-particular-directory-and-list-all-its-settings-in-one-go-cd-my_work--ls)|```cd ~/[dir_name] && ls```|
|[Create directory and switch to it using single command](https://github.com/Aakriti94/articles/blob/master/Linux/cd.md#create-directory-and-switch-to-it-using-single-command-mkdir-dir-name--cd-_)|```mkdir [dir-name] && cd $_```|
|[Create a directory named ‘-’ and switch to it](https://github.com/Aakriti94/articles/blob/master/Linux/cd.md#create-a-directory-named---and-switch-to-it-cd--)|```cd ./-```|
|[The working directory](https://github.com/Aakriti94/articles/blob/master/Linux/cd.md#the-working-directory-cd-)|```cd .```|
|[Notes](https://github.com/Aakriti94/articles/blob/master/Linux/cd.md#notes)||


## Options

#### Change to home directory: ```cd```
When used without any argument, ```cd``` will take you to your home directory.
The [```pwd``` command](https://github.com/Aakriti94/articles/blob/master/Linux/pwd.md) allows you to find out what directory you are currently in.
```sh
-bash-4.2$ pwd
/cos/home3/akashyap/scripting
-bash-4.2$ cd
-bash-4.2$ pwd
/cos/home3/akashyap
```

#### Follow symbolic links: ```cd -L```
Force symbolic links to be followed. In other words, if you tell cd to move into a "directory", which is actually a symbolic link to a directory, it moves into the directory the symbolic link points to.

This option is the default behavior of cd. Normally, it will always act as if ```-L``` was specified.

```sh
-bash-4.2$ cd /
-bash-4.2$ pwd
/
-bash-4.2$ ll | grep bin
lrwxrwxrwx    1 root root     7 Apr 24  2018 bin -> usr/bin
lrwxrwxrwx    1 root root     8 Apr 24  2018 sbin -> usr/sbin
-bash-4.2$ cd -L bin
-bash-4.2$ pwd
/bin
-bash-4.2$ cd /
-bash-4.2$ pwd
/
-bash-4.2$ cd -P bin
-bash-4.2$ pwd
/usr/bin
```

#### Don’t follow symbolic links: ```cd -P```
Use the physical directory structure without following symbolic links. In other words, only change into the specified directory if it actually exists as named; symbolic links will not be followed. This option is the opposite of the ```-L``` option, and if they are both specified, this option will be ignored.

```sh
-bash-4.2$ cd /
-bash-4.2$ pwd
/
-bash-4.2$ ll | grep bin
lrwxrwxrwx    1 root root     7 Apr 24  2018 bin -> usr/bin
lrwxrwxrwx    1 root root     8 Apr 24  2018 sbin -> usr/sbin
-bash-4.2$ cd -L bin
-bash-4.2$ pwd
/bin
-bash-4.2$ cd /
-bash-4.2$ pwd
/
-bash-4.2$ cd -P bin
-bash-4.2$ pwd
/usr/bin
```

```cd -P -e``` : If the ```-P``` option is specified, and the current working directory cannot be determined, this option tells ```cd``` to exit with an error. If ```-P``` is not specified along with this option, this option has no function.

#### Change the path to root directory: ```cd /```
This command would change your current working directory to root.
```sh
-bash-4.2$ pwd
/home/akashyap/scripts

-bash-4.2$ cd /
-bash-4.2$ pwd
/
```

#### Change to the parent of the current directory: ```cd ..```
 - The current directory is represented by a single dot: ```.```
 - Its parent directory is represented by two consecutive dots: ```..```

```sh
  -bash-4.2$ pwd
  /cos/home3/akashyap
  -bash-4.2$ cd scripting
  -bash-4.2$ pwd
  /cos/home3/akashyap/scripting
  -bash-4.2$ cd ..
  -bash-4.2$ pwd
  /cos/home3/akashyap
```

#### Return directly to home directory: ```cd ~``` <br>
A home directory, also called a login directory, that serves as the repository for a user's personal files, directories and programs. It is also the directory that a user is first in after logging into the system.
```sh
-bash-4.2$ pwd
/cos/home3/akashyap
-bash-4.2$ cd my_work/
-bash-4.2$ cd 2020
-bash-4.2$ pwd
/cos/home3/akashyap/my_work/2020
-bash-4.2$ cd ~
-bash-4.2$ pwd
/cos/home3/akashyap
```

If you want to navigate to the scripting directory, which is inside your home directory, you would type:
```sh
-bash-4.2$ pwd
/cos/home3/akashyap
-bash-4.2$ cd my_work/2019/dbcc/
-bash-4.2$ pwd
/cos/home3/akashyap/my_work/2019/dbcc
-bash-4.2$ cd ~/scripting
-bash-4.2$ pwd
/cos/home3/akashyap/scripting
```

You can also navigate to another user’s home directory using the following syntax: ```cd ~username```
```sh
-bash-4.2$ pwd
/root
-bash-4.2$ cd ~wiki/
-bash-4.2$ pwd
/home/wiki
-bash-4.2$ cd ~jira
-bash-4.2$ pwd
/home/jira
```

#### Return to the previous current directory: ```cd -```
When followed by a space and then a hyphen, ```cd``` both return the user to the previous current directory and reports on a new line the absolute pathname of that directory.
```sh
-bash-4.2$ pwd
/cos/home3/akashyap/my_work/2020
-bash-4.2$ cd ~
-bash-4.2$ pwd
/cos/home3/akashyap
-bash-4.2$ cd -
/cos/home3/akashyap/my_work/2020
```

#### Show last working directory from where we moved: ```cd --```
```sh
-bash-4.2$ pwd
/cos/home3/akashyap
-bash-4.2$ cd /cos/home3/akashyap/my_work/2020/jira-analysis
-bash-4.2$ pwd
/cos/home3/akashyap/my_work/2020/jira-analysis
-bash-4.2$ cd /cos/home3/akashyap/my_work/
-bash-4.2$ pwd
/cos/home3/akashyap/my_work
-bash-4.2$ cd -
/cos/home3/akashyap/my_work/2020/jira-analysis
-bash-4.2$ pwd
/cos/home3/akashyap/my_work/2020/jira-analysis
-bash-4.2$ cd --
-bash-4.2$ pwd
/cos/home3/akashyap
```

#### Absolute and Relative Path Names
The absolute or full path starts from the system root /, and the relative path starts from your current directory. By default, when you log into your Linux system, your current working directory is set to your home directory.
 - Our home directory is: ```/cos/home3/akashyap```
 - Folder ```scripting``` is inside our home directory.
 - We can use the **Relative Path Name** to navigate to ```scripting``` as ```cd scripting```
 - **Absolute  Path Name** as ```cd /cos/home3/akashyap/scripting```

```sh
-bash-4.2$ pwd
/cos/home3/akashyap
-bash-4.2$ ll
total 48
drwxr-xr-x 5 akashyap users 4096 Mar 26  2019 mywebproject
drwxr-xr-x 4 akashyap users 4096 Feb 16 21:31 my_work
drwxr-xr-x 3 akashyap users 4096 Feb 16 21:42 scripting

-bash-4.2$ cd scripting
-bash-4.2$ pwd
/cos/home3/akashyap/scripting
-bash-4.2$ cd ..
-bash-4.2$ pwd
/cos/home3/akashyap
-bash-4.2$ cd /cos/home3/akashyap/scripting
-bash-4.2$ pwd
/cos/home3/akashyap/scripting
```

#### Directories with Space in Their Names: ```cd 'Dir name with space'```, ```cd Dir\ name\ with\ space```
```sh
-bash-4.2$ ll
drwxr-xr-x 2 akashyap users 4096 Apr  3 00:35 dir with a space
-bash-4.2$ cd dir\ with\ a\ space/
-bash-4.2$ pwd
/cos/home3/akashyap/dir with a space
or, you can do
-bash-4.2$ cd 'dir with a space'/
-bash-4.2$ pwd
/cos/home3/akashyap/dir with a space
```

#### Change from current working directory to a particular directory and list all its settings in one go: ```cd ~/[dir_name] && ls```
```sh
-bash-4.2$ cd ~/my_work/ && ll
drwxr-xr-x 4 akashyap users 4096 Feb 16 23:23 2019
drwxr-xr-x 3 akashyap users 4096 Feb 16 21:38 2020
-bash-4.2$ pwd
/cos/home3/akashyap/my_work
```

#### Create directory and switch to it using single command: ```mkdir [dir-name] && cd $_```
The ```&&``` operator is used for executing multiple commands, and ```$_``` expands to the last argument of the previous command.
```sh
-bash-4.2$ mkdir new_dir && cd $_
-bash-4.2$ pwd
/cos/home3/akashyap/new_dir
```

#### Create a directory named ‘-’ and switch to it: ```cd ./-```
As we have already discussed, the ```-```  symbol when used with ```cd``` command takes you to the previous working directory. But what if you want to switch to a directory with ```-``` as its name? You can do this by using relative path:
```sh
-bash-4.2$ mkdir '-'
-bash-4.2$ ll
drwxr-xr-x 2 akashyap users 4096 Apr  3 15:27 -
-bash-4.2$ cd ./-/
-bash-4.2$ pwd
/cos/home3/akashyap/new_dir/-
```

#### The working directory: ```cd .```
  - The current directory, regardless of which directory it is, is represented by a single dot ```.```
  - It would change us into the current directory. In other words, it would do nothing.
  - [Here is the list where you can find ```cd .``` command useful.](https://unix.stackexchange.com/questions/447864/is-there-any-case-in-which-the-cd-single-dot-command-could-be-useful)

```sh
cd .
```


## Notes:
  - ```cd``` is a shell builtin.

  - When navigating through the file system, you can use the ```Tab``` key to autocomplete the names of directories. Adding a slash at the end of the directory name is optional. But, I would suggest to always have a slash at the end.
  - Check the path of ```cd``` command binary:
    ```sh
    bash-4.2$ which cd
    /usr/bin/cd
    ```
  - Verify:
    ```sh
    bash-4.2$ type cd
    cd is a shell builtin
    ```
  - To switch to a directory, you must have executable permissions for that directory.
