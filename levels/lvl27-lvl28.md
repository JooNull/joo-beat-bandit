# Bandit Level 27 → Level 28

> The challenge provides a remote Git repository accessible over SSH on port `2220`. The goal is to clone the repository locally and retrieve the next level's password.

## Steps

1. **Configure SSH:** Add the following host entry to `~/.ssh/config`:
   ```sshconfig
   Host bandit
       HostName bandit.labs.overthewire.org
       User bandit27-git
       Port 2220
   ```
   This configuration defines a shortcut named `bandit` for connecting to the Bandit Git server.
2. **Create a workspace:**
   ```bash
   mkdir Repos
   cd Repos
   ```
3. **Clone the repository:**
   ```bash
   git clone bandit:/home/bandit27-git/repo
   ```
   SSH uses the `bandit` host configuration, so there is no need to specify the hostname, username, or port in the clone command.
4. **Inspect the repository:**
   ```bash
   cd repo
   ls -aF
   cat README
   ```
   The `README` file contains the password for the next level.
