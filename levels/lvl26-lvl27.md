# Bandit Level 26 → Level 27

> After escaping the restricted shell in the previous level, use the SetUID binary `bandit27-do` to execute commands with `bandit27` privileges and retrieve the next level's password.

## Steps

1. **Inspect Available Files:** Run `ls -lh` to locate `bandit27-do` and inspect its permissions. The SetUID bit is enabled, and the binary is owned by `bandit27`.
2. **Execute a Command as Bandit27:** Run:
   ```bash
   ./bandit27-do cat /etc/bandit_pass/bandit27
   ```
   The binary executes `cat` with `bandit27` privileges, allowing access to the protected password file.
3. **Retrieve the Password:** The command displays the password for Level 27.
