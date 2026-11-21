# Bandit Level 13 → Level 14

> The password for Level 14 is stored in `/etc/bandit_pass/bandit14` and can only be read by user `bandit14`. A private SSH key is provided to log into the next level.

## Steps

1. **List Files:** Run `ls` to locate the `sshkey.private` file in the home directory.
2. **Read Hint:** Run `cat HINT` to check the provided instructions for this level.
3. **Download SSH Key:** Run `scp -P 2220 bandit13@bandit.labs.overthewire.org:/home/bandit13/sshkey.private .` from your local machine to download the private SSH key.
4. **Verify Download:** Run `ls` on your local machine to confirm that `sshkey.private` was downloaded successfully.
