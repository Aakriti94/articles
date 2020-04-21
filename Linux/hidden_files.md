# Hidden files in BASH

## What are the Hidden files?
  - Dot-files refers to files/directories with a ```.``` prepended to their name.
  - They are hidden files.
  - They are traditionally used to store settings, preferences.
  - It works anywhere, but its primary use is to hide configuration files in your home directory

## The history of hidden files
The hidden files are shortcuts. The story begins many years ago when the first file systems were created on UNIX. To allow easy navigation, a single file with a dot ```.``` was added to each directory. Secondly, a double dot file ```..``` was added to easily move up in the directory structure. As these files had no real data in them, a quick hack was added to the ls binary.

## Why are hidden files hidden?
No, hidden files are not bad. They are hidden to declutter your system.

## Contents
| Options                                                 | command |
| :-------	                                              |   :--   |
|[The single dot-file](https://github.com/Aakriti94/articles/blob/master/Linux/hidden_files.md#the-single-dot-file-)|```.```|
|[The double dot-file](https://github.com/Aakriti94/articles/blob/master/Linux/hidden_files.md#the-double-dot-file-)|```..```|
|[Show hidden files and folders](https://github.com/Aakriti94/articles/blob/master/Linux/hidden_files.md#show-hidden-files-and-folders-ls--a)|```ls -a```|
|[Show hidden files and folders without the ```.``` and ```..``` files](https://github.com/Aakriti94/articles/blob/master/Linux/hidden_files.md#show-hidden-files-and-folders-without-the--and--files-ls--a)|```ls -A```|
|[Create hidden files and folders](https://github.com/Aakriti94/articles/blob/master/Linux/hidden_files.md#create-hidden-files-and-folders)|```cat > .hidden-file```|
|[Hide existing file](https://github.com/Aakriti94/articles/blob/master/Linux/hidden_files.md#hide-existing-file)| |
|[Copy hidden files](https://github.com/Aakriti94/articles/blob/master/Linux/hidden_files.md#copy-hidden-files)||
|[Find And List All Hidden Files Recursively](https://github.com/Aakriti94/articles/blob/master/Linux/hidden_files.md#find-and-list-all-hidden-files-recursively-ls--lra)|```ls -lRa```|
|[List only hidden files and directory](https://github.com/Aakriti94/articles/blob/master/Linux/hidden_files.md#list-only-hidden-files-and-directory-ls--ld-)|```ls -ld .*```|



## Options:

#### [The single dot-file:](https://github.com/Aakriti94/articles/blob/master/Linux/cd.md#the-working-directory-cd-) ```.```
Location, location, location. It means **this directory.**
```sh
-bash-4.2$ pwd
/cos/home3/akashyap
-bash-4.2$ cd ./
-bash-4.2$ pwd
/cos/home3/akashyap
```

#### [The double dot-file:](https://github.com/Aakriti94/articles/blob/master/Linux/cd.md#change-to-the-parent-of-the-current-directory-cd-) ```..```
It means the directory immediately above the current one.
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

#### [Show hidden files and folders](https://github.com/Aakriti94/articles/blob/master/Linux/ls.md#show-hidden-files-and-folders-ls--a-): ```ls -a```
```sh
bash-4.2$ ls -a
.              .cache   id_rsa.pub    new-apache-project  .ssh
..             .config  .lesshst      newport             .viminfo
backup         .gnome2  mywebproject  opt                 web
.bash_history  id_rsa   my_work       scripting           z.sh
```
#### [Show hidden files and folders without the ```.``` and ```..``` files](https://github.com/Aakriti94/articles/blob/master/Linux/ls.md#show-hidden-files-without-the--and--file-ls--a): ```ls -A```
We can see in the below example that all the hidden files are visible except the ```.``` and ```..``` files.
```sh
-bash-4.2$ ls -A
backup         .cache   id_rsa        new-apache-project  scripting
.bash_aliases  .config  id_rsa.pub    new_dir             .ssh
.bash_history  demo     .lesshst      newport             .viminfo
.bash_profile  found    mywebproject  not                 web
.bashrc        .gnome2  my_work       opt                 z.sh
```

#### Create hidden files and folders:
Hidden files and folders are made the same way as the normal file/folder, just add a ```.``` in front of their name to make them hidden.
```sh
-bash-4.2$ cat > .hidden-file
-bash-4.2$ ls -la
-rw-r--r--   1 akashyap users     0 Apr 18 21:17 .hidden-file
-bash-4.2$ mkdir .hidden-folder
```

#### Hide existing file:
To change a regular file to hidden file, we would simply use the ```mv``` command.
```sh
-bash-4.2$ mv normal-file .normal-file
-bash-4.2$ ls -la
-rw-r--r--   1 akashyap users     0 Apr 18 21:20 .normal-file
```

#### Copy hidden files:
To copy hidden files, copy them using the regular manner with placing a ```.``` in front of their names.
```sh
cp .normal-file .normal-file2
cp .* demo/
```

#### Find And List All Hidden Files Recursively: ```ls -lRa```
```sh
-bash-4.2$ ll -Ra /cos/home3/akashyap/demo/
/cos/home3/akashyap/demo/:
total 32
drwxr-xr-x  3 akashyap users  4096 Apr 19 02:44 .
drwx------ 19 akashyap users  4096 Apr 19 02:36 ..
-rw-r--r--  1 akashyap users     0 Mar 23 10:57 a.txt
-rw-r--r--  1 akashyap users    18 Apr 18 23:40 .bash_aliases
-rw-r--r--  1 akashyap users     0 Apr 18 23:40 .bashrc
-rw-r--r--  1 akashyap users     0 Mar 23 10:58 b.doc
-rw-------  1 akashyap users    35 Apr 18 23:40 .lesshst
-rw-------  1 akashyap users  5656 Apr 18 23:40 .viminfo
-rw-r--r--  1 akashyap users     0 Mar 24 08:27 y.txt
-rw-r--r--  1 akashyap users     0 Mar 23 10:57 z.sh

/cos/home3/akashyap/demo/xyz:
total 8
drwxr-xr-x 2 akashyap users 4096 Apr 19 02:44 .
drwxr-xr-x 3 akashyap users 4096 Apr 19 02:44 ..
-rw-r--r-- 1 akashyap users    0 Apr 19 02:44 .file1
-rw-r--r-- 1 akashyap users    0 Apr 19 02:44 .file2
```

#### [List only hidden files and directory](https://github.com/Aakriti94/articles/blob/master/Linux/ls.md#list-only-directories-ls--ld-): ```ls -ld .*```
```sh
-bash-4.2$ ll -a
total 28
drwxr-xr-x  2 akashyap users  4096 Apr 18 23:40 .
drwx------ 19 akashyap users  4096 Apr 19 02:36 ..
-rw-r--r--  1 akashyap users     0 Mar 23 10:57 a.txt
-rw-r--r--  1 akashyap users    18 Apr 18 23:40 .bash_aliases
-rw-------  1 akashyap users 10640 Apr 18 23:40 .bash_history
-rw-r--r--  1 akashyap users    14 Apr 18 23:40 .bash_profile
-rw-r--r--  1 akashyap users     0 Apr 18 23:40 .bashrc
-rw-r--r--  1 akashyap users     0 Mar 23 10:58 b.doc
-rw-r--r--  1 akashyap users     0 Mar 23 10:58 h.exe
-rw-------  1 akashyap users    35 Apr 18 23:40 .lesshst
-rw-r--r--  1 akashyap users     0 Mar 23 10:58 r.xml
-rw-------  1 akashyap users  5656 Apr 18 23:40 .viminfo
-rw-r--r--  1 akashyap users     0 Mar 23 10:57 z.sh


-bash-4.2$ ls -ld .*
drwxr-xr-x  2 akashyap users  4096 Apr 18 23:40 .
drwx------ 19 akashyap users  4096 Apr 19 02:36 ..
-rw-r--r--  1 akashyap users    18 Apr 18 23:40 .bash_aliases
-rw-------  1 akashyap users 10640 Apr 18 23:40 .bash_history
-rw-r--r--  1 akashyap users    14 Apr 18 23:40 .bash_profile
-rw-r--r--  1 akashyap users     0 Apr 18 23:40 .bashrc
-rw-------  1 akashyap users    35 Apr 18 23:40 .lesshst
-rw-r--r--  1 akashyap users     0 Apr 18 23:40 .normal-file
-rw-r--r--  1 akashyap users     0 Apr 18 23:40 .normal-file2
-rw-------  1 akashyap users  5656 Apr 18 23:40 .viminfo
```
