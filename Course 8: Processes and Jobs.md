# #Challenge 1: Listing Processes

The `ps` command, which stands for either "process snapshot" or "process status," is used to list running processes, typically those associated with the terminal.

Its syntax can be specified in two main ways: the "standard" syntax with options like `-e` for every process and `-f` for full format, which can be combined as `-ef`; and the "BSD" syntax, using `a` for all users, `x` for processes not tied to a terminal, and `u` for user-readable output, combined as `aux`.

Although `ps -ef` and `ps aux` produce slightly different formats, both provide essential information about the processes on the system.

I ran the `ps -ef` command, which displayed a list of processes currently running on the system, along with their details such as user ID (UID), process ID (PID), parent process ID (PPID), CPU usage (C), start time (STIME), terminal (TTY), CPU time (TIME), and the command (CMD).

Among the listed processes, I executed the `/challenge/374-run-10822` command, which revealed the flag.

**pwn.college{Ya46Ql4QxbEj-BMx22-lEwyg4pp.dhzM4QDLxETO0czW}**

# #Challenge 2: Killing Processes

I learned how to terminate processes in Linux using the `kill` command, which allows a process to shut down gracefully.

After running `ps -ef`, I viewed the active processes, including two instances associated with `/challenge/dont_run`: process 93, which was started by a bash shell, and process 73, which was running directly under my user account, "hacker."

When I tried to kill process 93 with `kill 93`, I received an error message indicating "No such process," meaning it had already terminated. However, I still didn’t receive the flag.

I then successfully killed process 73 with `kill 73`, which allowed me to meet the challenge requirements and finally receive the flag. 

This experience highlighted the importance of knowing which processes I could control within a multi-user environment.

**pwn.college{U3Zuug8uAFI6tms29DLRmhEbKwO.dJDN4QDLxETO0czW}**

# #Challenge 3: Interrupting Processes

I learned that to terminate a process that’s clogging up my terminal, I could use the hotkey **Ctrl-C**, which sends an "interrupt" signal to the application waiting for input. This typically prompts the application to exit cleanly.

During the challenge, I was told that I wouldn't receive the flag until I exited the running process.

I used *Ctrl-C** to interrupt the process, and upon doing so, I received the flag.

This experience reinforced the effectiveness of using terminal shortcuts to manage running processes.

**pwn.college{4YKmEUMwLgx8FYL4PDHyMRcropR.dNDN4QDLxETO0czW}**

# #Challenge 4: Suspending Processes

I discovered that instead of terminating a process, I could suspend it using **Ctrl-Z* to regain control of my terminal.

During the challenge, I was prompted to obtain a flag only if another copy of the process was running.

After confirming there was no second instance, I used **Ctrl-Z* to suspend the current process, which returned the message: `[1]+ Stopped /challenge/run.`

When I executed the command again, it confirmed that another instance was now active. With both copies running, I successfully obtained the flag, receiving the flag.

This experience demonstrated the usefulness of suspending processes to free up my terminal without terminating them.

**pwn.college{otKMa06YgL8lQQk_RZpW-b-5LEQ.dVDN4QDLxETO0czW}**

# #Challenge 5: Resuming Processes

I learned that to resume a suspended process, I can use the `fg` command, which brings the process back to the foreground of my terminal.

During the challenge, I was instructed to suspend the process using **Ctrl-Z* and then resume it with the `fg` command.

After suspending the process, I received the message: `[1]+ Stopped /challenge/run.`

I then typed `fg` to bring the process back, and it responded with the flag.

This experience highlighted the importance of using `fg` to manage suspended processes effectively instead of terminating them.

**pwn.college{UwbTeo4MmA-2FK-D67k2QNIAQWj.dZDN4QDLxETO0czW}**

# #Challenge 6: Backgrounding Processes

I learned to resume suspended processes in the background using the `bg` command, which frees up my shell.

During the challenge, I needed another instance of a process running and not suspended to receive the flag.

After suspending the process with **Ctrl-Z*, I typed `bg` to resume it in the background. I then launched a new instance of the process with `/challenge/run`, confirming another copy was active. This resulted in the flag.

This experience demonstrated the usefulness of the `bg` command for managing processes.

**pwn.college{EeMxzQlbP3if0-UZhTKvzGzXAY1.ddDN4QDLxETO0czW}**

# #Challenge 7: Foregrounding Processes

In this level, I learned how to manage backgrounded processes by suspending, resuming, and then foregrounding them.

After running the command `/challenge/run`, I suspended the process with **Ctrl-Z*.

I then used the `bg` command to resume it in the background, allowing me to regain control of my terminal.

I hit Enter a few times to scroll past any overlapping text.

Finally, I brought the process back to the foreground using the `fg` command. This resulted in the flag.

This experience reinforced the effective management of processes by utilizing the suspend, background, and foreground commands.

**pwn.college{c7hbVQkK0ek6vTxXwImU7YYXYYx.dhDN4QDLxETO0czW}**

# #Challenge 8: Starting Backgrounded Processes

In this level, I learned that I can start a process directly in the background by appending an ampersand (`&`) to the command.

Initially, when I ran `/challenge/run`, it started in the foreground, and I was informed that I needed to run it in the background to receive the flag.

So, I executed the command again, this time as `/challenge/run &`, which successfully started the process in the background. I received the flag as a reward for correctly executing the command.

This experience highlighted the simplicity of starting processes in the background right from the start.

**pwn.college{ci2NcO8uFaYAmcyUF_6bTWctNbx.dlDN4QDLxETO0czW}**

# #Challenge 9: Process Exit Codes

In this level, I learned about exit codes for shell commands, which indicate whether a command succeeded or failed.

Successful commands usually return an exit code of `0`, while failed commands return a non-zero value.

For example, when someone uses `touch test-file`, it succeeded and returned `0`. However, when he or she tried to create a file at a restricted location with `touch /test-file`, it failed and returned `1`. 

During the challenge, I executed `/challenge/get-code`, which exited with an error code of `136`.

I then submitted this code with `/challenge/submit-code 136`, and I received the flag for my successful submission.

This experience emphasized the importance of understanding exit codes to check the success or failure of commands.

**pwn.college{IlRdlcNG9Bkyn5SN67MAfH9bPKN.dljN4UDLxETO0czW}**
