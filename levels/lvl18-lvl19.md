# Bandit Level 18 → Level 19

> The password for Level 19 is stored in the `readme` file in the home directory. However, the `.bashrc` file logs users out immediately after SSH login.

## Steps

1. **Execute a Command via SSH:** Run `ssh bandit18@bandit.labs.overthewire.org -p 2220 "cat readme"` to execute `cat readme` directly on the remote server without opening an interactive shell.
2. **Retrieve the Password:** The command displays the contents of `readme`, which contains the password for Level 19.
