# Bandit Level 30 → Level 31

> The challenge provides a Git repository with no useful password in its README or commit history. The goal is to inspect the repository's tags and retrieve the password.

## Steps

1. **Update SSH configuration:** Change the username in `~/.ssh/config` to `bandit30-git`:
   ```sshconfig
   Host bandit
       HostName bandit.labs.overthewire.org
       User bandit30-git
       Port 2220
   ```
2. **Clone the repository:**
   ```bash
   git clone bandit:/home/bandit30-git/repo
   cd repo
   ```
3. **Inspect the repository:**
   ```bash
   cat README.md
   git log
   git branch -a
   ```
   The README contains no useful information, and the repository has no additional branches or commits to inspect.
4. **List available tags:**
   ```bash
   git tag
   ```
   This reveals a tag named `secret`.
5. **Retrieve the password:**
   ```bash
   git show secret
   ```
   The tag points to an object containing the password for Level 31.
