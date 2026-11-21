# Bandit Level 28 → Level 29

> The challenge provides a remote Git repository. The goal is to inspect its commit history and recover the password removed from the latest version of `README.md`.

## Steps

1. **Configure SSH:** Update the `~/.ssh/config` host entry to use `bandit28-git` as the username.

2. **Clone the repository:**
   ```bash
   git clone bandit:/home/bandit28-git/repo
   cd repo
   ```
3. **Inspect the commit history:**
   ```bash
   git log
   git log --oneline
   ```
   The history contains three commits, including `add missing data` and `fix info leak`.
4. **Inspect the earlier commit:**
   ```bash
   git show 26663cf19bf4014c5f9dc845b9e8feef90a84660
   ```
   The diff reveals that the password was added by this commit and later removed in the following commit.
5. **Retrieve the password:** The previous version of `README.md` contains the password for Level 29.
