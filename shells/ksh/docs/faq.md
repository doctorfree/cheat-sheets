# FAQ

## General
                                                                 
### What is KornShell?                                                   

KornShell is a command and scripting language that is a superset 
of the System V UNIX shell, aka, BourneShell (or *sh*).          
                                                                 
### What is ksh?                                                         

ksh is the name of the program that implements the KornShell     
language.                                                        
                                                                 
### What is the history of ksh?                                          

ksh was written by David Korn at Bell Telephone Laboratories.    
David Korn is currently at AT&T Research. The first version of   
ksh was in 1983. It was the first shell to have command line     
editing with both emacs and vi style interaction. The 1986       
version was the first to offer multibyte support. The 1988       
version of ksh is the version that was adopted by System V       
Release 4 UNIX and was a source document for the IEEE POSIX and  
ISO shell standards. The 1993 version is a major rewrite of the  
1988 version and focuses more on scripting.                      
                                                                 
### Where is the official description of the KornShell language?         

The Bolsky and Korn book, *The KornShell Command and Programming 
Language*, published by Prentice Hall, defines the 1988 version. 
The newer Bolsky and Korn book, *The New KornShell Command and   
Programming Language*, also published by Prentice Hall, describes
the 1993 version. There are many new features since this book was
published and the man page for ksh93 is kept up to date.         
                                                                 
### What are the major new features of KornShell 1993?                   

The only major new interactive features are key binding and tab  
completion. Major new language features are floating point       
arithmetic, associative arrays, complete ANSI C printf, name     
reference variables, new expansion operators, dynamic loading of 
built-in commands, active variables, and compound variables.     
Active and compound variables allow shell variables to behave    
like objects. The ability to define types was added in 2009. In  
addition, ksh93 has been written to be extensible with an C      
language API for programming extensions.                         
                                                                 
### Are any further releases of ksh planned?                             

Yes, the KornShell language and ksh implementation are in active 
development. Most of the focus will be on scripting and          
reusability.                                                     
                                                                 
### Why are newer release of ksh still called ksh93?                     

We started the AST/ksh OpenSource release process in the late    
90\'s. At that point ksh93 was the well-known name for ksh. The  
OpenSource release was finally granted in March 2000. No one has 
since volunteered to repeat that process for ksh*XX*.            
                                                                 
### How can I determine the release or version of a particular ksh?      

The current version and release string may be accessed by        
**\${.sh.version}** and **\$KSH_VERSION**. The format is         
**Version** *features* 93*version*\[-/+\] *release*:             
-   *features* \-- compile time features, typically enabled by   
    **SHOPT\_***foo* state variables in the ksh93 Makefile. A    
    single letter represents each feature:                       
    -   **A** (*SHOPT_AUDIT*)                                    
    -   **B** (*SHOPT_BASH*) bash compatibility mode.            
    -   **J** (*SHOPT_COSHELL*) **-lcoshell** job pools.         
    -   **j** (*SHOPT_BGX*)                                      
    -   **L** (*SHOPT_ACCT*)                                     
    -   **M** (*SHOPT_MULTIBYTE*)                                
    -   **P** (*SHOPT_PFSH*)                                     
    -   **R** (*SHOPT_REGRESS*)                                  
-   *version*\-- a lowercase letter signifying major release     
    points. An optional **-** following *features* signifies an  
    alpha release. The first stable release has no **-**. An     
    optional **+** signifies a stable release with bug patches   
    and minor enhancements.                                      
-   *release*\-- the release date in *YYYY-MM-DD* form. This date
    corresponds to AST package and git repository releases.      
                                                                 
**KSH_VERSION** in a numeric context is an integer that encodes  
the release *YYYYMMDD*.                                          
                                                                 
### What new features are planned for ksh?                               

We are in the early stage of planning but the likely additions   
are namespaces, ability to read XML and JSON object into shell   
variables, and handling of queued signals. Support for           
multi-threading is also being considered.                        
                                                                 
### Is KornShell public domain?                                          

Yes, the language description is public domain and can be        
reimplemented. Some of the KornShell language features have been 
reimplemented in the GNU shell, bash, in zsh and mksh, and in    
pdksh, a public domain implementation.                           
                                                                 
### Is ksh public domain?                                                

No, earlier versions were owned by both AT&T and Novell. The 1993
version is owned by both Lucent and AT&T.                        
                                                                 
### Is source code available?                                            

Starting in March 2000, the ksh93 source is available as part of 
a larger collection of software called the ast-open software     
package which can be downloaded from the [github page](https://github.com/att/ast).
                                                                 
### What are the licensing terms?                                        

The exact license terms can be found on the [licence page](https://github.com/att/ast/blob/master/LICENSE.md).
                                                                 
### Does the license allow binaries to be freely redistributed?          

Yes, provided you make the license terms available to everyone   
you distribute binaries to.                                      
                                                                 
### If I make changes to the code, do I have to make them public?        

No, you do not have to make them public. However, if you         
distribute the changes, you must allow us to be able to get these
changes and distribute them along with the source.               
                                                                 
### Why do some vendors still ship ksh88, not ksh93?                     

Since ksh88 was included in System V release 4, most vendors have
just included this version. However most Linux systems and Mac OS
provide ksh93 version \'s\' or later. Solaris11 uses ksh93 as    
/bin/sh.                                                         
                                                                 
### Do you provide support for ksh?                                      

No, we will try to fix any bugs we hear about in future releases,
but we do not provide any official support.                      
                                                                 
### Is ksh supported commercially?                                       

Software vendors that supply ksh with their systems typically    
support it for that system.                                      
                                                                 
### What is pdksh and is it related to ksh or KornShell?                 

pdksh is a public domain version of a UNIX shell that is         
unrelated to ksh. It supports most of the 1988 KornShell language
features and some of the 1993 features. Some KornShell scripts   
will not run with pdksh.                                         
                                                                 
### How is the MKS Toolkit KornShell related to KornShell?               

MKS Toolkit KornShell is a completely independent implementation 
that supports a subset of the 1988 KornShell language.           
                                                                 
### What systems does ksh run on?                                        

ksh has been written to be portable. It has been ported to       
virtually run on every known UNIX system. In addition, it runs on
non-UNIX systems such as IBM\'s MVS using OpenEdition, and       
Microsoft\'s Windows 9X, Windows NT and Windows 2000. ksh is part
of the UWIN (Unix for Windows) software,                         
                                                                 
### Does ksh conform to the IEEE POSIX and ISO shell standard?           

The 1993 version should conform to the 1992 standard. At one     
point it had passed the test suite created by X/OPEN.            
                                                                 
### Will KornShell 88 scripts run with KornShell 93?                     

In almost all cases, the answer is yes. However, the IEEE POSIX  
and ISO standards required a few changes that could cause scripts
to fail. There is a separate document that lists all known       
incompatibilities.                                               
                                                                 
### Can ksh run as /bin/sh?                                              

We have installed ksh as /bin/sh on several systems without      
encountering any problems. It is /bin/sh on Solaris11. Our Linux 
systems use this instead of bash.                                
                                                                 
---
                                                                 
## Interactive
                                                                 
### How do I get separate history files for shell?                       
                                                                 
ksh uses a shared history file for all shells that use the same      
history file name. This means that commands entered in one window    
will be seen by shells in other windows. To get separate windows, the
HISTFILE variable needs to be set to different name before the first 
history command is created.                                          
                                                                 
### How do I get the time of day in my prompt?                           
                                                                 
You can use printf with supports the %T format for time and date     
formatting. For example, the format %(%H:%M:%S)T specifies time in   
hour, minute, second format and if no argument is specified, the     
current time is used. Thus setting PS1=\'\$(printf \"%(%H:%M:%S)T\"  
\$\' will output the time of day before the \$ prompt.               
                                                                 
### Why does the screen width not function correctly when non-printing characters are in my prompt?                                         
                                                                 
The shell computes the screen width by subtracting the width of the  
prompt from the screen width. To account for non-printing characters,
for example escape sequences that display in the title bar, follow   
these characters with a carriage return. The shell starts recomputing
the width after each carriage return.                                
                                                                 
### What is the PS4 prompt and how is it used?                           
                                                                 
The PS4 prompt is evaluated and displayed before each line when      
running an execution trace. If unset, a + and a \<space\> will be    
output before each line in the trace. Putting \'\$LINENO\' inside PS4
will cause the line number to be displayed. Putting \'\$SECONDS\' in 
the PS4 prompt will cause the elapsed time to be displayed before    
each line. Note that single quotes are used to prevent the expansion 
from happening when PS4 is defined.                                  
                                                                 
### How is keybinding done?                                              
                                                                 
ksh93 provides a KEYBD trap that gets executed whenever a key is     
entered from the keyboard. Using this trap, and the associative array
feature of ksh93, a keybind function can easily be written which will
map any entered key sequence to another key sequence.                
                                                                 
### How do I get the arrow keys to work?                                 
                                                                 
Starting with the \'h\' point release, on most keyboards you do not  
have to do anything to get the arrow keys to work. However, if they  
do not generate standard escape sequences, then you will have to use 
a keybinding function to get them to work.                           
                                                                 
### Does ksh support file name completion?                               
                                                                 
Yes, it does. The default key binding is \<ESC\>\<ESC\> however,     
starting with the \'g\' point release, \<TAB\> also works for        
completion.                                                          
                                                                 
### Does ksh support command completion?                                 
                                                                 
If you perform completion on the first word of a command, ksh will do
completion using aliases, functions, and commands.                   
                                                                 
### Is completion programmable?                                          
                                                                 
Yes, using the key binding mechanism, you can script the behavior of 
any key and therefore cause the current contents of any line to be   
replaced by any other line.                                          
                                                                 
### Is there any way to get the command-line editor to go to more than a single line?                                                         
The multiline option (now on by default) allows lines longer than the
width of the screen to be displayed on multiple lines on the screen. 
Also in vi-mode, if you hit \'v\' while in control mode, it will     
bring up a full screen version of vi on the current command. The     
command will execute when you exit vi.                               
                                                                 
### What is predictive editing?                                          
                                                                 
In 2010, a compile option was added that cause the shell to try to   
predict what you were trying to type by looking in the history file  
for all lines that matched and presenting them as a menu. Any line   
starting with \# would use the characters you type to find matching  
lines from the history file. If you find the line you wanted, you can
enter the number followed by \<TAB\> or newline. However bugs in     
earlier version led to core dumps.                                   
                                                                 
### Can I use the shell line editor on other commands?                   
                                                                 
The command ie, that comes along with shell, can be used to run line 
input oriented commands with command line editing.                   
                                                                 
### When I do echo \$?, I am getting 267. What does this mean?           
                                                                 
ksh93 reports process that terminate with a signal as 256+signo.     
Earlier versions used 128+signo but this makes it impossible to      
distinguish from a command exit with that value. If you run          
                                                                 
```                                                               
kill -l $?                                                       
```                                                               
                                                                 
on this signal number, it will give the name of the signal that      
caused this exit.                                                    
                                                                 
### When I type builtin, I notice that some of these are full pathnames. What does this mean?                                                 
                                                                 
Builtins that are not bound to pathnames are always searched for     
before doing a path search. Builtins that are bound to pathnames are 
only executed when the path search would bind to this pathname.      
                                                                 
### What is a self generating man page?                                  
                                                                 
A self generating man page is one that is generated by the option    
parser within that command using an extended version of the getopts  
function. The man page can be generated in html, troff, or directly  
for the terminal. Most builtin commands in the shell have self       
generating man pages so that you can run for example, **kill \--man**
or **kill \--html** to get the description of kill to the screen or  
as an html file. All self-documenting output is to the standard      
error, so you must redirect 2\>\... to capture the output.           
                                                                 
This same method can also be used for shell scripts. Run **getopts   
\--man** for more details.                                           
                                                                 
### What is autoloading?                                                 
                                                                 
Autoloading was a method used in ksh88, and still permitted in ksh93 
to declare that a name corresponded to a function. The function would
be loaded and executed when first referenced. This was necessary     
since FPATH was always searched after PATH with ksh88 and therefore  
if you defined a function whose name was the same as that of a       
program on your path, the program on your path would have been       
executed. With ksh93, when a pathname is encountered that is on PATH,
but also is in FPATH, this directory is assumed to be a function     
directory. Thus, you can have function directories searched before   
program directories so that autoloading is no longer needed.         
                                                                 
### Why does the output from \'time command 2\> file\' come out on the screen?                                                              
The time command is a compound command in ksh and time is a reserved 
word It can be followed by any pipeline. Thus, redirections applied  
at the end are for the command, not to time itself. You can use time 
{\...;} 2\> file to capture the timing output to a file. Note, that  
with ksh, time works with all commands, for example, time for i; do  
xxx;done.                                                            
                                                                 
### When I run \'mv \* ../elsewhere\' I so that get \'-ksh: mv: cannot   execute \[Arg list too long\]\', what causes this?                   
                                                                 
UNIX systems have a limit to the space consumed by command arguments 
and environment variables when running commands that are not built   
into the shell. The configuration parameter ARG_MAX defines this     
limit. You can run \'getconf ARG_MAX\' to find the limit for your    
system. Note that the shell expands \* to the list of files in the   
current directory before running mv. In many case the xargs or tw    
command can be used to work around this problem by splitting the line
into chunks and invoking the command. Another way to work around this
limit is to make the command a builtin. On systems in which the cmd  
library is installed, you can invoke \'builtin -f cmd mv\' to make mv
a shell builtin in which case the line length limit no longer        
applies. Another alternative is to use a for loop and invoke the mv  
command for each file, for example, \'for i in \*;do mv \$i          
../elsewhere;done\'. Starting with ksh93o+, a new feature was added  
to ksh to overcome this limit in some cases. If a command is preceded
by \'command -x\', and it fails because there are two many arguments,
the command will be run multiple times with subsets of the arguments.
However, the change in ksh93o+ does not work in the above case       
because the ../elsewhere is not used for each subset. This problem   
was resolved starting in ksh93p so that command -x mv \* ../elsewhere
should work. Note that it is possible to do alias mv=\'command -x    
mv\'                                                                 
                                                                 
### Is there any way to generate the list of .c files in the current directory and all the subdirectories?                                
                                                                 
Starting with ksh93o+, the globstar option (set -G or set -o         
globstar) was added. With globstar enabled, \*\* by itself matches   
zero or more directories or files, and \*\*/ matches zero or more    
directories so that \*\*/\*.c will match all .c files under the      
current directory.                                                   
                                                                 
### Is there any way to prevent sending a HUP signal to a job when I log out if I didn\'t nohup the job?                                      
                                                                 
Yes, the disown command tells ksh not to forward the HUP signal to   
the specified jobs when it disconnects.                              
                                                                 
---
                                                                 
## Programming
                                                                 
### What is the difference between \* and @, for example, and ?          
                                                                 
When used outside of \"\", they are equivalent. However, within      
double quotes, \"\$@\" produces one argument for each positional     
parameter, and \"\$\* produces a single argument. Note that \"\$@\"  
preserves arguments lists, whereas \$\* may not unless both word     
splitting and pathname expansion are disabled.                       
                                                                 
### Why do I need spaces around { and } but not around ( and )?          
                                                                 
The characters ( and ) are shell metacharacters and are always       
treated specially. For historical reasons, { and } were treated as   
reserved words and are only special as separate words at locations in
which a command can begin.                                           
                                                                 
### How do I get read to maintain the \\ characters?                     
                                                                 
Use read -r instead.                                                 
                                                                 
### How can I a write a ksh script that responds directly to each character so that you user just has to enter y, not y\<return\>?     
                                                                 
There are two ways to do this. The easiest is to use                 
                                                                 
```                                                               
read -n1 x                                                       
```                                                               
                                                                 
Alternatively, you could do                                          
                                                                 
```                                                               
function keytrap                                                 
{                                                                
    .sh.edchar=${sh.edchar}$'                                    
}                                                                
trap keytrap KEYBD                                               
```                                                               
                                                                 
and then                                                             
                                                                 
```                                                               
read x                                                           
```                                                               
                                                                 
### What is the purpose of \$\'\...\'?                                   
                                                                 
The \$\'\...\' string literal syntax was added to ksh93 to solve the 
problem of entering special characters in scripts. It uses ANSI C    
rules to translate the string between the \'\...\'. It would have    
been cleaner to have all \"\...\" strings handle ANSI C escapes, but 
that would not be backward compatible.                               
                                                                 
### What is the -n option used for?                                      
                                                                 
You should always run ksh -n on each script you write. The -n option 
will check for syntax errors on paths that might not even be checked 
when you run the script. It also produces a number of warning        
messages.                                                            
                                                                 
### Why are both \`\...\` and \$(\...) used for command substitution?    
                                                                 
The \`\...\` method has some rather strange quoting rules and does   
not nest easily. \$(\...) was added to ksh88 to make command         
substitution easy to use. \`\...\` is provided for backwards         
compatibility only.                                                  
                                                                 
### How can I tell if all the commands of a pipeline have succeeded?     
                                                                 
The pipefail option was added to the \'g\' point release of ksh93.   
With pipefail set, a pipeline will fail if any element of the        
pipeline fails. The exit status will be that of the first command    
that has failed.                                                     
                                                                 
### What is the difference between \[\...\] and \[\[\...\]\]?            
                                                                 
The \[\[\...\]\] is processed as part of the shell grammar whereas   
\[\...\] is processed like any other command. Operators and operands 
are detected when the command is read, not after expansions are      
performed. The shell does not do word splitting or pathname          
generation inside \[\[\...\]\]. This allows patterns to be specified 
for string matching purposes. You should use \[\[\...\]\] instead of 
\[\...\] and test.                                                   
                                                                 
### How come \[\[ \$foo == \$bar \]\] is true and \[\[ \$bar == \$foo \]\] is false?                                                       
The == operator is not symmetrical. It takes a string on the left and
a pattern on the right. However, if you double quote the right hand  
side, which removes the special meaning of pattern match characters, 
then this becomes a string comparison so that \[\[ \"\$foo\" ==      
\"bar\" \]\] and \[\[ \"\$bar\" == \"\$foo\" \]\] are equivalent.    
                                                                 
### Why does ksh93 have print since echo already exists and is widely used?

The behavior of echo varies from system to system. The POSIX standard
does not define the behavior of echo when the first argument beings  
with a - or when any argument contains a  character. This makes echo 
pretty useless for use in portable scripts.                          
                                                                 
### What is \$bar after running \'echo foo \| read bar\'?                
                                                                 
The answer is foo. ksh runs the last component of a pipeline in the  
current process. Some shells run it as a subshell as if you had      
invoked it as echo foo \| (read bar).                                
                                                                 
### How can I access a substring of a variable?                          
                                                                 
The syntax \${varname:offset:len} can be used to generate the string 
of length len starting at the specified offset. String offsets start 
at 0. If :len is omitted, then the remainder of the string will be   
used. Both offset and len can be arithmetic expressions. A negative  
offset is subtracted from the last offset.                           
                                                                 
### What is the difference between ((expr)) and \$((expr))?              
                                                                 
((expr)) is a command that evaluates an arithmetic expression. The   
exit status of this command is 0 if the expression evaluates to      
non-zero and is 1 if it evaluates to 0. 0 is an string expansion that
expands to a string representation of the value of this arithmetic   
expression. It can be used anywhere a variable substitution is       
permitted.                                                           
                                                                 
### What is the difference between \$((x\*y)) and \$((\$x\*\$y))?        
                                                                 
In the first case the value of x and the value of y are multiplied   
together, and then their result is converted to a string. In the     
second case variables \$x, \*, and \$y are concatenated to form an   
arithmetic expression which is then evaluated. This can yield        
different results, for example,                                      
                                                                 
```                                                               
x=2+3 y=4+5                                                      
print $((x*y)) \$(($x*$y))                                       
45 19                                                            
```                                                               
When x and y are numeric the first form is recommended for better
performance.                                                     
                                                                 
### How do I handle filenames with spaces in them?                       
                                                                 
To be POSIX conforming, ksh has to do word splitting and pathname    
expansion the results of substitutions. You can enclose variable     
substitutions in \"\...\" to prevent both word splitting and pathname
expansion. Alternatively, you can disable word splitting by setting  
IFS=\'\' and pathname generation with set -o noglob.                 
                                                                 
### What are active variables?                                           
                                                                 
By default shell variables are passive. They hold values given to    
them on assignment, and return values on reference. Active variables 
allow the assignment and reference (and other actions) be controlled 
by functions specific to that variable. At the shell level, a        
\'get\', \'set\', or \'unset\' shell function can be defined for any 
variable to make them active, so that the function foo.set will be   
invoked whenever the variable foo is assigned a value. At the C      
interface level, several functions can be stacked together for an    
active variable.                                                     
                                                                 
### What is the difference between function name and name()?             
                                                                 
In ksh88 these were the same. However, the POSIX standard choose     
foo() for functions and defined System V Release 2 semantics to them 
so that there are no local variables and so that traps are not       
scoped. ksh93 keeps the ksh88 semantics for functions defined as     
function name, and has changed the name() semantics to match the     
POSIX semantics. Clearly, **function** *name* is more useful.        
                                                                 
### What is the naming conventions for files in FPATH and can one file contain more than one function definition?                           
                                                                 
You can have more than one function defined in each file defined in  
FPATH and all of them will be added to the list of known functions.  
Any commands placed in this file outside of function definitions will
be invoked first. The name of the file must be that of the first     
function you invoke. If you have several functions defined in one    
file, then you should create a link to each of the function names    
that can potentially be invoked first.                               
                                                                 
### What are name reference variables and how are they used?             
                                                                 
Reference variables are variables in which all references and        
assignments refer to the variable that they reference. For example,  
                                                                 
```                                                               
typeset -n name=$1                                               
name=value                                                       
```                                                               
                                                                 
is equivalent to                                                     
                                                                 
```                                                               
eval \$1='value'                                                 
```                                                               
                                                                 
References are most useful for passing arguments such as arrays to   
functions.                                                           
                                                                 
If i=1 and var1=some value, how do I print var\$i to get its value?  
                                                                 
Either use                                                           
                                                                 
```                                                               
eval print var\$i                                                
```                                                               
                                                                 
or                                                                   
                                                                 
```                                                               
typeset -n x=var$i                                               
print $x                                                         
```                                                               
                                                                 
### How can I shift the elements of an array?                            
                                                                 
The shift special builtin-command only works for positional          
parameters. However, noting that array subscripts start at 0, you can
use                                                                  
                                                                 
```                                                               
typeset -A name "${name[@]:1}"                                   
```                                                               
                                                                 
to shift the array.                                                  
                                                                 
### Why are the braces required with array references, e.g. \${x\[1\]}?  
                                                                 
It would be nice to do \$x\[1\], but the POSIX shell would expand \$x
and then search for the file pattern resulting by concatenating      
\[1\]. ksh is POSIX compatible.                                      
                                                                 
### How do I get the list of subscript names for an associative array?   
                                                                 
The prefix operator ! in variable expansions can be used to get      
names. To get the names of subscripts for an array, associative or   
indexed, use \${!var\[@\]}.                                          
                                                                 
### How do I do global substitutions on the contents of shell variables? 
                                                                 
Use // instead of / for global substitution, \${var//aa/bb} will     
expand to the value of var with each \"aa\" replaced by \"bb\".      
                                                                 
### How can I convert %XX values to ASCII?                               
                                                                 
You can convert this to a sequence of ANSI C strings and then eval   
that string, for example suppose the variable \'foo\' contains %XX   
strings, then                                                        
                                                                 
```                                                               
eval print -r -- "\$'${foo//'%'@(??)/'\x\1"'\$'"}'"              
```                                                               
                                                                 
will print out the string in ASCII.                                  
                                                                 
### I want to use exec to open a file. How do I prevent the script from exiting if the exec fails?                                           
                                                                 
If you run                                                           
                                                                 
```                                                               
command exec ...| error ...
```                                                               
                                                                 
then error will be executed if the exec fails, but the script will   
not terminate. The command builtin will prevent the shell from       
exiting when special built-ins fail.                                 
                                                                 
### How do I execute a builtin inside a function of the same name?       
                                                                 
You use the command builtin for this. For example,                   
                                                                 
```                                                               
function cd                                                      
{                                                                
    command cd "$@" && title "$PWD"                              
}                                                                
```                                                               
                                                                 
will run the builtin command cd from within the function cd rather   
than calling the function cd recursively.                            
                                                                 
### How are variables scoped in ksh?                                     
                                                                 
The scoping of variables was not defined for ksh88 but in ksh93      
static scoping was specified. For example the output from            
                                                                 
```                                                               
function f1                                                      
{                                                                
    print foo=$foo                                               
}                                                                
function f2                                                      
{                                                                
    typeset foo=local                                            
    f1                                                           
}                                                                
foo=global                                                       
f2                                                               
```                                                               
                                                                 
will be \"global\". To get f2 to cause f1 to print the local value of
foo, f2 can run \"foo=\$foo f1\" instead.                            
                                                                 
### Can you write a self reproducing program in KornShell?               
                                                                 
Yes, the following program is self reproducing. Any shorter ones?    
                                                                 
```                                                               
n="                                                              
" q="'                                                           
" x="cat <<-!" y=! z='n="$n" q="$q" x="$x" y=$y z=$q$z$q$n$x$n$z$n$y'
cat <<-!                                                         
n="$n" q="$q" x="$x" y=$y z=$q$z$q$n$x$n$z$n$y                   
!                                                                
```
                                                                 
## Redirections
                                                                 
### How do I redirect both standard input and standard output to a file? 

Add the following redirections to the command. \> file 2\> &1.   
This will redirect standard output (file descriptor 1) to        
\"file\" and standard error (file descriptor 2) to the same place
as file descriptor 1. ksh redirection allows you to redirect any 
single digit file descriptor by putting the descriptor number in 
front of the redirection operator with no intervening space.     
                                                                 
### Is there a way for the shell to pick the file number when I open a file?

Yes, a redirection operator operator can be preceded by {n}      
without any intervening space where n is the name of a variable. 
The file descriptor will be placed in variable n.                
                                                                 
### How do I connect to a socket from a shell script?                    

exec 3\<\> /dev/tcp/hostname/portnum will open a tcp connection  
to portnum on hostname for reading and writing on file           
descriptor 3. You can then use read and print statements with    
file descriptor 3, or redirection operators \<&3 or \>&3 to use  
these connections.                                               
                                                                 
### How do I seek to a given location in a file?                         

The redirection operators \<# and \># allow you to seek to a     
specified location in a file. The operator can be followed by an 
arithmetic expression contained in ((\...)). The variables CUR   
and EOF can be used in the arithmetic expression to get relative 
locations or locations relative to the end of file respectively. 
Alternatively, \<# and \># can be followed by a shell pattern. In
this case, the file will be positioned to beginning of the next  
line containing this pattern.                                    
                                                                 
### What is the \<\<\< redirection operator?                             

It denotes a here-document in which the document is contained the
argument that follows \<\<\< and therefore there is no delimiter.
                                                                 
### What is the \>; redirection operator?                                

This operator writes the output into a temporary file in the same
directory as the file specified after \>;. If the command        
completes successfully, then the file is replaced. Otherwise, the
original file is unchanged and the temporary file removed.       
                                                                 
### What is the \<\>; redirection operator?                              

The file is opened for reading and writing as with \<\>. However,
when the file is closed it is truncated to the its current       
location.                                                        
                                                                 
---
                                                                 
## Extensions
                                                                 
### Is there a shell compiler?                                           

There is a separate command named shcomp that will convert a     
script into an intermediate machine independent form. The shell  
will detect this format whenever it runs a script and execute    
directly from this intermediate format.                          
                                                                 
### What is the advantage of making commands built-in?                   

The startup time is reduced by a couple of orders of magnitude.  
In addition, built-in commands can access ksh internals.         
                                                                 
### What is the disadvantage of making commands built-in?                

Errors in these built-ins can cause the shell to crash.          
                                                                 
### How do I add built-in commands?                                      

There are two ways to do this. One is write a shared library with
functions whose names are b_xxxx where xxxx is the name of the   
builtin. The function b_xxxx takes three arguments. The first two
are the same as a mail program. The third parameter is a pointer 
argument which will point to the current shell context. The      
second way is to write a shared library with a function named    
lib_init(). This function will be called with an argument of 0   
after the library is loaded. This function can add built-ins with
the sh_addbuiltin() API function. In both cases, the library is  
loaded into the shell with the \"builtin\" utility.              
                                                                 
### Can ksh93 be embedded?                                               

Yes, ksh93 can be compiled as a shared or dynamically linked     
library which can be embedded into applications. There is an API 
for interfacing to shell variables and to several of the internal
shell functions.                                                 
                                                                 
### Can I write GUI applications with ksh?                               

There are two extensions to ksh that can be used to write GUI    
applications as shell script. One is dtksh which was written by  
Steve Pendergrast at Novell and is included with the Common      
Desktop Environment, CDE. The other is tksh which was written by 
Jeff Korn. tksh combines the tk graphics package with ksh93 and  
reimplements the tcl language as an extension so that both tcl   
and ksh scripts can run in the same address space. The source for
tksh is included in the ast-open package.                        
                                                                 
---
      June 19, 2012                                              
---
