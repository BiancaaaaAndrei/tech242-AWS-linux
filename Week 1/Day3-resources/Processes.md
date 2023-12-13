# Processes Documentation

## Introduction

This documentation provides an overview of working with processes in a Linux environment, demonstrated through terminal commands.

## Commands and Explanations


## Display help information for the 'ps' command
```
ps --help
```
Displays the help information for the `ps` command, providing details about its usage and available options.

## Display simplified help information for the 'ps' command
```
ps --help simple
```
Displays simplified help information for the `ps` command, offering a quick reference for common options and syntax.

## List all currently running processes
```
ps -e
```
Lists all currently running processes on the system, providing essential information such as Process ID (PID), terminal, CPU and memory usage.

## Access the manual page for the 'ps' command
```
man ps
```
Opens the manual page for the `ps` command, offering in-depth documentation, usage guidelines, and details on various options.

## List files in the current directory
```
ls
```
Lists files in the current directory, demonstrating a command unrelated to processes but included for context.

## Clear the terminal screen
```
clear
```
Clears the terminal screen, providing a clean slate for improved visibility and organization of commands and outputs.


## Display a detailed list of all processes
```
ps aux
```
Displays a detailed list of all processes, including user, resource usage, and additional information. The `aux` options provide an extensive view.

## Display a dynamic view of system processes with 'top'
```
top
```
Launches a dynamic, real-time view of system processes, continuously updating to reflect changes and resource utilization.

## Pause execution for 3 seconds
```
sleep 3
```
Pauses execution for 3 seconds, simulating a short-duration process or introducing delays in script execution.

## Start a background process that sleeps for 5000 seconds
```
sleep 5000 &
```
Starts a background process that sleeps for 5000 seconds, demonstrating background job execution and the use of the ampersand (`&`) to run processes in the background.

## Display information about background jobs
```
jobs
```
Displays information about background jobs, including their status, providing visibility into currently running background processes.

## Display a detailed list of all processes, including the background job
```
ps aux
```
Executes the `ps aux` command again to display an updated list of processes, including any changes after running background processes.

## Terminate the background process with PID 1786
```
kill 1786
```
Terminates the background process with PID 1786, showcasing the use of the `kill` command to end a specific process.

## Display a detailed list of all processes after terminating the job
```
ps aux
```
Displays an updated list of processes after terminating the background job, reflecting the changes made by the `kill` command.


