# #Challenge 1: The PATH variable

In this exercise, I learned how to manipulate the `PATH` variable, which determines where the shell looks for executable commands.

Initially, I ran `ls` to list the files in my directory, which worked as expected.

Then, I set the `PATH` variable to an empty string using `PATH=""`, causing the shell to lose track of executable commands and resulting in an error when I tried to run `ls` again.

After clearing the `PATH`, I executed `/challenge/run`, which attempted to delete the flag using `rm`.

However, since `rm` was also inaccessible, the command failed, and the flag remained intact, allowing me to claim it successfully.

**pwn.college{sG_GAqSUKZZYmOooYtM7oiNKxuu.dZzNwUDLxETO0czW}**

# #Challenge 2: Setting PATH

In this exercise, I learned how to manipulate the `PATH` variable to simplify command execution.

The goal was to ensure that `/challenge/run` could successfully invoke the 'win' command.

Without modifying `PATH`, I'd have to specify the full path to run commands, which could lead to failure in invoking 'win.'

By setting `PATH="/challenge/more_commands"`, I was able to run `/challenge/run` directly, ensuring it invoked 'win' as intended.

This highlighted the importance of properly setting `PATH` to facilitate command execution and achieve the desired outcome.

**pwn.college{oIQnQNYdRp47ESJJuo4qaNPv_Sx.dVzNyUDLxETO0czW}**

# #Challenge 3: Adding Commands

To create a custom command called "win", I started by recognizing that the win command did not exist.

I wrote a script with `echo -e "read flag < /flag\necho \$flag" > ~/win` to read and display the flag.

After making the script executable using `chmod +x ~/win`, I set the PATH to include my home directory with `PATH="~/"`.

Finally, I executed `/challenge/run`, which invoked the "win" command and successfully revealed the flag.

**pwn.college{kkuNe_lB1Mp6LVPY6BoB7pGXTKS.dZzNyUDLxETO0czW}**

# #Challenge 4: Hijacking Commands

In this challenge, I aimed to prevent the deletion of the flag by hijacking the `rm` command.

I created a script using `echo -e "read flag < /flag\necho \$flag" > ~/rm`, which reads the flag from the file and echoes it.

After making the script executable with `chmod +x ~/rm`, I set the `PATH` variable to `PATH="~"` to ensure my custom `rm` command would be invoked.

When I ran `/challenge/run`, it tried to remove the flag, but instead, it executed my script, revealing the flag.

Unlike `cat`, which is an external command that couldn’t be found due to the altered `PATH`, `read` is a built-in command in the shell, allowing me to successfully access the flag.

**pwn.college{cT5aL8zbfurNhNUBvS0J7QqJoN3.ddzNyUDLxETO0czW}**
