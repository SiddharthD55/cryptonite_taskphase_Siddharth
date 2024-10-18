# #Challenge 1: Chaining with Semicolons

Chaining commands in a Linux shell can be effortlessly achieved using the semicolon (`;`), which enables multiple commands to run in succession without the need for separate Enter key presses.

In this challenge, I utilized this technique by executing `/challenge/pwn; /challenge/college`, which successfully linked the two commands and resulted in the flag.

This method streamlines command execution and enhances efficiency in the shell.

**pwn.college{EbkRfXVW_CwKAKe0wzPwlHDA-Ru.dVTN4QDLxETO0czW}**

# #Challenge 2: Your First Shell Script

As commands become more complex, managing lengthy prompts can become cumbersome, which is where shell scripts come in handy.

By placing commands in a file, such as `x.sh`, and executing it with `bash`, you streamline the process.

For example, I created a script using `echo -e "/challenge/pwn\n/challenge/college" > x.sh` to combine two commands into a shell script.

Running `bash x.sh` executed both commands in sequence, confirming my success with the flag.

**pwn.college{Yg4h6OMvWKemss_OCExhV2lwUQV.dFzN4QDLxETO0czW}**

# #Challenge 3: Redirecting Script Output

In this challenge, I explored how to redirect the output of a shell script to another command using piping.

I created a script with the commands `/challenge/pwn` and `/challenge/college` using `echo -e` and saved it as `script.sh`.

When I executed the script with `bash script.sh | /challenge/solve`, the output was successfully piped into `/challenge/solve`, confirming my success with the flag.

This method illustrated how scripts can be treated as commands, allowing for flexible output redirection.

**pwn.college{wDSdJLjNxfnLKAbZnf55YX65opr.dhTM5QDLxETO0czW}**

# #Challenge 4: Executable Shell Scripts

In this exercise, I learned that instead of invoking a shell script with `bash script.sh`, which launches the Bash shell to read commands from the script, I could run it directly by making it executable.

I created a script called `solve.sh` with the command `/challenge/solve` and initially faced permission issues when trying to execute it.

After using `chmod +x solve.sh` to grant execution permissions, I successfully ran the script with `./solve.sh`, which led to the flag.

This streamlined the process and demonstrated the benefits of using executable scripts.

**pwn.college{8paWwJOpkUhRKQOGDM97_FYOH81.dRzNyUDLxETO0czW}**
