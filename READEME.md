# **Guide to build CLI with PHP [Hypertext Preprocessor]**

   1. What is CLI [Command line interface]?

      - CLI is a command-line program that accepts text input to execute operating system functions.

   1. Why to use PHP CLI?

      - because there are several advantages in being able to run PHP code from the command line such as:
         - PHP into a general-purpose language to execute on any environment, not only on web servers.
         - no need to learn another language such as [Perl](https://www.perl.org/), [Bash](https://www.gnu.org/software/bash/), [Awk](https://www.tutorialspoint.com/awk/index.htm) or [python](https://www.python.org/)
         - running scheduled (CRON) tasks.
         - making GUI applications with [GTK](https://github.com/php/php-gtk-src).
         - reuse of your existing components.
         - write very robust scripts for your system using multi-threading capabilities.
         - access system STDIN [input], STDOUT [output], STERR [error].

## **Sample App**

![Alt Text](https://media.giphy.com/media/JauV76IyvGknqnFSxS/giphy.gif)

## **Guideline**

### **Notes**

- `in this Guide, we will use vim editor and you are free to use vscode or anything you like`
- for `php://stdin, php://stdout and php://stderr` check [Accessing various I/O streams](https://www.php.net/manual/en/wrappers.php.php)

### **Steps to create your first CLI app**

1. We need to create our executable file and protect it from running on the web servers.
   1. `vim [example] -> (filename) then press Enter` [notes that we didn't add the extension for the file for protecting it].
   1. make our file executable via our OS using the command `chmod -x example`.

1. Writing our program.
   1. start your file with the following sentence.
      - if you are following this guide using vim `press i` so you can start typing.
      - `#!/usr/bin/env php` to make our code executable via PHP installed on our machine.
      - after making sure that our program can execute our PHP code then open your PHP tag and start to write your code.

   1. Inputs
      - to read input while starting the CLI app use super global indexed array `$_SERVER["argv"]`
         - to access first input `$_SERVER["argv"][0]` the second - to access first input `$_SERVER["argv"][1]`, etc
         - to get count of the parameter passed via starting the CLI app access it using `$_SERVER["argc"]`
      - after running the CLI app can make it reactive with the user which you are building the app for him use `$input = fread(fopen('php://stdin','r'), $length);`
         - `$length -> length of bytes you want to read`
   1. Outputs
      - `echo $output|| print($output)`
      - `fwrite(fopen('php://stdout','w'), $output)`

### **Starting CLI app**

- with inputs
  - `php [example] -> (filename) input1 input2, etc`
- without inputs
  - `php [example] -> (filename)`

## **References**

- [PHP](https://www.php.net/manual/en/features.commandline.php)
- [PHP CLI](http://php-cli.com/)

## **Author**

- [Omar Hossam El-Din Kandil](https://www.linkedin.com/in/omar-hossameldin-kandil-74633a1bb/)