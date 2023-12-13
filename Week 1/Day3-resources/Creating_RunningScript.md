# Creating and running a script

## Description

This project involves creating a bash script for automating the update, upgrade, installation of nginx, and restarting/enabling the nginx service on a Linux system. Additionally, we have explored ways to test our commands within the script.

## Installation

1. Create a new bash script file named `provision.sh`:

    ```bash
    touch provision.sh
    ```

2. Open the script file in text editor and plan the script.

## Bash Script Planning

Plan the content of `provision.sh` to include the following commands:

```
#!/bin/bash

# Update
sudo apt update -y

# Upgrade
sudo apt upgrade -y

# Install Nginx
sudo apt install nginx -y

# Restart Nginx
sudo systemctl restart nginx

# Enable Nginx
sudo systemctl enable nginx
```


## Testing Steps
Test each command individually to ensure they work as expected prior to the execusion of `provision.sh`.

```
# Test update
sudo apt update -y

# Test upgrade
sudo apt upgrade -y

# Test Nginx installation
sudo apt install nginx -y

# Test Nginx restart
sudo systemctl restart nginx

# Test Nginx enable
sudo systemctl enable nginx
```

After testing each command manually, make sure they execute without errors!

## Echo
Use echo to output informative messages within the script to enhance visibility and understanding.
```
# Example echo statements
echo "Updating system..."
sudo apt update -y
echo "Done!"
echo "" (used to create space between each execution)
```

## Running the Script
Make the script executable:
```
sudo chmod +x provision.sh
```

Run the script:
```
./provision.sh
```

## Testing the Automation
After running the script, manually verify the Nginx status to ensure it is active and enabled:
```
sudo systemctl status nginx
```

Confirm that Nginx is functioning as expected.

## Take-Away Notes
- Ensure proper permissions when running the script. Command ls -l
- Always review and understand scripts before execution.
- An operation or command is idempotent on Linux if executing it multiple times has the same effect as executing it once, ensuring the system remains in the same state regardless of the number of repetitions;