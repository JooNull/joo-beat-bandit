# Bandit Level 17 → Level 18

> The password for Level 18 is stored in `passwords.new` and is the only line that differs between `passwords.old` and `passwords.new`.

## Steps

1. **List Files:** Run `ls` to locate `passwords.old` and `passwords.new` in the home directory.
2. **Compare Files:** Run `diff passwords.old passwords.new` to compare the two files and identify the changed line.
3. **Retrieve the Password:** The output shows that line 42 differs between the files. The line marked with `>` contains the new password stored in `passwords.new`.
