# Executing Linux Commands

In the Git Bash session, I executed various Linux commands to manage files and directories. Below is a concise log of the commands and their explanations:

## Basic Commands

- **ls:** List files and directories in the current location, or in long format with `-l`.
- **ls -a:** List all files, including hidden ones.
- **exit:** Exit the terminal.
- **uname:** Display system information, or get help with `--help`.
- **whoami:** Display the current user.
- **history:** Show command history.

## File and Directory Operations

- **cd .:** Change to the current directory.
- **pwd:** Print the current working directory.
- **cd ..:** Move to the parent directory.
- **cd ~:** Change to the home directory.

## Downloading Files

- **curl [URL]:** Download a file from the given URL, or download and save with `--output [filename]`.
- **ls:** List files in the current directory.
- **file [filename]:** Display file type.

## File Manipulation

- **mv [oldname] [newname]:** Rename a file.
- **cp [source] [destination]:** Copy a file.
- **rm [filename]:** Remove a file.

## Directory Management

- **mkdir [dirname]:** Create a directory, or attempt with a space in the name.
- **rmdir [directory]:** Remove an empty directory.
- **rm -r [directory]:** Remove a directory and its contents.

## Text File Operations

- **touch [filename]:** Create an empty file.
- **cat [filename]:** Display the contents of a file.
- **nano [filename]:** Open a text editor to edit a file.

## File Content Manipulation

- **head -1 [filename]:** Display the first line of a file.
- **tail -1 [filename]:** Display the last line of a file.
- **nl [filename]:** Number lines in a file.
- **cat [filename] | grep chicken:** Display lines containing "chicken."
- **cat [filename] | grep the:** Display lines containing "the."

## Directory Structure Visualization

- **tree:** Display the directory structure, or attempt to install with `apt install tree`.
- **sudo apt install tree:** Install the `tree` command with superuser privileges.
- **sudo apt update -y:** Update package information.

## System Navigation

- **pwd:** Print the current working directory.
- **cd ..:** Move to the parent directory.