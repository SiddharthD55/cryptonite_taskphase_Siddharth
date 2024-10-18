# #Challenge 1: Becoming root with su

In this challenge, I explored the `su` (switch user) command, a traditional, old utility used to elevate privileges in Linux, which runs as root due to its SUID bit.

I began by using the command `su`, which prompted me for the root password. After entering the correct password, "hack-the-planet," I successfully switched to the root user.

With root access, I then used the command `cat /flag` to retrieve the flag, demonstrating how `su` can grant administrative privileges when the correct credentials are supplied.

**pwn.college{wLM9XhC4YntuyKiCozUjCn4CGs6.dVTN0UDLxETO0czW}**

# #Challenge 2: Other users with su

With no arguments, the `su` command will start a root shell after authenticating with the root password.

However, I can also specify a username as an argument to switch to that user instead of root.

For example, when I used the command `su zardus` and entered the password "dont-hack-me," I successfully switched to the Zardus account.

From there, I executed `/challenge/run` and received the flag.

**pwn.college{AfCGScKVQejcrif6wdTRc8D2Sa2.dZTN0UDLxETO0czW}**

# #Challenge 3: Cracking passwords

When entering a password for the `su` command, it compares the input against the stored password in `/etc/shadow`, which securely holds hashed passwords to prevent unauthorized access.

This file is only readable by root, but if it gets leaked; such as through unprotected backups; hackers can use tools like John the Ripper to crack the password hashes.

In this case, I ran the command `john /challenge/shadow-leak` on a leaked shadow file and successfully cracked Zardus's password, revealing "aardvark."

After using this password with `su zardus`, I switched to the Zardus account and executed the command `/challenge/run`, receiving the flag.

**pwn.college{w9ldLl4IsVUfjENAPoaiCy34jL4.ddTN0UDLxETO0czW}**

# #Challenge 4: Using sudo

Historically, Linux systems relied on root passwords for administrators to access root privileges via the `su` command, but this approach proved cumbersome and vulnerable, especially in larger setups.

To enhance security and streamline management, the shift to `sudo` (superuser do) emerged, allowing users to run specific commands as root without needing to switch users entirely.

Unlike `su`, which demands the root password, `sudo` uses rules defined in the `/etc/sudoers` file to determine whether a user is authorized for certain actions.

I utilized this modern approach by executing `sudo cat /flag`, which allowed me to access sensitive data and successfully retrieve the flag.

**pwn.college{UZYqPzeZgQ96lpes5E7SZRbxGdk.dhTN0UDLxETO0czW}**
