# #Challenge 1: The Root

An absolute path has a specific format that begins at the root directory, represented by a leading slash `/`. It provides the complete location of a file or directory in the filesystem.

In this challenge, I learned about the root directory and how to access it using an absolute path. For instance, typing `/pwn` allowed me to enter the pwn directory directly from the root.

**pwn.college{MXxYuFypoAls48Dy5WPKxoAnhbn.dhzN5QDLxETO0czW}**

# #Challenge 2: Program and Absolute Paths

Here I learned more about absolute paths and its usage by typing `/challenge/run`, which is the complete path I used to access the command.

**pwn.college{Md-50E1GZbcnTgKs2r0WK8rYLf_.dVDN1QDLxETO0czW}**

# #Challenge 3: Position thy self

I started in the `/challenge` directory and ran `/challenge/run`, but it failed because I wasn't in the correct location. I then changed to the `/proc/201` directory using `cd`. Once there, I successfully executed `/challenge/run`, which provided the flag.

I learned about the importance of the `~` symbol, the main directory.

**pwn.college{IIiqWP9tzIRDwoh5FvDAz40S_oJ.dZDN1QDLxETO0czW}**

# #Challenge 4: Position elsewhere

I began in the `/challenge` directory and attempted to run `/challenge/run`, but it failed because I wasn't in the correct directory. I then navigated to `/tmp` using the `cd` command. After that, I executed `/challenge/run` again, which succeeded and revealed the flag.

**pwn.college{s_1m60ViM0SWYlskoVtJjoEY5A3.ddDN1QDLxETO0czW}**

# #Challenge 5: Position yet elsewhere

I attempted to run the command `/challenge/run` but received an error stating that I was not in the required directory, `/sys/kernel`. This prompted me to use the `cd` command to change my location. After navigating to the correct directory, `/sys/kernel`, I successfully executed `/challenge/run`.

All the above 3 challenges reinforced the importance of being in the right directory when working with absolute paths in the command line. Ultimately, I learned that precise navigation is essential for executing commands correctly and obtaining the desired output, such as flags.

**pwn.college{YZE4CzpbWTT9WCmlblERaNca0UH.dhDN1QDLxETO0czW}**

# #Challenge 6: implicit relative paths, from /

Starting from the root directory `/`, I navigated there by using the command `cd /`. Then, I successfully invoked the flag file by typing `challenge/run`. 

This experience helped me understand the concept of relative paths.

Relative paths  basically they do not start from the home directory; they start from the current working directory.

**pwn.college{M0ltIF7e_V4OJQzgSs8ASV0LJIv.dlDN1QDLxETO0czW}**

# #Challenge 7: explicit relative paths, from /

After explicitly navigating to the root directory with `cd /`, I executed `./challenge/run` to invoke the flag file. 

This demonstrated the use of an explicit relative path, as I was able to successfully run the command from the correct directory.

**pwn.college{AuocKNc3UuXeq-3aujo7lA0jDZG.dBTN1QDLxETO0czW}**

# #Challenge 8: implicit relative path

By changing to the `/challenge` directory with `cd /challenge`, I attempted to execute `run`, which resulted in a "command not found" error. However, when I used `./run`, I successfully invoked the flag file. 

This illustrates the use of an implicit relative path, as the command was executed from the correct directory.

**pwn.college{wjX9ijXMZHyZgwv1GeukESZlCqj.dFTN1QDLxETO0czW}**

# #Challenge 9: home sweet home

When I attempted to run `/challenge/run` without any arguments, I received a message indicating that an argument was required. Then, I tried to access `~/f`, but encountered a "Permission denied" error. 

However, invoking `/challenge/run ~/f` successfully created a file at that location and read it back to me, revealing the flag.

I also learnt that `~` serves as a shorthand for the path `/home/hacker`.

**pwn.college{MyRGfmNOvXvCWk3HJyFbhvW9CB3.dNzM4QDLxETO0czW**
