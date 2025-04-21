To look at whats inside the files we can cat the contents of the files.
Doing this on an image showed a lot of stuff
Using md5sum lets us check the hash and compare the hash against what should be expected. I think this is checksums

Quickly:
img_stat: 
mmls: get layout
fstat: using offset lets us look into the disk image file system
fls: lists the files within a given partition (in root by default) can provide inode to look into directories.


[img_stat]():
```
img_stat disk.flag.img
IMAGE FILE INFORMATION
--------------------------------------------
Image Type: raw

Size in bytes: 314572800
Sector size:	512
```
Give it an image and it prints out information about the file.

[mmls]()
```
mmls disk.flag.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000360447   0000153600   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000360448   0000614399   0000253952   Linux (0x83)
```
Then we can run mmls to see more information about the partitions of the image. Lets us see the start point of the partitions we might want to analyze

In this example I think we want to look at the linux partitions that we have
This is a physical disk image and not a logical one because then mmls would give us an error
TODO: Look into physical vs logical disk image

We can focus on the start (the offset) to continue to look into it

[fstat]()

```shell
fsstat -o <offset> <image_name>
```

NOTE: This is a very small amount of the information that was given.
```
fsstat -o 2048  disk.flag.img
FILE SYSTEM INFORMATION
--------------------------------------------
File System Type: Ext4
Volume Name:
Volume ID: 8e023955b4e7dab7e04b7643076ccf0f

Last Written at: 2021-09-29 14:10:02 (EDT)
Last Checked at: 2021-09-29 11:57:16 (EDT)

Last Mounted at: 2021-09-29 14:06:00 (EDT)
Unmounted properly
Last mounted on: /mnt/boot

Source OS: Linux
Dynamic Structure
Compat Features: Journal, Ext Attributes, Resize Inode, Dir Index
InCompat Features: Filetype, Extents, Flexible Block Groups,
Read Only Compat Features: Sparse Super, Large File, Huge File, Extra Inode Size

Journal ID: 00
Journal Inode: 8
```

directories are labeled with d/d
Next we want to be looking at the directories

[fls]()
lists files in the root directory of the partition of the disk image.
If we are looking into a physical disk image we have to give the offset. If it is logical then we do not need to.

This can let us look at the directories that are in the image.
```
fls -o <offset> <image_name> <inode_to_look_at>
```

mactime formate is what a lot of other tools look at for inputs.

-r: recurses through directories on the image. Shows us all the files and folders in the entire disk.

##### [icat](https://www.sleuthkit.org/sleuthkit/man/icat.html)
Prints the content of a file in an image (if it can be) to the stdout. This is accessed via the inode number.

##### [srch_strings](https://manpages.debian.org/jessie/sleuthkit/srch_strings.1)
Prints the contents of text files in the image.
```
srch_strings -o 2048 dds1-alpine.flag.img
```

##### [blkls](https://www.sleuthkit.org/sleuthkit/man/blkls.html)
Not completely sure what this does.
I used the following code to get the slack space from an image to print out a flag.
```bash
blkls -s <image-name> 
```