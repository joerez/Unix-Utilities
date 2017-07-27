# Unix Utilities

_More powerful than the spiky blue shell_

## Challenges, Part 1

Challenges within each section are meant to be solved in order.

### Navigation

1.  Print the path of your working directory
    -   `pwd`
1.  List the files in your working directory
    -   `ls`
1.  List the files with a particular extension, like `.txt`
    -   `ls *.txt`
1.  List the files in a subdirectory, like `project`
    -   `ls project`
1.  Navigate to a subdirectory, like `project`
    -   `cd project`
1.  Navigate to the parent directory of your working directory
    -   `cd ..`
1.  Navigate to a nested subdirectory, like `path/to/project`
    -   `cd path/to/project`
1.  Navigate to your home directory
    -   `cd ~`
    -   `cd`
1.  Navigate back to the previous directory
    -   `cd -`

### Variables

1.  Print a sentence, like `Hello world`
    -   `echo "Hello world"`
1.  Print a variable value, like `$USER` or `$PATH`
    -   `echo $USER`
    -   `echo $PATH`
1.  Set a variable `NAME` equal to your first name, then print its value
    -   `NAME=Firstname`, then `echo $NAME`
1.  Set a variable `FULL_NAME` equal to your full name, then print its value
    -   `FULL_NAME="Firstname Lastname"` (quotes matter), then `echo $FULL_NAME`
1.  Print all environment variables (names and values)
    -   `env`
1.  Make an alias named `hello` that prints `Hello world`
    -   `alias hello='echo "Hello world"'`
1.  Make an alias named `gocode` that navigates to your code directory
    -   `alias gocode='cd ~/MakeSchool/Code'`
1.  Print all aliases (names and values)
    -   `alias`

### Getting Help

1.  Print what options a command accepts, like `bash` or `python`
    -   `bash --help`
    -   `python --help`
1.  Read the manual for a command, like `echo` or `ls`
    -   `man echo`
    -   `man ls`
1.  Print the file path to a command, like `bash` or `python`
    -   `which bash`
    -   `which python`

### Files

1.  Navigate to the directory `animals`
    -   `cd animals`
1.  Print the contents of the file `cats.txt`
    -   `cat cats.txt`
1.  Print the contents of both files `cats.txt` and `dogs.txt`
    -   `cat cats.txt dogs.txt`
1.  Count the words in the file `cats.txt`
    -   `wc cats.txt`
1.  Count the words in all files with the extension `.txt`
    -   `wc *.txt`
1.  Copy the file `dogs.txt` to a new file `baby_dogs.txt`
    -   `cp dogs.txt baby_dogs.txt`
1.  Rename the file `baby_dogs.txt` to `puppies.txt`
    -   `mv baby_dogs.txt puppies.txt`
1.  Make a new directory named `shelter` inside `animals`
    -   `mkdir shelter`
1.  Move the file `puppies.txt` into the directory `shelter`
    -   `mv puppies.txt shelter`
1.  Copy the file `cats.txt` to `kittens.txt` inside `shelter`
    -   `cp cats.txt shelter/kittens.txt`
1.  List the files within the directory `shelter`
    -   `ls shelter`
1.  Count the words in all `.txt` files inside `shelter`
    -   `wc shelter/*.txt`
1.  Try to remove the directory `shelter` (this should fail)
    -   `rmdir shelter` (this should fail)
1.  Remove all `.txt` files inside `shelter`
    -   `rm -i shelter/*.txt`
1.  Remove the directory `shelter` (this should succeed)
    -   `rmdir shelter`
    -   `rm -iR shelter` (`-R` specifies recursive file removal)
1.  Now cry because you just deleted those poor tiny animals
    -   `:'-(`

### Permissions

1.  Print out your user name
    -   `whoami`
    -   `echo $USER`
1.  List the permissions (and metadata) of all `.txt` files
    -   `ls -l *.txt`
1.  Give all users write permission on the file `cats.txt`
    -   `chmod a+w cats.txt`
1.  List the permissions (and metadata) of the file `cats.txt`
    -   `ls -l cats.txt`
1.  Change the owner of the file `cats.txt` to another user
    -   `chown otheruser cats.txt`
1.  Now list the permissions (and owner) of the file `cats.txt`
    -   `ls -l cats.txt`
1.  Try to change the owner of the file `cats.txt` back to yourself
    -   `chown $USER cats.txt` or `chown $(whoami) cats.txt`
1.  Invoke the super-user to make the previous command succeed
    -   `sudo chown $USER cats.txt`
    -   `sudo !!` (but be careful!)
1.  List the permissions (and owner) of the file `cats.txt` again
    -   `ls -l cats.txt`

## Challenges, Part 2

These challenges utilize more sophisticated Unix utilities. Challenges within each section are meant to be solved in order.

### Streams

1.  Print a sentence like `Hello world` into a file named `test.txt`
    -   `echo "Hello world" > test.txt`
1.  Print another sentence `Hola Mundo` on a new line of `test.txt`
    -   `echo "Hola Mundo" >> test.txt`
1.  Print the contents of the file `test.txt`
    -   `cat test.txt`
1.  Print the contents of the file `numbers.txt`
    -   `cat numbers.txt`
1.  Print the first 10 lines in the file `numbers.txt`
    -   `head numbers.txt`
1.  Print the first 5 lines in the file `numbers.txt`
    -   `head -n 5 numbers.txt`
1.  Print the last 10 lines in the file `numbers.txt`
    -   `tail numbers.txt`
1.  Print the last 5 lines in the file `numbers.txt`
    -   `tail -n 5 numbers.txt`
1.  Print lines 6 through 10 in the file `numbers.txt`
    -   `head -n 10 numbers.txt | tail -n 5`
1.  Sort all lines in the file `numbers.txt`
    -   `sort numbers.txt`
1.  Print the first 2 characters of each line in `numbers.txt`
    -   `cut -c 1-2 numbers.txt`
1.  Sort the first 2 characters of each line in `numbers.txt`
    -   `cut -c 1-2 numbers.txt | sort`
1.  Print only the unique first 2 characters of each line in `numbers.txt`
    -   `cut -c 1-2 numbers.txt | sort | uniq`
1.  Replace all `o`s with `0`s in file `test.txt`
    -   `tr o 0 test.txt`
    -   `sed -e 's/o/0/' test.txt`
1.  Capitalize all letters in the file `test.txt`
    -   `tr a-z A-Z test.txt`
1.  Capitalize the string `Hello world`
    -   `echo "Hello world" | tr a-z A-Z`

### Search

1.  Find the file named `cats.txt` in the directory `animals`
    -   `find animals -name cats.txt`
1.  Find all files ending with `.py` in your code directory
    -   `find ~/code -name '*.py'`
1.  Find all files larger than 100 MB in your movies directory
    -   `find ~/movies -size 100M`
1.  Find all lines containing the word `one` in the file `numbers.txt`
    -   `grep 'one' numbers.txt`
1.  Find the function `search` definition in a source code file
    -   `grep 'def search' ~/code/search.py`
1.  Find the function `search` definition in all source code files
    -   `find ~/code -name '*.py' | grep 'def search'`
1.  Count the lines and words in all source code files
    -   `find ~/code -name '*.py' | xargs | wc`
1.  Find all U.S. zip codes in a file containing addresses
    -   `grep '[0-9]{5}' ~/addresses.txt`
