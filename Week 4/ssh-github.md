# Setup the SSH to push to GitHub

## 1. Change directory into the .ssh folder
```
cd .ssh
```

## 2. Generate an SSH key
```
ssh-keygen -t rsa -b 4096 -C "biancaaandrei@yahoo.com"
```
### Enter file in which to save the key (/c/Users/bianc/.ssh/id_rsa): bianca-github-key

### Push enter for the passphrase

### Go on GitHub and generate a new ssh key:
github>settings>ssh and gpg keys>new ssh key

### Get the public key from .ssh file: 
```
cat bianca-github-task-key.pub
```

### Add the SSH key to the SSH agent
```
eval `ssh-agent -s`
```

```
ssh-add bianca-github-task-key
```

### Test the connection with GitHub
```
ssh -T git@github.com
```

### Repository Creation and Push

## 3. Navigate to the local directory where you want to create the repository
```
cd ~/Desktop/Sparta Projects
```

## 4. Create a new directory for the repository
``` 
mkdir tech242-ssh
```

## 5. Change into the repository directory
```
cd tech242-ssh
```

## 6. Add a line to the README.md file
```
echo "# push using ssh for the afternoon task" >> README.md
```

## 7. Initialize a new Git repository
```
git init
```

## 8. Add all files to the staging area
```
git add .
```

## 9. Commit the changes
```
git commit -m "Initial commit message"
```

## 10. Rename the default branch to "main"
```
git branch -M main
```

## 11. Add the GitHub repository as the remote origin
```
git remote add origin git@github.com:BiancaaaaAndrei/tech242-ssh.git
```

## 12. Push the changes to GitHub
```
git push -u origin main
```

