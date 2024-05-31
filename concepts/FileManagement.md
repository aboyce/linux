## File Management

If you want to assign something to root, you have to be root.

### `ls`

You can list other directories with `ls /path/to/directory`.

To see the latest file, at the bottom (closest to the terminal) you can use `ls -ltr` (long list formatting, sort by time, in reverse). The reverse is useful if you have more files than the screen can show.

The long list (`-l`) formatting shows you:

- Type of file (if it's a file, directory, or link)
- Permissions
- Number of links
- Owner
- Group
- Size
- Created month
- Created day
- Created time
- Name

### `chown`

Used to change the owner, you pass the `owner` and then the `filename`.

```bash
chown root file
```

You can also change the group if you pass it `owner:group`.

```bash
chown root:root file
```

### `chgrp`

Used to change the group, you pass the `group` and then the `filename`.

```bash
chgrp root file
```

### Soft and Hard Link

`inode` is pointer/number of a file on the hard disk. When you create a file, it is assigned a number and this is what the OS uses.

To see the `inode` with `ls`, you want to pass `-i`, for example; `ls -ltri`.

To create links use:

```bash
# create a hard link
ln

# create a soft link
ln -s
```

#### Soft Link

A soft link is a pointer to the original file, which is then a pointer to the `inode`.

It will be removed if the original file is removed or renamed. When you `ls -i` the link and the original file has been removed, it will be 'red' or invalid. The link will remain, but it will be pointing to an invalid location.

Any edits to the soft linked file, will update the original file.

Soft links will have a different `inode`, this is because the `idnode` is of the link itself, not the actual file it points to, it is like a Windows shortcut.

To create a soft link (called the same thing), i.e. a shortcut to a file, go to that directory and create a link.

```bash

cd /tmp
ln -s /path/to/file

# you will then have a link called `file`, that points to `file`
```

#### Hard Link

A hard link is a pointer to the underlying `inode.`

Deleting, renaming or moving the original file will not affect the hard link. The hard link is itself a pointer to that underlying data.

They will only work within the same partition.