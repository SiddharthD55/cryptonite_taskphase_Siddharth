# #Challenge 1: Learning from Documentation

To obtain the flag, I ran the command `/challenge/challenge --giveflag`

By providing the correct argument, I successfully received the flag.

**pwn.college{ohtfu1_N8TSgrd-IJAbw30v1CdA.dRjM5QDLxETO0czW}**

# #Challenge 2: Learning Complex Usage

Here we had to run the `/challenge/challenge --printfile /flag` to get the flag. Here we read a mini documentation and saw that --printflag would do the job.

**pwn.college{o7SeJ2OGh4mL38003GvIibB-rox.dVjM5QDLxETO0czW}**

# #Challenge 3: Reading Manuals

Here we use a command `man` to read the desred manual. The correct syntax for this is `man <page>`.

To obtain the flag, I consulted the manual for the `/challenge/challenge` command using man challenge. The manual indicated that the correct usage to print the flag involves the `--finoud` option, specifically with the `NUM` value 418. 

Following these instructions, I executed the command `/challenge/challenge --finoud 418`, and got the flag. 

**pwn.college{4fJZin18o3udxFlG6mPvY_9Vc3e.dRTM4QDLxETO0czW}**

# #Challenge 4: Searching Manuals

Now here we have a few shortcuts we can use for scrolling.

I can choose to scroll through the text or jump directly to what I'm looking for. If I want to search for specific terms, I can press `/` and type my keyword, then hit Enter. Once I've searched, I can navigate through the results by pressing `n` for the next match or `N` for the previous one.

When exploring man pages, I can scroll using the arrow keys or Page Up/Page Down. Alternatively, if I prefer to search backwards, I can use `?` followed by my term.

So in this challenge I typed `man challenge` and went through the page, and found, with these shortcuts, an arguement `--ghfvc` that woulfd print the flag. I ran the command `/challenge/challenge --ghfvc`, and it said "Correct usage!"

**pwn.college{4orsg5uM73BA5SQxtghyr_--lpO.dVTM4QDLxETO0czW}**

# #Challenge 5: Searching for Manuals

Here to find out how to search for the correct `man` page, I can start by reading the `man` page for the man command with `man man`.

First I entered `man man`, and found out that we could use `man -k` to search. So i typed `man -k /challenge/challenge` and got `rpibcoguad (1)       - print the flag!`.

This was another manual for `/challenge/challenge`. So I entered the `man rpibcoguad` and got the `/challenge/challenge` manual. After getting the manual i saw that the arguement `--rpibco NUM` where NUM was 010 would print the flag.

Upon entering the command ` /challenge/challenge --rpibco 010`, I got the flag.

**pwn.college{0WrJ10GQVpJibAK7VcTo20guHaZ.dZTM4QDLxETO0czW}**

# #Challenge 6: Helpful Programs

Some programs that do not have a `man` page have some programs that have nearly the same purpose as `man`. Here, we use the `--help` command.

I ran the command `/challenge/challenge --help`, abiding by the format, to see the available options. 

Using  `/challenge/challenge -p`, the option to print the secret value, I discovered the secret value was 290. 

I then executed `/challenge/challenge -g 290`, as g gives the flag provided we enter the correct secret value, and the program confirmed my correct usage with "Correct usage!" This helped me navigate the challenge successfully.

**pwn.college{c2NvTyDMKflx9VBp0kWi2FN8Ef_.ddjM4QDLxETO0czW}**

# #Challenge 7: Help for Builtins

Certain commands are integrated directly into the shell rather than being separate programs with their own man pages and help options; these are known as builtins.

We can get a list of shell builtins by `help`, but we can also get the desired one usinf the `help <desired_builtin>`.

I ran the command `help challenge` to get information about the `challenge` builtin. 

The output indicated that the command requires specific arguments to function correctly. Notably, the option `--secret VALUE` prints the flag if the provided value is correct. The correct value for `--secret` was revealed to be "QtodIJw8."

After executing the command `challenge --secret QtodIJw8`, I received confirmation with "Correct! Here is your flag!" This successfully completed the challenge.

**pwn.college{QtodIJw8R3DfE52BPYyrlx5fjT3.dRTM5QDLxETO0czW}**
