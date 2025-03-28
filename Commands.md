[CyberChef](https://gchq.github.io/CyberChef/) can be used to decode various forms of encoded data.

ROT13: 

[ssh](https://linux.die.net/man/1/ssh): 
Opens a secure shell to a user in a node
```
ssh <username>@<ip-addr>:<port>
```

[net cat](https://linux.die.net/man/1/nc): 
Can do so much stuff, have to look up uses
```
nc <destination> <port>
ex: nc jupiter.challenges.picoctf.org 64287
```

[chmod](https://linux.die.net/man/1/chmod): 
Updated permissions of a file
```bash
chmod <permission-levels> <file>
	ex: chmod 766 warm
	4 = r, 2 = w, 1 = x
```

[strings](https://linux.die.net/man/1/strings): 
Prints all printable strings in a file
```bash
strings <filename>
ex: strings strings.txt
```

[netstat](https://linux.die.net/man/8/netstat):  ```netstat```

[bvi](https://linux.die.net/man/1/bvi):
opens a visual editor for binary files. 
(could have been useful when trying to edit the pokemon yellow memory)

[rm](): 
remove files
```bash
removing all files in a directory
	rm -r /path/to/directory/*
```

[unzip]():
unzips a file into a folder of the same name -.zip unless specified

[find](https://linux.die.net/man/1/find):
Allows you to look at each file and evaluate it using an expression. Honestly Im not clear on how this works and what it does. An example is here [Big Zip][[2025-03-16#[Big Zip](https //play.picoctf.org/playlists/18?m=166)].
```bash
find <path> <expression>
find . -name thisfile.txt
```

[wget](https://www.gnu.org/software/wget/):
wget allows downloading of a resource at a uri.
```shell
wget <file-name>
```

field:
TODO: Add notes about this but this is so cool.
https://www.youtube.com/shorts/0Z71je-X6YM

[file](https://linux.die.net/man/1/file):
Print information about the file
```shell
file <file-name>
```

[mmls](https://wiki.sleuthkit.org/index.php?title=Mmls)
Part of SleuthKit

[gzip/gunzip](https://linux.die.net/man/1/gunzip)
Allows for compressing and decompressing files.