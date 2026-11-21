# Bandit Level 31 → Level 32

> The challenge requires pushing a file named `key.txt` containing the exact text `May I come in?` to the remote repository on the `master` branch.

## Steps

1. **Update SSH configuration:** Change the username in `~/.ssh/config` to `bandit31-git`:
   ```sshconfig
   Host bandit
       HostName bandit.labs.overthewire.org
       User bandit31-git
       Port 2220
   ```
2. **Inspect the repository:**
   ```bash
   ls -aF
   cat README.md
   cat .gitignore
   git branch
   ```
   The `.gitignore` file contains `*.txt`, which causes Git to ignore text files. The required branch is `master`.
3. **Create the required file:**
   ```bash
   echo "May I come in?" > key.txt
   ```
4. **Force-add the ignored file:**
   ```bash
   git add -f key.txt
   ```
5. **Commit the change:**
   ```bash
   git commit -m "Add required key file"
   ```
6. **Push to the remote repository:**
   ```bash
   git push
   ```
   The remote server runs a `pre-receive` hook to validate the submitted file. After successful validation, it displays the password for Level 32, then rejects the push (`pre-receive hook declined`).
