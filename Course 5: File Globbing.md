# #Challenge 1: Matching with *

When the shell that we're programming in sees a `*` character in an argument, it takes it as a "wildcard", and replaces the arguement with any file that has a matching pattern as the arguement.\

It is very useful when there are less files with that pattern, and so we can type less and save time.

I successfully used the command cd /ch* to navigate to the /challenge directory. After that, I executed /challenge/run, which confirmed that I was in the correct directory with the message: "You ran me with the working directory of /challenge! Here is your flag." 

This indicates that I successfully completed the challenge.

**pwn.college{0cFaj9tf5r-CVFOX5riTxeAP_fG.dFjM4QDLxETO0czW}**

# #Challenge 2: Matching with ?

`?`, unlike `*`, matches only one character; the shell treats it as a "single character" wildcard here.

I navigated to the `/challenge` directory using the command cd /?ha??enge; replacing all a's and l's with `?`. After reaching the directory, I ran /challenge/run, and the output confirmed my location with the flag.

**pwn.college{IFrV0nPNS2WJfAiXiHdZ3nb3Jro.dJjM4QDLxETO0czW}**

# #Challenge 3: Matching with []

The `[]` notation acts as a wildcard for a specific set of characters defined inside the brackets.

I navigated to the `/challenge/files` directory using the command `cd /challenge/files`. Then, I executed `/challenge/run file_[bash]`, which successfully matched the specified files. The output confirmed my success with the message: "You got it! Here is your flag!"

**pwn.college{oFnvFMC7CjfSYD3mEOmJcCHTxtW.dNjM4QDLxETO0czW}**

# #Challenge 4: Matching paths with []

An important line to know is that globbing happens on a path basis.

I started from my home directory by running `cd ~`. 

Then, I executed the command `/challenge/run /challenge/files/file_[bash]` to use bracket globbing for matching the absolute paths of the specified files. The command successfully matched `file_b`, `file_a`, `file_s`, and `file_h`, and I received confirmation with the message: "You got it! Here is your flag!" 

This demonstrated my successful application of globbing to expand entire paths.

**pwn.college{sd0zg3smKrsW_Q1LHU9NCEOqlN-.dRjM4QDLxETO0czW}**

# #Challenge 5: Mixing globs

So for mixing all the globs and matching the files "challenging", "educational", and "pwning", the single statement, after we change directory to `/challenge/files` by `cd /challenge/files`, is 

`/challenge/run [cep]*`

**pwn.college{Evw5FgLGL7Gf4kFvBdz2HkxtrTp.dVjM4QDLxETO0czW}**

# #Challenge 6: Exclusionary globbing

When the first character in the brackets is a `!` or, in newer bash versions, a `^`, the glob pattern will invert, allowing it to match characters that are excluded from the list.

I navigated to the `/challenge/files` directory using the command `cd /challenge/files`. 

Then, I executed `/challenge/run [!pwn]*`, which successfully filtered out files that start with `p`, `w`, or `n`. 

This allowed me to run the command with the remaining files in the directory.

**pwn.college{Y3z-HxWQ6OS96sXgXgDlq_bjZiY.dZjM4QDLxETO0czW}**
