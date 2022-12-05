1. List column wise output with `ls` command: `ll | awk '{print $9}'`
2. List all directories only:
  - `ll | awk '{print $1}' | grep 'd'`
  - `ls -ld */`
  - `ls -al | grep '^d'` - sort with first letter starting is `d`
3. List all links only:
  - `ls -la | grep "\->"`
  - `ls -al | grep '^l'`
4. List all files only:
  - `ls -p | grep -v /` - Using `ls -p` tells ls to append a slash to entries which are a directory, and using `grep -v /` tells grep to return only lines not containing a slash.
  - `ls -al | grep '^-'` - sort with first letter starting is `-` 
