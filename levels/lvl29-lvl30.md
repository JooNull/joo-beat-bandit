# Bandit Level 29 → Level 30

> The challenge provides a remote Git repository. The password is not available in the `master` branch, so the goal is to inspect other remote branches and find the missing data.

## Steps

1. **Update SSH configuration:** Change the username in `~/.ssh/config` to `bandit29-git`:
   ```sshconfig
   Host bandit
       HostName bandit.labs.overthewire.org
       User bandit29-git
       Port 2220
   ```
2. **Clone the repository:**
   ```bash
   git clone bandit:/home/bandit29-git/repo
   cd repo
   ```
3. **List available branches:**
   ```bash
   git branch -a
   ```
   This reveals two additional remote branches: `origin/dev` and `origin/sploits-dev`.
4. **Inspect the development branch history:**
   ```bash
   git log origin/dev
   ```
   The latest commit is named `add data needed for development`.
5. **Inspect the commit:**
   ```bash
   git show 6a3b86581f1c4ba92a2ae86b3d62f95dd20b284f
   ```
   The diff reveals that the password was added to `README.md` in the `origin/dev` branch.
