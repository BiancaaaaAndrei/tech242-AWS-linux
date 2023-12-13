# File Ownership and Permissions in VSCode Terminal

## Why is managing file ownership important?

Because is maintaining security and control over the files and directories. Assigning the correct owner ensures that the right individuals or processes have appropriate access to the data, helping to prevent unauthorized access and potential security risks.

## What is the command to view file ownership?
```
$ ls -l
```
This provides a detailed listing that includes information about the owner and group of each file or directory in the specified location.

## What permissions are set when a user creates a file or directory? 
- When a user creates a file or directory, the default permissions are typically set to give the owner read and write permissions. 

## Who does the file or directory belong to?
- The file or directory belongs to the user who created it, and they are assigned as the owner.

## Why does the owner, by default, not receive X permissions when they create a file?
- By default, the owner does not receive execute (X) permissions when creating a file to prevent accidental execution of files that may contain sensitive or harmful content. 
- This adds an extra layer of security by requiring explicit permission to execute a file.

## What command is used to change the owner of a file or directory?
```
chown new_owner:new_group file_or_directory
```
- Replace new_owner with the new owner's username and new_group with the new group's name. Optionally, can omit :new_group if only want to change the owner without modifying the group. 
- Additionally, may need superuser privileges (root) to change ownership of certain files or directories. In that case, use sudo:

```
sudo chown new_owner:new_group file_or_directory
```
