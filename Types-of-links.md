# Types of Links

# What is a link?

- Links are pointers pointing to a file or a directory.

# Why do we need Links?

- Some programs required a particular version of a library.
- When a library upgrade replaced the old version, the program would crash with an error specifying the name of the old, now-missing library.
- Usually, the only change in the library name was the version number.
- I simply added a link to the new library but named the link after the old library name.
- In fact, almost all applications are linked to libraries using a generic name with only a major version number in the link name, while the link points to the actual library file that also has a minor version number.  Eg: `cd` command have its binaries at the location `location` and whenever we use `cd` command in a script, the binaries are loaded from the location.
- In other instances, required files have been moved from one directory to another to comply with the Linux file specification, and there are links in the old directories for backward compatibility with those programs that have not yet caught up with the new locations. If you do a long listing of the /lib64 directory, you can find many examples of both.

```bash
A few of the links in the /lib64 directory
lrwxrwxrwx   1 root root       23 Apr 11 16:33 libanl.so -> ../../lib64/libanl.so.1
lrwxrwxrwx.  1 root root       15 Jan  7  2020 libXft.so.2 -> libXft.so.2.3.2
lrwxrwxrwx   1 root root       10 Apr 11 16:29 ld-linux-x86-64.so.2 -> ld-2.17.so
lrwxrwxrwx   1 root root       20 Apr 11 16:34 ld-lsb-x86-64.so -> ld-linux-x86-64.so.2
lrwxrwxrwx.  1 root root       20 Jan  7  2020 ld-lsb-x86-64.so.3 -> ld-linux-x86-64.so.2
```

The long listing of the /lib64 directory above shows that the first character in the file mode is the letter "l," which means that each is a soft or symbolic link.

## TL;DR

- Linking libraries
- Making sure files are in constant locations (without having to move the original)
- Keeping a “copy” of a single file in multiple locations

# Links Types

## **There are two types of links:**

Symbolic links are not updated (they merely contain a string which is the pathname of its target); hard links always refer to the source, even if moved or removed. 

For example, if we have a file a.txt. If we create a hard link to the file and then delete the file, we can still access the file using hard link. But if we create a soft link of the file and then delete the file, we can’t access the file through soft link and soft link becomes dangling. Basically hard link increases reference count of a location while soft links work as a shortcut (like in Windows)

They both provide multiple directory entries (or references) to a single file. Links are powerful and add flexibility to Linux file systems because everything is a file.

A symbolic or soft link is an actual link to the original file, whereas a hard link is a mirror copy of the original file. If you delete the original file, the soft link has no value, because it points to a non-existent file. But in the case of hard link, it is entirely opposite. Even if you delete the original file, the hard link will still has the data of the original file. Because hard link acts as a mirror copy of the original file.

## **Hard links**

- You can think of a hard link as an additional name for an existing file.
- Hard links are associating two or more file names with the same inode. You can create one or more hard links for a single file.
- Each file has one inode that contains information about that file, including the location of the data belonging to that file.
- Because all the hard links point to the single inode that contains the metadata about the file, all of these attributes are parts of the file, such as ownership, permissions, and the total number of hard links to the inode, and cannot be different for each hard link. It is one file with one set of attributes. The only attribute that can be different is the file name, which is not contained in the inode. Hard links to a single file/inode located in the same directory must have different names, due to the fact that there can be no duplicate file names within a single directory.
- Hard links share the same data blocks on the hard disk, while they continue to behave as independent files.
- Hard links cannot be created for directories and files on a different file system or partition.
- They are the low-level links. It links more than one filename with the same Inode and it represents the physical location of a file. When a hard link is created for a file, it directly points to the Inode of the original file in the disk space, which means no new Inode is created. Directories are not created using hard links and they can not cross filesystem boundaries. When the source file is removed or moved, then hard links are not affected.
- Links have actual file contents
- Removing any link, just reduces the link count, but doesn’t affect other links.
- you can only link to files (and not directories); We cannot create a hard link for a directory to avoid recursive loops.
- Command to create a hard link is:

```bash
ln  [original filename] [link name]
```

- Hard links can not cross filesystem boundaries. There is an immediate disadvantage: hard links can't span partitions, because inode numbers are only unique within a given partition. Hard links are limited to files contained within a single filesystem. This is because inode numbers are unique only within each filesystem, and a different filesystem, for example, /var or /opt, will have inodes with the same number as the inode for our file.
- The number of hard links for a file is displayed with the `ls -l` command. If you want to display the actual inode numbers, the command `ls -li` does that.
- Has the same inode number and permissions of the original file, and permissions will be updated if we change the permissions of the source file,

## **Soft links**

A soft link is something like a shortcut in Windows. It is an indirect pointer to a file or directory. Unlike a hard link, a symbolic link can point to a file or a directory on a different filesystem or partition.

- Soft links are very common. It represents a virtual or abstract location of the file. A soft link doesn't contain any information or content of the linked file, instead, it has a pointer to the location of the linked file. In other words, a new file is created with a new Inode, having a pointer to the Inode location of the original file.
- Each soft linked file contains a separate Inode value that points to the original file. As similar to hard links, any changes to the data in either file is reflected in the other. Soft links can be linked across different file systems, although if the original file is deleted or moved, the soft linked file will not work correctly (called hanging link).
- `ls -l` command shows all links with first column value l? and the link points to original file.
- Soft Link contains the path for original file and not the contents.
- Removing soft link doesn’t affect anything but removing original file, the link becomes “dangling” link which points to nonexistent file.
- A soft link can link to a directory.
- Link across filesystems: If you want to link files across the filesystems, you can only use symlinks/soft links.
- can cross the file system,
- allows you to link between directories,
- has different inode number and file permissions than original file,
- permissions will not be updated,
- has only the path of the original file, not the contents.
- Command to create a Soft link is:

    ```bash
    $ ln  -s [original filename] [link name]
    ```

- Note that removing the target file for a symbolic link makes the link useless.
- Because soft links point to a hard link for the file and not the inode, they are not dependent upon the inode number and can work across filesystems, spanning partitions and LVs.
- The downside to this is: If the hard link to which the symlink points is deleted or renamed, the symlink is broken. The symlink is still there, but it points to a hard link that no longer exists. Fortunately, the `ls` command highlights broken links with flashing white text on a red background in a long listing.

## Difference between HARD and SOFT Links
| HARD Link  | SOFT Links  | 
|---|---|
| Target must exist  | Target may already exist, but does not have to  |   
| Allowed within file systems only  | Allowed between different file systems  | 
| Links directly to the place the file is stored  | Links to the entry in the file system table (node)  |  
| Removing the link means removing the whole file | Removing the link means removing the link to the node, not the file itself |
| point directly to the inode belonging to the file | soft links point to a directory entry, i.e., one of the hard links. |

# Lab project: experimenting with links

[A user's guide to links in the Linux filesystem](https://opensource.com/article/17/6/linking-linux-filesystem)

# Reference:

[Explaining Soft Link And Hard Link In Linux With Examples - OSTechNix](https://www.ostechnix.com/explaining-soft-link-and-hard-link-in-linux-with-examples/)
