## UID: 305751602

(IMPORTANT: Only replace the above numbers with your true UID, do not modify spacing and newlines, otherwise your tarfile might not be created correctly)

# Hey! I'm Filing Here

This program creates a standard example of the EXT2 file system.

## Building

To build the program, navigate to the directory containing the source files and run 
`make`.

You can then use `./ext2-create` to create the image.

## Running

Running `./ext2-create` creates the base image.

You can then create a directory to mount your filesystem to by running

`mkdir mnt`

and replacing "mnt" with your desired name.

Mounting your filesystem can be done with the command

`sudo mount -o loop cs111 -base.img mnt`

once again you should "mnt" with the name of the directory you wish to mount in.

you can then test the contents of this filesystem by running

```
cd mnt

ls -ain
```

The output should look like

```
total 7
     2 drwxr-xr-x 3    0    0 1024 Mar 18 04:28 .
942008 drwxr-xr-x 5 1000 1000 4096 Mar 18 04:34 ..
    13 lrw-r--r-- 1 1000 1000   11 Mar 18 04:28 hello -> hello-world
    12 -rw-r--r-- 1 1000 1000   12 Mar 18 04:28 hello-world
    11 drwxr-xr-x 2    0    0 1024 Mar 18 04:28 lost+found
```
## Cleaning up

To unmount your file system you should run

`sudo umount mnt`

and then use

`rmdir mnt`

to remove the directory after you are done with it

To clean up all the files you may use the makefile command
```
make clean
```
inside the working directory.

