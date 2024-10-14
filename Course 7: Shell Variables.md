# #Challenge 1: Printing Variables

In this challenge , we cannot read the flag just by running `/challenge/flag`. This is because the flag is put into a variable named `FLAG`.

I used the command `echo $FLAG` to print the flag stored in the FLAG variable in my shell. When I executed this command, it displayed the flag.

This shows how to access and display the value of an environment variable in a shell.

**pwn.college{Ql1KEuj2Ea2GjwjqOOwPDtff25q.ddTN1QDLxETO0czW}**

# #Challenge 2: Setting Variables

For assigning values to variables we use the syntax `VARIABLE_NAME=<Value>` for example `PWN=COLLEGE`.

One thing to be careful here is that there should be no space near the `=` sign, or else the varibale is treated as a command.

Here all i had to do was invoke the `PWN=COLLEGE` command to assign the value COLLEGE to PWN, and I got the flag.

**pwn.college{g7NdDfQXiYXQ647wqqQNltcF8FX.dlTN1QDLxETO0czW}**

# #Challenge 3: Multi-word Variables

To store values having space, we will need to enclose them in `""` (double quotes), as the shell recognises he space as the end of the variable assignment and the enxt word as another command.

This is what i did when I did this challenge, basically executing the line `PWN="COLLEGE YEAH"`.

**pwn.college{89WXiXasZlwfIkXUGWqIySihkcu.dBjN1QDLxETO0czW}**

# #Challenge 4: Exporting Variables

To complete the challenge, I first exported the variable `PWN` and set it to the value `COLLEGE`. Then, I set the variable `COLLEGE` to the value `PWN` without exporting it.Printing Exported Variable

To ensure that `COLLEGE` was not automatically exported, I ran the `unset COLLEGE` command before executing the final command.

Finally, I executed `/challenge/run`, which confirmed that I had successfully exported `PWN` while keeping `COLLEGE` local, resulting in the correct outcome.

**pwn.college{cLDbASbMo91H2ju_18Q9ZAI8xC1.dJjN1QDLxETO0czW}**

# #Challenge 5: Printing Exported Variables

Here we can use the `env` command to print out all the exported variables in the shell. I did just that, and got a huge list, among which i found the `FLAG` variable containing the flag.

**pwn.college{4_mr7EC1pO70WItz2A8bsEz6eFR.dhTN1QDLxETO0czW}**

# #Challenge 6: Storing Command Output

In the course of working with the shell, I often want to store the output of a command in a variable using command substitution. 

For example, I used `PWN=$(cat /challenge/run)` to capture the contents of the file into the variable `PWN`, and then print it out using `echo` command, basically `echo $PWN` to read the file, basically the flag.

I can then use this variable later in my script, making it useful for handling dynamic data.

I can also use backticks for command substitution, like ``FLAG=\`cat /flag\`` instead of `FLAG=$(cat /flag)`. However, backticks are an older method and can be cumbersome for nesting commands. In contrast, using `$(...)` is much clearer and easier for me to manage. Overall, I prefer `$(...)` for its readability and flexibility.

**pwn.college{8I5lszLs9BhUmct-8ORnzRyfKam.dVzN0UDLxETO0czW}**

# #Challenge 7: Reading Input

We simply use the `read` command here.

The syntax is `read VARIABLE_NAME`. To enable entering a desired prompt, we use `-p` arguement and the syntax would then be `read -p "PROMPT" VARIABLE_NAME`.

I started by reading the value into the `PWN` variable. To do this, I used the command `read PWN`, which prompted me to enter the value. Once I provided the input, I confirmed that I had set the `PWN` variable properly.

After successfully storing the value in `PWN`, I could use it in my scripts or commands as needed. Finally, as promised, I received the flag, which signifies that I completed the task correctly. 

This process not only helped me understand variable assignment but also demonstrated how to capture user input effectively.

**pwn.college{YqPo-CcQy7_PI3UC6e9Xi2oEQMu.dhzN1QDLxETO0czW}**

# #Challenge 8: Reading Files

Often, when shell users want to read a file into an environment variable, they might use a command like `VAR=$(cat some_file)`, which is considered a "Useless Use of Cat."

Instead, I can leverage the shell's capabilities to read files directly into variables. For example, to read the contents of `/challenge/read_me` into the `PWN` variable, I use the command `read PWN < /challenge/read_me`.

This redirects the file into the standard input of the `read` command, allowing me to capture the value efficiently. I also got the flag.

After executing the command, I can verify it by echoing `$PWN`.

**pwn.college{UUZiEnoJkdIFuMXyMy3A29zO2cY.dBjM4QDLxETO0czW}**
