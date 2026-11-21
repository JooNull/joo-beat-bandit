# Bandit Level 19 → Level 20

> The home directory contains a SetUID binary that allows executing commands with the permissions of its owner (bandit20). Use it to read the next level's password.

## Steps

1. **Locate the Binary:** Run `ls` to find `bandit20-do` in the home directory.
2. **Inspect the Binary:** Run `file bandit20-do` to confirm that it is a SetUID executable.
3. **Check Usage:** Execute `./bandit20-do` without arguments to display its usage instructions.
4. **Verify Execution:** Run `./bandit20-do whoami`. The output `bandit20` confirms that the command runs with the binary owner's privileges.
5. **Retrieve the Password:** Run `./bandit20-do cat /etc/bandit_pass/bandit20` to read the next level's password.
