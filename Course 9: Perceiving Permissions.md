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

# #Challenge 5: Executable Files

In this level, we explore execute permissions in Linux.

When trying to run a program like `/challenge/run`, it only executes if you have the appropriate permissions.

Initially, the permissions were set to `-rwxr-xr--`, allowing the owner and group to execute it, but not others.

After attempting to remove permissions with `chmod go-rwx`, I encountered a "permission denied" error. I then restored execute access using `chmod u+x` and `chmod go+x`, changing the permissions to `-r-x--x--x`.

Finally, I successfully executed the program by running `/challenge/run` and retrieved the flag.

**pwn.college{oh3oWf7PYeIaS0dEwWzK5tutOeR.dJTM2QDLxETO0czW}**

# #Challenge 6: Permission Tweaking Practice

During the completion of all 8 rounds of the permission challenges, I started by using `chmod g+w,o+w /challenge/pwn` to add write permissions for the group and others.

Next, I ran `chmod u-r /challenge/pwn` to remove the user’s read permission.

I followed this with `chmod go-w /challenge/pwn` to take away write access from the group and others.

To enable the group to execute, I used `chmod g+wx /challenge/pwn`, and then added write permissions for others with `chmod o+w /challenge/pwn`.

I removed read and write permissions for the user using `chmod u-rw,o-rw /challenge/pwn`, and then adjusted the group permissions with `chmod g-wx /challenge/pwn`.

I also added read and execute permissions for both the user and group using `chmod u+rx,g+rx /challenge/pwn`.

After completing the rounds, I changed the permissions of `/flag`, which initially had `---------` permissions, by running `chmod a+r /flag`.

Finally, I executed `cat /flag` to reveal its contents and retrieve the flag.

**pwn.college{E7K8fsCzGqXiaVSvckWXNUeTNLh.dBTM2QDLxETO0czW}**

# #Challenge 7: Permissions Setting Practice

I learned that I can use `chmod` to both add or remove permissions and overwrite them using `=`.

For example, `u=rw` sets read and write for the user, while `o=x` only allows execution for others.

By chaining commands with commas, like `chmod u=rw,g=r`, I could set different permissions for the user and group at the same time.

I also used `-` to clear permissions completely.

In an 8-round challenge, I adjusted file permissions to meet specific requirements for the user, group, and others.

After completing all rounds, I used `chmod u=r` on the `/flag` file to grant myself read access and successfully read the file.

**pwn.college{0YeLnvQmIdRtEHOkqExMIXft9fx.dNTM5QDLxETO0czW}**

# #Challenge 8: The SUID Bit

Non-root users often need elevated access for certain system tasks, but admins can't always provide passwords for actions restricted to root or sudoers.

The "Set User ID" (SUID) permission bit allows users to execute a program as the owner of that program's file, enabling tools like `su` and `sudo`.

For example, the command `chmod u+s /challenge/getroot` sets the SUID bit, allowing the program to run as root.

However, caution is essential, as granting SUID to an executable owned by root can pose security risks.

In this challenge, successfully setting the SUID bit with `/challenge/getroot` provides access to the flag.

**pwn.college{IeRtxQ7Kip1Rse7GzrrWQx_Cv_y.dNTM2QDLxETO0czW}**
