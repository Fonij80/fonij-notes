---
title: "Initial Set Up"
lang: en
handle: intial-set-up
layout: default
---

# Chapter 1: Initial Set Up

- Initial set up of every new technology you learn, is a headache but you have to do it once correctly to avoid further headaches.

- Learning Goals:
  - What is Shell?
  - Most used shell commands
  - Install Python
  - Set up virtual environment
  - Use git as version control

## What is Shell?

    - Command line:
        text-only interface,
        used for executing programs, installing software, using Git, connecting to servers in the cloud
        terms refer to the command line:
            Command Line Interface (CLI)
            Console: text-based app
            Terminal: program that opens up a new window to access CL
            Shell: program that runs commands on the underlying OS
            Prompt: where commands are typed and run, $ for Linux prompt, > for Windows and % for macOS.
            PowerShell: built-in terminal & shell on windows
            Terminal: built-in terminal on mac & linux

    - Shell Access:
        - Windows:
            search for “PowerShell” in taskbar search
        - Ubuntu & Mac:
            search for “terminal”,
            Ctrl + Alt + T in ubutnu

    - A Mac Tip:
        Since 2019, zsh is the default macOS shell (% prompt).
        Bash is the previous default macOS shell ($ prompt).

## Most used shell commands

    $ whoami: computer name/username
    $ # some command: not executed, # comment symbol
    $ echo “Hi!”: print sth
    $ pwd: print working dir
    $ cd {dir's_name}: change dir
    $ mkdir {dir's_name}: make new dir
    $ ls: list the dir/file
    $ clear: clear the terminal
    $ exit: close the terminal


    - Command autocomplete: > key in windows, tab in linux/mac
    - ↑ and ↓ keys cycle through previous commands

    * For more commands: https://ss64.com/

## Install Python

    - On Windows: Type “python” in the search bar and select the latest version of Python on the Microsoft Store and to download it.

To confirm that Python is installed correctly, open a new Terminal window with
PowerShell and type python --version. Then, type python to open the Python
interpreter from the command-line shell. You can exit the Python interpreter by typing either exit() or Ctrl-Z plus
Return.

    - On Mac: On Mac, the official installer on the Python website is the best approach. In a

new browser window, go to the Python downloads page and click on the button
underneath the text “Download the latest version for Mac OS X.” As of this
writing, that is Python 3.12. The package will be in your Downloads directory:
double-click on it to launch the Python Installer, and follow the prompts.
To confirm the download was successful, open a new Terminal window and type
python3 --version.
