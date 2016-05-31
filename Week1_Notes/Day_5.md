# Week 1 Day 5

### Functions of the Day
#### Unix Functions
- **awk**
- **grep,egrep,fgrep** - find something based on a regular expression
- **ll**
- **wc** - word count
- **|** - pipe from left command to the right command
- **<** - take input from a file
- **>** - redirect output to a file
- **head,tail,less**
- **man, info + command** - gives info
- **pwd** - gives directory path
- **lm -la** - shows all hidden files (hidden files start with a .)
- **ln** - allows you to create a link to a folder or file so you aren't 'cd-ing' everytime
- **touch** - will create a file if it isn't there
- **rm -rf** - removes folders recursively (**Be careful!**)
- **cat** - concatenate, dumps to screen
- **uniq** - return the unique words
- **env** - tells you your current environment variables
- **history** - returns a list of the command history
- `!command_num` - will run a command based on it's number from the history
- **find**
- **locate**
- **ack** - recursively descend file tree and find files that match a regular expression
- **kill** - kills a process

#### Objectives
- Use unix essentials
    - config
    - navigate
    - manipulate files
    - basic job control in unix (i.e. kill a process)
- describe CRISP_DM workflow
- learn how to do basic EDA (exploratory data analysis)
- setup AWS

## UNIX
- very robust for data science, can build quick efficient custom programs that solve difficult problems quickly
- the command line assumes you are smart, it won't ask you things, it treats you like an adult
- **Filters + Pipes** - unix has a bunch of small building blocks that chain well together
- At the core of an operating system you have **The kernel** which does:
    1. multitasking
    2. mutual exclusion - doesn't allow two things to happen at once
    3. synchronization
- when UNIX run things, it runs them in something called a process which has 3 things:
    1. operating system
    2. thread of execution (machine instructions)
    3. stack and heap - types of memory that are used during processes
- there are many different kinds of shells: `sh, csh, bash, zah, ksh, tcsh,...`
    - these are different interpreters
    - programming language for the shell scripts
- `$HOME` - environment variable of the home directory
- aliases - are custom commands that we can set in our bash profile
- EOF = end of file

#### Permissions
`-|rwx|---|---` first 3 are `u`ser permissions, second 3 are `g`roup permissions, third 3 are the `w`orld permissions
- r = read = 4
- w = write = 2
- x = execute = 1
- `chmod` - allows you to change permissions on a file
- `chmod gtrx file`
- `chmod 750 file` - this uses the numerical equivalents for the read write and execute

## More Notes

- ssh - command that lets you connect to another shell somewhere else



### Today we're signing up for AWS
