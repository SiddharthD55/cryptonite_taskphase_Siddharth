# #Challenge 1: cat: not the pet, but the command!

By using the command `cd ~`, I navigated to my home directory. Then, I executed `cat flag` to display the contents of the file, revealing the fla.

Basically, I saw that the `cat` command is primarily utilized for displaying the contents of files. It can also concatenate multiple files and output their combined content.

**pwn.college{w2OGxYErZ_EzF_qKWmgHOZbZIm8.dFzN1QDLxETO0czW}**

# #Challenge 2: catting absolute paths

Using the `cat` command with the file path `/flag`, basically `cat /flag` retrieves and displays the contents of the flag.

Here we are using the `cat` command with an absolute path, `/flag`.

**pwn.college{INcylYXeJjEkjp4M5uOZ1jp4wR0.dlTM5QDLxETO0czW}**

# #Challenge 3: more catting practice

Executing the `cat` command on the file located at `/usr/lib/jvm/flag` displays its contents.

**pwn.college{8nHb1OV0pSUDzxx_r98XTqg9APU.dBjM5QDLxETO0czW}**

# #Challenge 4: grepping for a needle in a haystack

When dealing with large files, using the `cat` command can be overwhelming. Fortunately, the `grep` command allows you to efficiently search for specific content within those files, helping you find what you need without having to sift through all the data.

Using the `grep` command to search for the string `"pwn.college"` (as any flag starts with this string) in the file `/challenge/data.txt` returns the flag.

**pwn.college{YtbwVqxfbqP0vcAkEnkVa-fhmSQ.ddTM4QDLxETO0czW}**

# #Challenge 5: listing files

We can list all the files in a folder or directory by using the `ls` command.

Upon listing the contents of the `/challenge` directory, I discovered a file named `7170-renamed-run-24146`, basically inputted `ls /challenge`. When I executed it, I was greeted with a message: `"Yahaha, you found me! Here is your flag."`.

**pwn.college{8pOg8EEvg4HvBJAEy8VrsvfLkDr.dhjM4QDLxETO0czW}**

# #Challenge 6: touching files

We can create files as well in our desired directory using the `touch` command.

I created two empty files using the touch command: one named `pwn` in the `/tmp` directory and another named `college`, using the commands `touch tmp/pwn` and `touch /tmp/college`. After that, I executed `/challenge/run`, which returned a message confirming success along with the flag.

**pwn.college{03e4O_xulorKdxtd3nWTns6Z8ah.dBzM4QDLxETO0czW}**

# #Challenge 7: removing files

We can remove files using the `rm` command.

I returned to my home directory using the `cd` command and then removed the file `delete_me` with the `rm` command, basically `rm delete_me`. Upon running `/challenge/check`, I received a message confirming the successful deletion along with the flag.

**pwn.college{cmAi3r41g1KUX4_yfjlEkfAy1YG.dZTOwUDLxETO0czW}**

# #Challenge 8: hidden files

`ls` cannot list all the files when executed, as there are some hidden files in the folder as well. To see the hidden files, we can use the `-a` command, basically `ls -a`.

I navigated to the root directory using `cd /` and listed all files, including hidden ones, with `ls -a`. Among the files, I found `.flag-13623033019940`. I then used the `cat` command, `cat .flag-13623033019940` to read its contents.

**pwn.college{YzenD-xd9L8BOHkh4qI12dxjlrm.dBTN4QDLxETO0czW}**

# #Challenge 9: An Epic Filesystem Quest

Here I was going into many, many directories, first using `cd` and `ls -a`, then just using `cat`, and then finding the flag.



# #Challenge 10: making directories

We can make new directories using `mkdir` command, with syntax `mkdir <new_directory>`.

I created a directory named `pwn` in the `/tmp` location using the command `mkdir /tmp/pwn`. After that, I navigated into the new directory with `cd /tmp/pwn`. 

Next, I created a file called college by running the command `touch college`. Finally, I executed the command `/challenge/run`, which successfully returned my flag.

**pwn.college{cahXKO-gDmZ23bkvSOBkyslnPF9.dFzM4QDLxETO0czW}**

# #Challenge 11: finding files

We can use the `find` command to find the file.

Here I first navigated into the main directory using `cd ~`. Then I ran the `find find / -name flag` command and found some files where permission was denied, as well as some files and directories with the 'flag' at the end of the address.

Finally on seeing one directory, I found it. I had to use `cat` command to read it , and it was trial and error.

**pwn.college{AA6eDGyYZy6CqjuwtnVwEpib4me.dJzM4QDLxETO0czW}**

# #Challenge 12: linking files

Here, we needed to create a 'symbiotic link' using `ln -s /flag /home/hacker/not-the-flag` and then executed `/challenge/catflag` and got the flag.

**pwn.college{MSnDGkwoMFNiDy1IkDp9XtXafSM.dlTM1UDLxETO0czW}**

