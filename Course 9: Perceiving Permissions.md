# #Challenge 1: Changing File Ownership

In Linux, every file is owned by a user, including my account and the root account, which has admin privileges. Files like `/flag` are owned by root and have restricted access, preventing unauthorized reading.

The `chown` command is used to change the ownership of a file or directory, allowing me to reassign ownership to a new user (and optionally a group). By using `chown hacker /flag`, I can change the ownership of the `/flag` file to my user account.

After this, when I run `cat /flag`, I'll be able to read its contents.

This command is typically restricted to the root user or the file's current owner, enabling me to access files I otherwise couldn't read—an essential technique for privilege escalation.

**pwn.college{4feBkY8JaFvTVvQQ9_RlbV7UaBo.dFTM2QDLxETO0czW}**

# #Challenge 2: Groups and Files

In Linux, files have both an owning user and group, allowing for effective resource access control. Users can belong to multiple groups, which is crucial for managing permissions; the `id` command shows a user's groups.

The `chgrp` command is used to change the group ownership of a file or directory, allowing me to reassign the group that owns the file.

For example, by using `chgrp hacker /flag`, I can change the group ownership of the `/flag` file to my user group.

After doing this, when I run `cat /flag`, I'll be able to access its contents, demonstrating how group ownership can enhance my ability to interact with system resources.

**pwn.college{wl7Uv1ghy5uA9fcxB81t41MT1xC.dFzNyUDLxETO0czW}**

# #Challenge 3: Fun with Groups Names

In Linux, each user typically belongs to their own group, but it's common for environments like computer labs to group all users into a shared group.

To determine which group I belong to, I can use the `id` command, which displays my user ID, group ID, and the groups I’m a member of.

After running `id`, I found that my user is part of the `grp4811` group.

I can then change the group ownership of the `/flag` file to `grp4811` using `chgrp grp4811 /flag`, allowing me to access it with `cat /flag`.

**pwn.college{YmiaF_djd__Tz4drPdz2xHi3Kbe.dJzNyUDLxETO0czW}**

# #Challenge 4: Changing Permissions

In Linux, file permissions control access and are represented by a string of ten characters, where the first indicates the file type and the next nine specify read, write, and execute permissions for the owner, group, and others.

For example, `rw-r--r--` allows the owner to read and write, while the group and others can only read.

Using the `chmod` command, I can modify permissions; after initially failing with `chmod u+r /flag`, I successfully used `chmod go+rwx /flag`, which grants the group and others read, write, and execute permissions, allowing me to access the file with `cat /flag`.

**pwn.college{cVZhWE7eCGVodAO--9Fl3wfUDVE.dNzNyUDLxETO0czW}**
