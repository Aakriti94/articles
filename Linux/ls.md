# LS Command

## What is the ls command?
The ```ls``` command lists the contents of a directory.
<br>

## Syntax
```
ls [OPTIONS] [FILES]
```

## Options

##### Show the contents of a directory:
This will list the contents of the directory in alphabetical order.
```
-bash-4.2$ ls
backup  id_rsa.pub    my_work             newport  scripting  z.sh
id_rsa  mywebproject  new-apache-project  opt      web

```
<br>

##### Show hidden files and folders: ```ls -a ```
```
-bash-4.2$ ls -a
.              .cache   id_rsa.pub    new-apache-project  .ssh
..             .config  .lesshst      newport             .viminfo
backup         .gnome2  mywebproject  opt                 web
.bash_history  id_rsa   my_work       scripting           z.sh

```
<br>

**Show a long listing:** ```ls -l```
```
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
<br>

**Sort by size:** ```ls -S```, ```ls -lS``` <br>
 In the following example this is combined with the -l option to show a long listing.
```
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
<br>

**Sort by modification time:** ```ls -lt```
```
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
To show the last edited file in a directory the ls command can be combined with head:
```
ls -t | head -n 1
z.sh
```
<br>

**Show file size in human readable format:** ```ls -lh```
```
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
<br>

**Display one file or folder per line:** ```ls -1```
```
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
<br>

**Show a recursive listing:** ```ls -R```
```
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





















<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>

<!-------------------------Read More------------------------------->

**Append file types to listings:** To append an indicator of the file type to a directory listing pass the -F option.
The following characters are appended based on this option:

- / indicates a directory
- @ indicates a symbolic link
- | indicates a FIFO
- = indicates a socket
- > indicates a door
- nothing is shown for regular files
https://shapeshed.com/unix-ls/

------------------------------------------------------------------------------------------

**Sort by access time:** ```ls -lu``` <br>
This causes the output to show the most recently accessed files of folders at the top of the listing.
