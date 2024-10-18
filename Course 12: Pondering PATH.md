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

# #Challenge 3: 
