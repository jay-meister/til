**run a file**
```sh

```
**shebang**
```sh
#!/bin/bash
echo hello
```
- instructs `program loader` to call `/bin/bash` passing current path as first argument
- QUESTION: running `bash say_hello.sh` runs fine both with/without shebang - why do we need?


**variabels**
```sh
# use $VARIABLE to reference variables
ME=Jack; echo "Hi, $ME"
# Hi, Jack

# single quotes will not expand variables
ME=Jack; echo 'Hi, $ME' 
# Hi, $ME

# delete a variable:
ME=Jack; unset ME;echo "Hi, $ME"
# Hi, 
```

**environment variabels**
```sh
# export environment variables:
export GLOBAL_VAR="I am a global variable"

Variable Description
-------- ----------------------------------------------------------------------------
$HOME    The current users home directory.
$USER    The current user.
$PATH    A colon-separated list of directories in which the shell looks for commands.
$PWD     The current working directory.
$RANDOM  Random integer between 0 and 32767.
$UID     The numeric, real user ID of the current user.
$PS1     The primary prompt string.
$PS2     The secondary prompt string.
```

List of environment variables in Bash:
http://tldp.org/LDP/Bash-Beginners-Guide/html/sect_03_02.html#sect_03_02_04

**string**
```sh
# use $() to run bash command in string
echo "Hi $(whoami)" 
# Hi, jackmurphy
```

**echo**
```sh
# $() to interpolate variables into strings
echo -e "\nprints\nnew\lines"
echo -n "no new line after printing:"
# use $() or `` to save output into variable
pwd # /Users/jackmurphy/test
P=$(echo pwd)
echo $P

CURRENT_DIR=`echo $(pwd)`; echo $CURRENT_DIR
```