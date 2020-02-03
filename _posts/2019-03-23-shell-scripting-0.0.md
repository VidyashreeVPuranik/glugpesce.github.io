---
layout: post
title: Shell Scripting 0.0
categories: event
date: 2019-03-23
---
## SHELL SCRIPTING 0.0

> *Shell Scripting is a series of command/s stored in a plain text file and
> execute the text file instead of typing each command it is Shell Script.*

**Shell scripts** can take input from a user or file and output them to the
screen. Whenever one do the **same task over and over again**, using of shell
script automates the repetitive task. Shell acts as a interface between Kernel
and User.

![](https://cdn-images-1.medium.com/max/800/1*A3RH0jSbqvaFYyD1AtPdtA.jpeg)
<span class="figcaption_hack">Shell Scripting [courtesy: Internet]</span>

**A script consists of**

    Shell Keyword - if..else, do..while.
    Shell commands- cd, pwd, man, echo etc..
    Linux binary commands - w, who, free etc..
    Text processing utilities - grep, awk, cut.
    Functions - frequently used commands together via functions. 
    For  example, 
     /etc/init.d/functions is a file which contains functions which are used by most system shell 
     scripts in the directory. In simpler terms printf which is part of pre defined function.
    Control flow- are statements which contains if..then..else or shell loops to perform repeated actions.

### **Table of Contents :**

#### 1. Introduction to Shell Scripting<br> 2. Variables and Environment<br> 3.Decision Making<br> 4. Loops (Bash Loops)<br> 5. Pipes and Traps<br> 6.Functions<br> 7. Extra concepts

### I. Introduction to Shell Scripting

#### **1.Linux Shell**

A Computer understand the language of 0’s and 1’s called **binary language**,it
is difficult for all of us, to read and write in binary language. Wherein OS
have a program called **Shell or command line interpreter** which accepts your
instruction or commands written in high level language and translate it into
computers binary language.<br> There are many types of shell like **BASH, CSH,
KSH, etc.** Among them, BASH is very famous and it was developed by GNU.
**Bourne -Again SHell(BASH)** is the default GNU/Linux shell and it does run on
every version of Unix, ms-dos, and Windows platforms.<br> **KSH** - AT&T version
of the Korn shell.<br> **CSH** - C like syntax.

Bash understands the below commands :

     such as if, else, for, while etc..
     (user defined functions such as genpasswd)
     such as cd, ls, pwd etc..
     such as /home/text or /bin/desktop/programs
     

#### **2. Shell Script**

Let’s use **Nano** in our case and to begin with script lets start with **Hello
World!.**

    nano hello.sh (editor opens and sh is the format)

    #!/bin/bash
    echo "Hello, World!" (echo works the same as print)
    echo "Welcome to the Shell Scripting Tutorial !!."

    bash hello.sh (changes the execution permission)

    Hello, World!
    Welcome to the Shell Scripting Tutorial !!.

Our script started with **#! (shabang)**, it is the interpreter for execution in
**GNU/Linux or UNIX OS**. Most of the shell script starts with **#!/bin/bash.**<br> And after shabang the path indicates the path  Bash installed
in OS and in GNU/Linux its under **bin.** 

#### **3. Commenting** 

Commenting can be done using **#** before line and for multiple line comment use
**<<COMMENT keyword:**

    #!/bin/bash
    #This is an Example of Single line Comment!
    echo "Welcome !!"


    #!/bin/bash
    echo "Welcome!!"
    <<COMMENT
    Multiple line Comment : Usage
    Commenting two or more lines of a script
    Can be used to explain the written code
    COMMENT
    echo "End!!"   



### **II . VARIABLES & ENVIRONMENTS**

**Variables** are used to store data and configuration options. There are two types
of variable<br> 1. System Variables.<br> 2. User defined Variables.

#### **1. System Variables**

The variables are created and maintained by **Bash Shell** and it is is defined in
**CAPITAL LETTERS** only. Aspects of shell can be configured by modifying system
variables such as PATH, LANG, DISPLAY , HOSTNAME etc..

    ╔══════════════╦═════════════════════════════════════════════════╦═════════════════════════╗
    ║ System       ║                    Meaning                      ║ Variable Value Type     ║  
    ║ Variable     ║                                                 ║                         ║ 
    ║ Variable     ║                                                 ║                         ║ 
    ╠══════════════╬═════════════════════════════════════════════════╬═════════════════════════╣
    ║ BASH_VERSION ║ Holds the version of this instance of bash.     ║ echo $BASH_VERSION      ║
    ║ HOSTNAME     ║ The name of the your computer.                  ║ echo $HOSTNAME          ║
    ║ HOME         ║ The home directory of the current u             ║ echo $HOSTNAME          ║
    ║ HISTSIZE     ║ The number of commands to remember in the       ║ echo $HISTSIZE          ║
    ║              ║ command history.Default value is 500.           ║                         ║
    ║ HISTFILESIZE ║ The maximum lines contained in the history file.║ echo $HISTFILESIZE      ║
    ║ HISTFILE     ║ The file in which command history is saved.     ║ echo $HISTFILE          ║
    ║ CDPATH       ║ The search path for the cd command.             ║ echo $CDPATH            ║
    ║ IFS          ║ IFS is used for word splitting after expansion  ║ echo $IFS               ║
    ║ LANG         ║ Determine the locale category                   ║ echo $LANG              ║
    ║ PATH         ║ list of directories where shell search commands.║ echo $PATH              ║
    ║ PS1 	       ║ Your prompt settings. 	                      	 ║ echo $PS1               ║
    ║ TMOUT        ║ The default timeout for the read builtin command║ echo $TMOUT             ║
    ║              ║ The wait time for i/p after issuing the command ║                         ║
    ║ TERM         ║ Your login terminal type.                       ║ echo $TERM              ║
    ║              ║                                                 ║ export TERM=vt100       ║
    ║ SHELL        ║ Set path to login shell.                        ║ echo $SHELL             ║
    ║ DISPLAY      ║ Set X display name                              ║ echo $DISPLAY           ║
    ║              ║                                                 ║ export DISPLAY=:0.1     ║
    ║ EDITOR       ║ Set name of default text editor.                ║export EDITOR=/usr/bin/vi║
    ╚══════════════╩═════════════════════════════════════════════════╩═════════════════════════╝
    


When it comes to display the value of any given variable,


    #!/bin/bash
    VARIABLE=1029
    printf "$VARIABLE\n"
    printf "String %s\n" $VARIABLE
    printf "Signed Decimal Number %d\n" $VARIABLE
    printf "Floating Point Number %f\n" $VARIABLE
    

#### **2. User Defined Variables**

This type of variables are created and maintained by user. Variable defined here
may use any valid variable name, but it is good practice to avoid all uppercase
names as many are used by the shell.

<br> 

<br> 

### III. DECISION MAKING

> *So far all the scripts we have followed is ***sequential flow***(line by line),
> is it possible to execute a command based on condition if it exist?*

**If** command is used for selective execution of certain commands of a script.
A warning message can pop up and run a script more interactively using if
command to execute the script based on any given **condition.**<br> A condition
is an expression that evaluates to a boolean value (0/1). A condition is used in
**shell script loops and if statements.**

    echo $(( 7 + 4))    #Output : 11
    echo $(( 5 < 2 ))   #Output : 0, Is 5 is less than 2? No
    echo $(( 5 > 12 ))  #Output: 0, Is 5 greater than 12? No 
    echo $(( 5 == 10 )) #Output: 0, Is 5 equal to 10? No
    echo $(( 5 != 2 ))  #Output: 1, Is 5 is not equal to 2? Yes
    echo $(( 1 < 2 ))   #Output: 1, Is 1 less than 2? Yes 
    echo $(( 5 == 5 ))  #Output: 1, Is 5 equal to 5? Yes

#### **1. Test Command**

The **test command** is used to check **file types and compare given values**.
Test is used in Decision Making statements too. It is used mainly for, <br> a.
File attributes comparisons<br> b.  Perform string comparisons<br> c. Basic
arithmetic comparisons.

**Note**: Try **man test** command on terminal for complete list of conditions
which are used for test command.

    test <condition>
    OR
    test <condition> && <true-command>
    OR
    test <condition> || <false-command>
    OR
    test <condition> && <true-command> || <false-command>

    test 5 -gt 2 && echo "Yes"
    test 1 -lt 2 && echo "Yes"
    test 5 -eq 9 || echo "No"
    test 5 -gt 2 && echo "Yes" || echo "No"
    test 5 -ne 10 && echo Yes || echo No

    Yes
    Yes
    No
    Yes
    Yes

#### **2. If Command Statements**

a. if then<br> b. if else fi<br> c. Nested ifs<br> d. Multilevel if then else

**a. if then**

    if condition     if test var == value     if test -f /file/exists
    then             then                     then
      command1         command1                 command1 
      command2         command2                 command2
      ...              ...                      ...
      commandN         commandN                 commandN
    fi               fi                       fi     

In a **If then** command,  condition is checked and if its true then commands
are executed, in false condition it exits. For Example,

    #!/bin/bash
    read -p "Enter a Password : " pass
    if test "$pass" == "gnu"
    then
      echo "Password verified."
    fi

**b. if else fi**

     if condition       if test var -eq val    
     then               then                    
       command1           command1                 
       command2           command2                
       ...                ...                   
       commandN           commandN                 
     else               else                    
       command1           command1                
       command2           command2               
       ...                ...                    
       commandN           commandN               
     fi                 fi 

In a **If else fi** command, condition is checked and if its true then commands
are executed, in false condition it else commands are executed. For Example,

    #!/bin/bash
    read -p "Enter a number : " num
    if test $num -ge 0
    then
    	echo "$num is Positive number."
    else
	echo "$num number is Negative number."
    fi


**c. Nested If**
In a **Nested I** command, condition is checked and if its true
then commands are executed interestingly we have another if condition as the
then commands, so again we need to complete the inner if condition and once
exited, we have false condition for the outer if command and else commands are
executed. 

	if condition
	then
		if condition
		then
			command1
			.....
			..
			commandN
		else
			command1
			....
			..
			commandN
		fi
	else
		command1
		...
		.....
		commandN
    fi
    
     
**d. Multilevel if then else**In a **Multilevel  If then else** command,
condition is checked and if its true then commands are executed, in false
condition it moves to **elif** then **condition1** is executed till we complete
**conditionN** and then else commands of the condition are executed. 

           if condition
           then
                       condition is true
                       execute all commands up to elif statement
           elif condition1 
           then
                       condition1 is true
                       execute all commands up to elif statement  
           elif condition2
           then
                       condition2 is true
                       execute all commands up to elif statement          
           elif conditionN
           then
                       conditionN is true
                       execute all commands up to else statement          
           else
                       None of the above conditions are true
                       execute all commands up to fi
           fi

#### **3. Exit Status**

Each Linux command executed have an exit status, it is nothing but an **integer
number**. **Zero(0)** as a  exit status means the command was successful in
execution without any errors. And a **non-zero (1–255)** as a exit status means
command was a failure.<br> Special shell variable **$?** can be used to get the
exit status of the previously executed command and use echo command to print th
exit status value.<br> **For Example** *lets search username is found or not?*

    #!/bin/bash
    FILE=/etc/passwd

    read -p "Enter a user name : " username

    #locate the username in the file passwd
    if grep "^$username:" /etc/passwd >/dev/null
    then
	echo "User '$username' found in $FILE file."
    else
	echo "User '$username' not found in $FILE file."
    fi

#### **4. Boolean Operators**

a. Logical AND - &&<br> b. Logical OR - ||<br> c. Logical Not - !

**a. Logical AND - &&** It executes commands based on the **exit status** of
another command where it runs second command only if **first is successful**.

    command1 && command2

    grep "^glugpesce" /etc/passwd && echo "Found in /etc/passwd"
    

**b. Logical OR -  &&** It executes commands based on the **exit status** of
another command where it runs second command only if **first is not
successful**.

    command1 || command2

    Checks whether we are root or not
    test $(id -u) -eq 0  && echo "You are root" || echo "You are NOT root"
    

**c. Logical Not - !** It checks whether the command is **true or false (0/1).**

    ! expression    [ ! expression ]    if test ! condition    if [ ! condition ]
                                        then                   then
                                          command1               command1
                                          ...                    ...
                                          commandN               commandN 
                                        fi                     fi

**For Example**: In the below case it executes if second command when first
command is false i.e., it creates a new folder/ directory called shell (command:
mkdir) if there is no folder or directory present in the machine.<br> Same is in
the case of prog1.sh.

    #!/bin/bash
    [ ! -d shell ] && mkdir shell
    [ ! -f prog1.sh ] && touch prog1.sh

#### **5. Numerical Comparison**

It can be done **test command**, the previous examples of program used these
**test command**. The Numerical Comparisons commonly used are eq, ge, gt, lt,
le, etc…

    #Numerical Comparison
    eq 	INTEGER1 -eq INTEGER2 	INTEGER1 is equal to INTEGER2 
    ge 	INTEGER1 -ge INTEGER2 	INTEGER1 is greater than or equal to INTEGER2 
    gt 	INTEGER1 -gt INTEGER2 	INTEGER1 is greater than INTEGER2 
    le 	INTEGER1 -le INTEGER2 	INTEGER1 is less than or equal to INTEGER2
    lt 	INTEGER1 -lt INTEGER2 	INTEGER1 is less than INTEGER2 
    ne 	INTEGER1 -ne INTEGER2 	INTEGER1 is not equal to INTEGER2 

#### **6. String Comparisons**

It can also be done using **test command.**

    STRING1 = STRING2

    STRING1 != STRING2

    -z STRING

The three condition can be checked in a shell script. For Example :

    #!/bin/bash
    read -s -p "Enter your password :  " pass
    echo 
    #checks whether the string is non zero
    if test -z $pass 
    then
        echo "No password was entered!!! Cannot verify an empty password!!!"
        exit 1
    elif test "$pass" != "gnu"
    then
        echo "Wrong Password !!"
    else
        echo "Authentication of password Success!"
    fi


#### **7. File attributes comparisons**

**File attributes** can be used making use of **test commands or conditional
execution or decision making statements**.Commonly used among them are -f, -d,
-a, -c, etc…

    #File Attributes Comparison are

    -a file : True if file exists. 
    -b file : True if file exists and is a block special file. 
    -c file : True if file exists and is a character special file. 
    -d dir  : True if file exists and is a directory. 
    -e file : True if file exists. 
    -f file : True if file exists and is a regular file. 
    -g file : True if file exists and is set-group-id.
    -h file : True if file exists and is a symbolic link.
    -k file : True if file exists and its ‘‘sticky’’ bit is set.
    -p file : True if file exists and is a named pipe (FIFO).
    -r file : True if file exists and is readable.
    -s file : True if file exists and has a size greater than zero.
    -t fd   : True if file descriptor fd is open and refers to a terminal.
    -u file : True if file exists and its set-user-id bit is set.
    -w file : True if file exists and is writable.
    -x file : True if file exists and is executable.
    -O file : True if file exists and is owned by the effective user id.
    -G file : True if file exists and is owned by the effective group id.
    -L file : True if file exists and is a symbolic link.
    -S file : True if file exists and is a socket.
    -N file : True if file exists and has been modified since it was last read. 

#### 8. Command line argument

A **command line argument** is nothing but an argument sent to a program being
called. 

    cd shell

    shell: No such file or directory.

Command line Arguments are listed below
    
    $* : holds all command line parameters or arguments.
    $# : holds the number of positional parameters.
    $- : holds flags supplied to the shell.
    $? : holds the return value set by the previously executed command.
    $$ : holds the process number of the shell (current shell).
    $! : hold the process number of the last background command.
    $@ : holds all command line parameters or arguments.

In a command line argument special shell variable are used and they are <br> $1,
$2, $3, $4, $5, …,$9.<br> Few shell variables such as <br> a. $@<br> b. $*

**$@** are expanded as **“$1” “$2” “$3” … “$n”.**<br> 
**$*** are expanded as **“$1y$2y$3y…$n”,** where y is the value of **$IFS** which acts as an **separator.**

**Program**

    #!/bin/bash
    IFS="- "
    echo "The script name : $0"
    echo "The first argument to the script : $1"
    echo "The second argument to the script : $2"
    echo "The third argument to the script : $3"
    echo "The fourth argument to the script : $4"
    echo "The number of arguments passed to the script : $#"
    echo "* Display all free Softwares names usinng (\$@ version) : $@"
    echo 
    echo "* Display all Free Softwares names using (\$* version) : $*"

**Execute**

    bash cal_shell.sh VLC GIMP Firefox Inkspace

**Output**

    The script name : cal1.sh
    The first argument to the script : VLC
    The second argument to the script : GIMP
    The third argument to the script : Firefox
    The fourth argument to the script : Inkspace
    The number of arguments passed to the script : 4
    * Display all free Softwares names usinng ($@ version) : VLC GIMP Firefox Inkspace

    * Display all Free Softwares names using ($* version) : VLC-GIMP-Firefox-Inkspace


**Exit Command**In order to exit the **BASH shell** we can use **exit** command in
out script.<br> *Try to use ***exit 0*** at the end of previous program and echo
it using ***echo $?*** and check the ***exit status***?*

#### 9. The Case statement

The **case statement** is easier to use than multilevel if then else, matching
several values against one variable is a lot easier in the case statement. It is
easier to read and write.

          case  $variable-name  in            case  $variable-name  in
                pattern1)                           pattern1|pattern2|pattern3)   
     		            command1                            command1                           
                    ...                                 ...     
                    commandN                            commandN
                    ;;                                  ;;
                pattern2)                           pattern4|pattern5|pattern6)   
     		            command1                            command1 
                    ...                                 ... 
                    commandN                            commandN
                    ;;                                  ;;
                patternN)                           pattern7|pattern8|patternN)
     		            command1                            command1 
                    ...                                 ... 
                    commandN                            commandN
                    ;;                                  ;;
                *)                                  *)   
          esac                                 esac 

**The case statement** allows to check conditions in a easier manner and if a
command-line is needed when the condition evaluates to true, it can be done.
Here the **$variable-name** is compared against the conditions until a match is
found. ***)** acts as default case when no match is found it is executed.
Including **;;** at the end of each **commandN** is a must. The shell executes
all the statements up to the two semicolons. And the **esac** is always required
inorder to indicate end of case statement. <br> **For Example**,

**Program**

    #!/bin/bash
    NOW=$(date +"%a")
    case $NOW in
    	    Mon)	
		echo "Full backup", $NOW;;
	    Tue|Wed|Thu|Fri)
		echo "Partial backup", $NOW;;
	    Sat|Sun)	
		echo "No backup", $NOW;;
	    *) ;;
    esac
    

**Program**

    file 1: prog.sh
    #!/bin/bash
    var=$1
    case $var in
            maths)
                    echo "In Engineering we have MATHS in 1st to 4th Sem..."
                    ;;
            phy)
                    echo "Luckily or Sadly we have we have PHYSICS only for 1st or 2nd Sem..."
                    ;;
            ece|cse|ise|ae|ipe|ce|eee)
                    echo "Now its time to ask Seniors..."
                    ;;
            *)
                    echo "PSECE"
                    echo "Welcome to $var Department !!!"
                    echo "Have a nice time !!"
                    echo "	$var : Departmental Issues!!  talk to HOD"	;;
    esac

    file2 : execute.sh
    chmod +x prog.sh
    ./prog.sh maths
    ./prog.sh phy
    ./prog.sh ec


**Output**

    In Engineering we have MATHS in 1st to 4th Sem...
    Luckily or Sadly we have we have PHYSICS only for 1st or 2nd Sem...
    PSECE
    Welcome to ec Department !!!
    Have a nice time !!
     ec : Departmental Issues!!  talk to HOD

<br>

> We will continue other topics in next blog session . Thank you


### **Important Linux Commands** 
#### Using Terminal is fun and learning made easy! Forthe [basics commands](https://glug-pesce.gitlab.io/event/introduction-to-gnu-linux-and-terminal-commands/)please visit the below blog session on our [Website :https://glug-pesce.gitlab.io/](https://glug-pesce.gitlab.io/)

<br> 
