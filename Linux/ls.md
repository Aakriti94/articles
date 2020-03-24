# LS Command

## What is the ls command?
```ls``` lists files and directories, and their associated metadata, such as file size, ownership, and modification time. With no options, ls lists the files contained in the current directory, sorting them alphabetically.
<br>

## Syntax
```sh
ls [OPTIONS] [FILES]
```

## Contents

| Options                                                 | command |
| :-------	                                              |   :--   |
|**[Show the contents of a directory](#https://github.com/Aakriti94/articles/blob/master/Linux/ls.md#show-the-contents-of-a-directory)**|```ls```|
|**[Show hidden files and folders](#https://github.com/Aakriti94/articles/blob/master/Linux/ls.md#show-hidden-files-and-folders-ls--a-)**|```ls -a```|
|**[Show a long listing](#https://github.com/Aakriti94/articles/blob/master/Linux/ls.md#show-a-long-listing-ls--l)**|```ls -l```|
|**[Sort by size](#https://github.com/Aakriti94/articles/blob/master/Linux/ls.md#sort-by-size-ls--s-ls--ls-)**|```ls -lS```|
|**[Sort by modification time](#https://github.com/Aakriti94/articles/blob/master/Linux/ls.md#sort-by-modification-time-ls--lt)**|```ls -lt```|
|**[Sort in the reverse order](#https://github.com/Aakriti94/articles/blob/master/Linux/ls.md#sort-in-the-reverse-order-ls--lr)**|```ls -lr```|
|**[Sort alphabetically by extension](#https://github.com/Aakriti94/articles/blob/master/Linux/ls.md#sort-alphabetically-by-extension-ls--lx)**|```ls -lX```|
|**[Show file size in human readable format](#https://github.com/Aakriti94/articles/blob/master/Linux/ls.md#show-file-size-in-human-readable-format-ls--lh)**|```ls -lh```|
|**[Display one file or folder per line](#https://github.com/Aakriti94/articles/blob/master/Linux/ls.md#display-one-file-or-folder-per-line-ls--1)**|```ls -1```|
|**[Show a recursive listing](#https://github.com/Aakriti94/articles/blob/master/Linux/ls.md#show-a-recursive-listing-ls--r)**|```ls -lR```|
|**[Append file types to listings](#https://github.com/Aakriti94/articles/blob/master/Linux/ls.md#append-file-types-to-listings-ls--f)**|```ls -F```|
|**[Display Inode number of File or Directory](#https://github.com/Aakriti94/articles/blob/master/Linux/ls.md#display-inode-number-of-file-or-directory-ls--li)**|```ls -li```|
|**[Display UID and GID of Files](#https://github.com/Aakriti94/articles/blob/master/Linux/ls.md#display-uid-and-gid-of-files-ls--n)**|```ls -n```|
|**[Listing the name of the files without the name of its owner](#https://github.com/Aakriti94/articles/blob/master/Linux/ls.md#listing-the-name-of-the-files-without-the-name-of-its-owner-ls--g)**|``ls -g``|
|**[Listing the name of files without the name of group](#https://github.com/Aakriti94/articles/blob/master/Linux/ls.md#listing-the-name-of-files-without-the-name-of-group-ls--lg)**|```ls -lG```|
|**[List the size of files and folders in desired scale format](#https://github.com/Aakriti94/articles/blob/master/Linux/ls.md#list-the-size-of-files-and-folders-in-desired-scale-format-ls---block-sizem--l-ls---block-sizek--l)**|```ls --block-size=M -l```|
|**[Show author of each file](#https://github.com/Aakriti94/articles/blob/master/Linux/ls.md#show-author-of-each-file-ls---author--l)**|```ls --author -l```|
|**[Print the contents of a directory separated with comma](#https://github.com/Aakriti94/articles/blob/master/Linux/ls.md#print-the-contents-of-a-directory-separated-with-comma-ls--m-ls---formatcomma-)**|```ls -m```|
|**[Enclose your output in double quotes](#https://github.com/Aakriti94/articles/blob/master/Linux/ls.md#enclose-your-output-in-double-quotes-ls--q)**|```ls -Q```|
|**[Manually assign the value of screen width and control number of columns appearing](#https://github.com/Aakriti94/articles/blob/master/Linux/ls.md#manually-assign-the-value-of-screen-width-and-control-number-of-columns-appearing-ls---width-no)**|```ls --width 80```|
|**[Ignoring Files](#https://github.com/Aakriti94/articles/blob/master/Linux/ls.md#ignoring-files-ls---hide)**|```ls --hide```|
|**[Dired mode](#https://github.com/Aakriti94/articles/blob/master/Linux/ls.md#Dired-mode-ls--ld)**|```ls -lD```|
|**[Print the name of folders before directories](#https://github.com/Aakriti94/articles/blob/master/Linux/ls.md#print-the-name-of-folders-before-directories-ls---group-directories-first)**|```ls --group-directories-first```|
|**[List the contents of a directory with time using various time styles](#https://github.com/Aakriti94/articles/blob/master/Linux/ls.md#list-the-contents-of-a-directory-with-time-using-various-time-styles-ls--l-time-stylestyle)**|```ls -l –time-style=[STYLE]```|
|**[Include manual tab size](#https://github.com/Aakriti94/articles/blob/master/Linux/ls.md#include-manual-tab-size-at-the-contents-of-directory-listed-by-ls-command-instead-of-default-8-ls---tabsizevalue)**|```ls --tabsize=[value]```|
|**[One Line Commands](#https://github.com/Aakriti94/articles/blob/master/Linux/ls.md#one-line-commands)**||
|**[Some other not so famous ```ls``` commands](#https://github.com/Aakriti94/articles/blob/master/Linux/ls.md#some-other-not-so-famous-ls-commands)**||
|**[Notes](#https://github.com/Aakriti94/articles/blob/master/Linux/ls.md#notes)**||


## Exit Status

| Exit Status  | Message  |
|:------: | :------  |              
|0	|Everything is OK.|
|1	|There were minor problems; for example, could not access a subdirectory.|
|2	|There were serious problems; for example, a command-line option could not be accessed.|

## Options
#### Show the contents of a directory:
This will list the contents of the directory in alphabetical order.
```sh
-bash-4.2$ ls
backup  id_rsa.pub    my_work             newport  scripting  z.sh
id_rsa  mywebproject  new-apache-project  opt      web
```

#### Show hidden files and folders: ```ls -a ```
```sh
-bash-4.2$ ls -a
.              .cache   id_rsa.pub    new-apache-project  .ssh
..             .config  .lesshst      newport             .viminfo
backup         .gnome2  mywebproject  opt                 web
.bash_history  id_rsa   my_work       scripting           z.sh
```

#### Show a long listing: ```ls -l```
```sh
drwxr-xr-x 3 akashyap users 4096 Apr  2  2019 backup
-rw------- 1 akashyap users 1679 Mar 27  2019 id_rsa
-rw-r--r-- 1 akashyap users  400 Mar 27  2019 id_rsa.pub
drwxr-xr-x 5 akashyap users 4096 Mar 26  2019 mywebproject
drwxr-xr-x 4 akashyap users 4096 Feb 16 21:31 my_work
drwxr-xr-x 3 akashyap users 4096 Jul 15  2019 new-apache-project
drwxr-xr-x 5 akashyap users 4096 Nov 27 00:07 newport
drwxr-xr-x 4 akashyap users 4096 Jan 31  2019 opt
drwxr-xr-x 3 akashyap users 4096 Feb 16 21:42 scripting
drwxr-xr-x 4 akashyap users 4096 Feb 12  2019 web
-rwxr-xr-x 1 akashyap users  397 Feb 25 01:52 z.sh
```

- The file type:
  - ```-``` is a files
  - ```d``` is a directory
  - ```b``` is a  Block special file
  - ```c``` is a  Character special file
  - ```d``` is a  Directory
  - ```l``` is a  Symbolic link
  - ```n``` is a  Network file
  - ```p``` is a  FIFO
  - ```s``` is a  Socket
- The file permissions: ```drwxr-xr-x``` <br>
    - The next nine characters are showing the file permissions.
    - The first three characters are for the user, the next three are for the group, and the last three are for others.
- Number of hard links to the file: ```3```
- File owner: ```akashyap```
- File group: ```users```
- File size: ```4096```
- Date and Time: ```Apr  2  2019```
- File name: ```backup```

#### Sort by size: ```ls -S```, ```ls -lS``` <br>
 In the following example this is combined with the -l option to show a long listing.
```sh
-bash-4.2$ ls -lS
total 44
drwxr-xr-x 3 akashyap users 4096 Apr  2  2019 backup
drwxr-xr-x 5 akashyap users 4096 Mar 26  2019 mywebproject
drwxr-xr-x 4 akashyap users 4096 Feb 16 21:31 my_work
drwxr-xr-x 3 akashyap users 4096 Jul 15  2019 new-apache-project
drwxr-xr-x 5 akashyap users 4096 Nov 27 00:07 newport
drwxr-xr-x 4 akashyap users 4096 Jan 31  2019 opt
drwxr-xr-x 3 akashyap users 4096 Feb 16 21:42 scripting
drwxr-xr-x 4 akashyap users 4096 Feb 12  2019 web
-rw------- 1 akashyap users 1679 Mar 27  2019 id_rsa
-rw-r--r-- 1 akashyap users  400 Mar 27  2019 id_rsa.pub
-rwxr-xr-x 1 akashyap users  397 Feb 25 01:52 z.sh
```

#### Sort by modification time: ```ls -lt```
```sh
-rwxr-xr-x 1 akashyap users  397 Feb 25 01:52 z.sh
drwxr-xr-x 3 akashyap users 4096 Feb 16 21:42 scripting
drwxr-xr-x 4 akashyap users 4096 Feb 16 21:31 my_work
drwxr-xr-x 5 akashyap users 4096 Nov 27 00:07 newport
drwxr-xr-x 3 akashyap users 4096 Jul 15  2019 new-apache-project
drwxr-xr-x 3 akashyap users 4096 Apr  2  2019 backup
-rw-r--r-- 1 akashyap users  400 Mar 27  2019 id_rsa.pub
-rw------- 1 akashyap users 1679 Mar 27  2019 id_rsa
drwxr-xr-x 5 akashyap users 4096 Mar 26  2019 mywebproject
drwxr-xr-x 4 akashyap users 4096 Feb 12  2019 web
drwxr-xr-x 4 akashyap users 4096 Jan 31  2019 opt
```

#### Sort in the reverse order: ```ls -lr```
```sh
ls -lr
total 0
-rw-r--r-- 1 akashyap users 0 Mar 23 10:57 z.sh
-rw-r--r-- 1 akashyap users 0 Mar 23 10:58 y.jsp
-rw-r--r-- 1 akashyap users 0 Mar 23 10:58 r.xml
-rw-r--r-- 1 akashyap users 0 Mar 23 10:58 l.csv
-rw-r--r-- 1 akashyap users 0 Mar 23 10:58 i.cpp
-rw-r--r-- 1 akashyap users 0 Mar 23 10:58 h.exe
-rw-r--r-- 1 akashyap users 0 Mar 23 10:58 b.doc
-rw-r--r-- 1 akashyap users 0 Mar 23 10:57 a.txt
```
#### Sort alphabetically by extension: ```ls -lX```
```sh
-rw-r--r-- 1 akashyap users 0 Mar 23 10:58 i.cpp
-rw-r--r-- 1 akashyap users 0 Mar 23 10:58 l.csv
-rw-r--r-- 1 akashyap users 0 Mar 23 10:58 b.doc
-rw-r--r-- 1 akashyap users 0 Mar 23 10:58 h.exe
-rw-r--r-- 1 akashyap users 0 Mar 23 10:58 y.jsp
-rw-r--r-- 1 akashyap users 0 Mar 23 10:57 z.sh
-rw-r--r-- 1 akashyap users 0 Mar 23 10:57 a.txt
-rw-r--r-- 1 akashyap users 0 Mar 23 10:58 r.xml
```

#### Show file size in human readable format: ```ls -lh```
```sh
ls -lh
-rwxr-xr-x 1 akashyap users  713 Dec  3 21:58 4Dec19-dbcc.sh
-rwxr-xr-x 1 akashyap users 2.1K Dec  4 03:45 5Dec19-dbcc.sh
-rwxr-xr-x 1 akashyap users  30K Apr  2  2019 arguments-in-reverse.sh
-rwxrwxrwx 1 akashyap users 3.8K Dec  9 03:13 cos-to-dr.sh
-rwxr-xr-x 1 akashyap users   52 Apr  2  2019 count-for.sh
-rwxr-xr-x 1 akashyap users  913 Apr  2  2019 counting-jsp-files.sh
-rwxr-xr-x 1 akashyap users   84 Apr  2  2019 count-while.sh
-rwxrwxrwx 1 akashyap users 3.1K Dec  8 21:02 dbcc.sh
-rwxr-xr-x 1 akashyap users    0 Apr  2  2019 debugging.sh
```

#### Display one file or folder per line: ```ls -1```
```sh
-bash-4.2$ ls -1
backup
id_rsa
id_rsa.pub
mywebproject
my_work
new-apache-project
newport
opt
scripting
web
z.sh
```

#### Show a recursive listing: ```ls -R```
```sh
ls -R my_work/
my_work/:
2019  2020

my_work/2019:
dbcc  delete-files

my_work/2019/dbcc:
Database_connection_to_OS.txt  dbcc.sh  Documentation.docx  file.txt  input.csv

my_work/2019/delete-files:
delete-files.sh

my_work/2020:
jira-analysis

my_work/2020/jira-analysis:
Document  Excel_Templates  Scripts

my_work/2020/jira-analysis/Document:
Documentation-demo.docx

my_work/2020/jira-analysis/Excel_Templates:
Cumulative-graphs.xlsx  snapshot.xlsx

my_work/2020/jira-analysis/Scripts:
generate_csv_files.sh  jira-analysis-detail.sh  no_of_issues-JIRA.sh  size_of_each_issue-JIRA.sh
```

#### Append file types to listings: ```ls -F```
To append an indicator of the file type to a directory listing pass the -F option.
The following characters are appended based on this option:

- ```/``` indicates a directory
- ```@``` indicates a symbolic link
- ```|``` indicates a FIFO
- ```=``` indicates a socket
- ```>``` indicates a door
- nothing is shown for regular files

```sh
backup/  id_rsa      mywebproject/  new-apache-project/  opt/        web/
demo/    id_rsa.pub  my_work/       newport/             scripting/  z.sh*
```

#### Display Inode number of File or Directory: ```ls -li```
```sh
88214525 drwxr-xr-x 3 akashyap users 4096 Apr  2  2019 backup
97379564 drwxr-xr-x 2 akashyap users 4096 Mar 23 10:58 demo
83543600 -rw------- 1 akashyap users 1679 Mar 27  2019 id_rsa
83543601 -rw-r--r-- 1 akashyap users  400 Mar 27  2019 id_rsa.pub
73899168 drwxr-xr-x 5 akashyap users 4096 Mar 26  2019 mywebproject
99673907 drwxr-xr-x 4 akashyap users 4096 Feb 12  2019 web
83725088 -rwxr-xr-x 1 akashyap users  397 Feb 25 01:52 z.sh
```

#### Display UID and GID of Files: ```ls -n```
```sh
drwxr-xr-x 3 34293 100 4096 Apr  2  2019 backup
drwxr-xr-x 2 34293 100 4096 Mar 23 10:58 demo
-rw------- 1 34293 100 1679 Mar 27  2019 id_rsa
-rw-r--r-- 1 34293 100  400 Mar 27  2019 id_rsa.pub
drwxr-xr-x 5 34293 100 4096 Mar 26  2019 mywebproject
-rwxr-xr-x 1 34293 100  397 Feb 25 01:52 z.sh
```
  - UserID: 34293
  - GroupID: 100

#### Listing the name of the files without the name of its owner: ```ls -g```
```sh
drwxr-xr-x 3 users 4096 Apr  2  2019 backup
drwxr-xr-x 2 users 4096 Mar 23 10:58 demo
-rw------- 1 users 1679 Mar 27  2019 id_rsa
-rw-r--r-- 1 users  400 Mar 27  2019 id_rsa.pub
drwxr-xr-x 3 users 4096 Feb 16 21:42 scripting
-rwxr-xr-x 1 users  397 Feb 25 01:52 z.sh
```

#### Listing the name of files without the name of group: ```ls -lG```
```sh
drwxr-xr-x 3 akashyap 4096 Apr  2  2019 backup
drwxr-xr-x 2 akashyap 4096 Mar 23 10:58 demo
-rw------- 1 akashyap 1679 Mar 27  2019 id_rsa
-rw-r--r-- 1 akashyap  400 Mar 27  2019 id_rsa.pub
drwxr-xr-x 3 akashyap 4096 Feb 16 21:42 scripting
-rwxr-xr-x 1 akashyap  397 Feb 25 01:52 z.sh
```

#### List the size of files and folders in desired scale format: ```ls --block-size=M -l```, ```ls --block-size=K -l```
- ```--block-size=SIZE```
- K = Kilobyte
- M = Megabyte
- G = Gigabyte
- T = Terabyte
- P = Petabyte
- E = Exabyte
- Z = Zettabyte
- Y = Yottabyte

```sh
drwxr-xr-x 3 akashyap users 1M Apr  2  2019 backup
drwxr-xr-x 2 akashyap users 1M Mar 23 10:58 demo
-rw------- 1 akashyap users 1M Mar 27  2019 id_rsa
-rw-r--r-- 1 akashyap users 1M Mar 27  2019 id_rsa.pub
drwxr-xr-x 3 akashyap users 1M Feb 16 21:42 scripting
-rwxr-xr-x 1 akashyap users 1M Feb 25 01:52 z.sh
```

```sh
drwxr-xr-x 3 akashyap users 4K Apr  2  2019 backup
drwxr-xr-x 2 akashyap users 4K Mar 23 10:58 demo
-rw------- 1 akashyap users 2K Mar 27  2019 id_rsa
-rw-r--r-- 1 akashyap users 1K Mar 27  2019 id_rsa.pub
drwxr-xr-x 3 akashyap users 4K Feb 16 21:42 scripting
-rwxr-xr-x 1 akashyap users 1K Feb 25 01:52 z.sh
```

#### Show author of each file: ```ls --author -l```
```sh
drwxr-xr-x 3 akashyap users akashyap 4096 Apr  2  2019 backup
drwxr-xr-x 2 akashyap users akashyap 4096 Mar 23 10:58 demo
-rw------- 1 akashyap users akashyap 1679 Mar 27  2019 id_rsa
-rw-r--r-- 1 akashyap users akashyap  400 Mar 27  2019 id_rsa.pub
drwxr-xr-x 3 akashyap users akashyap 4096 Feb 16 21:42 scripting
-rwxr-xr-x 1 akashyap users akashyap  397 Feb 25 01:52 z.sh
```

####  Print the contents of a directory separated with comma: ```ls -m```, ```ls --format=comma``` <br>
When used in long listing format, switch -m gets useless.
```sh
backup, demo, id_rsa, id_rsa.pub, mywebproject, my_work, new-apache-project,
newport, opt, scripting, web, z.sh
```

#### Enclose your output in double quotes: ```ls -Q```
```sh
"backup"  "id_rsa.pub"    "new-apache-project"  "scripting"
"demo"    "mywebproject"  "newport"             "web"
"id_rsa"  "my_work"       "opt"                 "z.sh"
```

#### Manually assign the value of screen width and control number of columns appearing: ```ls --width [no.]```
  - ```ls --width 80```
  - ```ls --width 100```
  - ```ls --width 150```

```sh
-bash-4.2$ ls --width 50
backup      mywebproject        opt
demo        my_work             scripting
id_rsa      new-apache-project  web
id_rsa.pub  newport             z.sh
```

```sh
ls --width 80
backup  id_rsa      mywebproject  new-apache-project  opt        web
demo    id_rsa.pub  my_work       newport             scripting  z.sh
```

#### Ignoring Files: ```ls --hide```
The example below hides all the 'txt' files.
```sh
-bash-4.2$ ls
a.txt  b.doc  h.exe  i.cpp  k.txt  l.csv  r.xml  y.jsp  y.txt  z.sh

-bash-4.2$ ls --hide=*.txt
b.doc  h.exe  i.cpp  l.csv  r.xml  y.jsp  z.sh
```

#### Dired mode: ```ls -lD```
Generate output designed for Emacs' dired mode. [More information..](https://www.gnu.org/software/coreutils/manual/html_node/What-information-is-listed.html#What-information-is-listed)
```sh
-bash-4.2$ ls -lD
  total 48
  drwxr-xr-x 3 akashyap users 4096 Apr  2  2019 backup
  drwxr-xr-x 2 akashyap users 4096 Mar 24 08:27 demo
  -rw------- 1 akashyap users 1679 Mar 27  2019 id_rsa
  -rw-r--r-- 1 akashyap users  400 Mar 27  2019 id_rsa.pub
  drwxr-xr-x 5 akashyap users 4096 Mar 26  2019 mywebproject
  drwxr-xr-x 4 akashyap users 4096 Feb 16 21:31 my_work
  drwxr-xr-x 3 akashyap users 4096 Jul 15  2019 new-apache-project
  drwxr-xr-x 5 akashyap users 4096 Nov 27 00:07 newport
  drwxr-xr-x 4 akashyap users 4096 Jan 31  2019 opt
  drwxr-xr-x 3 akashyap users 4096 Feb 16 21:42 scripting
  drwxr-xr-x 4 akashyap users 4096 Feb 12  2019 web
  -rwxr-xr-x 1 akashyap users  397 Feb 25 01:52 z.sh
//DIRED// 59 65 114 118 167 173 222 232 281 293 342 349 398 416 465 472 521 524573 582 631 634 683 687
//DIRED-OPTIONS// --quoting-style=literal
```

#### Print the name of folders before directories: ```ls --group-directories-first```
```sh
-bash-4.2$ ls --group-directories-first -l
drwxr-xr-x 3 akashyap users 4096 Apr  2  2019 backup
drwxr-xr-x 2 akashyap users 4096 Mar 24 08:27 demo
drwxr-xr-x 5 akashyap users 4096 Mar 26  2019 mywebproject
drwxr-xr-x 4 akashyap users 4096 Feb 16 21:31 my_work
drwxr-xr-x 3 akashyap users 4096 Jul 15  2019 new-apache-project
drwxr-xr-x 5 akashyap users 4096 Nov 27 00:07 newport
drwxr-xr-x 4 akashyap users 4096 Jan 31  2019 opt
drwxr-xr-x 3 akashyap users 4096 Feb 16 21:42 scripting
drwxr-xr-x 4 akashyap users 4096 Feb 12  2019 web
-rw------- 1 akashyap users 1679 Mar 27  2019 id_rsa
-rw-r--r-- 1 akashyap users  400 Mar 27  2019 id_rsa.pub
-rwxr-xr-x 1 akashyap users  397 Feb 25 01:52 z.sh
```

#### List the contents of a directory with time using various time styles: ```ls -l –time-style=[STYLE]```
  - ```ls -l --time-style=full-iso```
  - ```ls -l --time-style=long-iso```
  - ```ls -l --time-style=iso```
  - ```ls -l --time-style=locale```
  - ```ls -l --time-style=+%H:%M:%S:%D```
  - ```ls --full-time```
```sh
ls -l --time-style=+%H:%M:%S:%D
drwxr-xr-x 3 akashyap users 4096 22:08:12:04/02/19 backup
drwxr-xr-x 2 akashyap users 4096 08:27:31:03/24/20 demo
-rw------- 1 akashyap users 1679 02:43:12:03/27/19 id_rsa
-rw-r--r-- 1 akashyap users  400 02:43:12:03/27/19 id_rsa.pub
drwxr-xr-x 3 akashyap users 4096 21:42:32:02/16/20 scripting
-rwxr-xr-x 1 akashyap users  397 01:52:41:02/25/20 z.sh
```

#### Include manual tab size at the contents of directory listed by ls command instead of default 8: ```ls --tabsize=[value]```
```sh
ls --tabsize=1
backup   id_rsa                                  mywebproject    new-apache-project      opt                                                     web
demo                     id_rsa.pub      my_work                                newport                                                                         scripting        z.sh

ls --tabsize=10
backup  id_rsa  mywebproject  new-apache-project  opt        web
demo    id_rsa.pub      my_work     newport         scripting  z.sh
```
####
```sh

```



## One Line Commands:

- ls command and its Aliases: ```alias ls="ls -l"```

- remove an alias previously defined: ```unalias ls```
- Show latest modification file or directory date as last: ```ls -ltr```
- Show version of ```ls``` command: ```ls --version```
- Man page for ```ls```: ```ls --help```
- list all the files within a directory including hidden files, but do not list implied ```.``` and ```..```: ```ls -A```
- control the output of ‘ls’ command to be colorful or no-color: ```ls --color=never```, ```ls --color=auto```, ```ls --color=always```
- list directory entries themselves, not their contents: ```ls -d```
- **switch (-h) output size in power of 1024:** ```ls -si``` <br>
    There exist a switch -si which is similar to switch -h. The only difference is switch -si uses power of 1000 unlike switch -h which uses the power of 1024. Like --human-readable, but use powers of 1000, not 1024.
- Listing the Contents of Home Directory: ```ls ~```
- Listing the Contents of Parent Directory: ```ls ../```
- List all the directories only using echo command: ```echo *```
- List all the directories only using echo command: ```echo */```
- Get the newest file or directory, use this command: ```ls -t | head -1```
- Get the oldest file or directory, use this command: ```ls -t | tail -1```

## Some other not so famous ```ls``` commands

   - ```-b``` also, ```--escape```	Print C-style escapes for nongraphic characters
   - ```-B``` also, ```--ignore-backups```	In directories, ignore files that end with ‘~’
   - ```-c```	With -lt:, sort by and show the ctime (time of last modification of file status information); with -l:, show ctime and sort by name; otherwise: sort by ctime, newest first.
   - ```-C```	List entries by columns.
   - ```-f```	Do not sort, enable -aU, and disable -ls --color.
   - ```-F```, ```--classify```	Append indicator (one of */=>@|) to entries.
   - ```--file-type```	Similar to ```--classify```, except do not append '*'
   - ```--format=word```	Formats according to the following:
      - across ```-x```
      - commas ```-m```
      - horizontal ```-x```
      - long ```-l```
      - single-column ```-1```
      - verbose ```-l```
      - vertical ```-C```
   - ```-I```, ```--ignore=pattern```	Do not list implied entries matching shell pattern.
   - ```-L```, ```--dereference```	When showing file information for a symbolic link, show information for the file the link references rather than for the link itself.
   - ```-N```, ```--literal```	Print raw entry names (don't treat e.g., control characters specially).
   - ```-q```, ```--hide-control-chars```	Print ? instead of non graphic characters.
   - ```--quoting-style=word```	Use quoting style word for entry names: literal, locale, shell, shell-always, c, escape.
   - Print the SELinux security context of each file: ```ls -lZ```, ```--context```


## Notes:
 - If the user you are logged in doesn’t have read permissions to the directory, you will get a message saying that ls can’t open the directory:
 ```sh
 ls /root
 ls: cannot open directory '/root': Permission denied
 ```
