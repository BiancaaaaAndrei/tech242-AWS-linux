# Environment Variables Documentation

## Introduction

This documentation outlines the usage of environment variables in a Linux environment, demonstrated through terminal commands. 

## Commands and Explanations

# Print the value of the 'user' environment variable
```
printenv USER
```
The printenv command is used to display the values of environment variables and printenv USER showes the stored information about the current user.


# Assign the value 'bianca' to the 'MYNAME' environment variable
```
MYNAME=bianca
```

# Display all environment variables
```
printenv
```

# Echo the value of the 'MYNAME' environment variable
```
echo $MYNAME
```
The echo $MYNAME command prints the value of the 'MYNAME' environment variable.

# Export and assign the value 'Anamaria' to the 'MYNAME' environment variable
```
export MYNAME=Anamaria
```
Using export MYNAME=Anamaria exports 'MYNAME' to make it available in subsequent sessions.

# Display all environment variables, including the updated 'MYNAME'
```
printenv
```

# Open the .bashrc file in the nano text editor
```
nano .bashrc
```

Editing the .bashrc file with nano .bashrc allows for persistent changes to environment variables. Write export MYNAME=Bianca_is_persistent in order to create a persistent env.

# Source the .bashrc file to apply changes immediately
```
source .bashrc
```

# Print the value of the 'MYNAME' environment variable after sourcing .bashrc
```
printenv MYNAME
```
The final printenv MYNAME verifies the updated value of 'MYNAME' after sourcing .bashrc.


