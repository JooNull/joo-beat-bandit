# Bandit Level 2 → Level 3

> The password for Level 3 is stored in a file with spaces in its name, located in the home directory.

## Steps

1. **List Files:** Run `ls` to locate the file named `--spaces in this filename--`.
2. **Read the File (Method 1):** Run `cat ./'--spaces in this filename--'`. The `./` prefix prevents the filename from being interpreted as an option, while single quotes preserve spaces as part of a single argument.
3. **Read the File (Method 2):** Run `cat -- "--spaces in this filename--"`. The `--` marks the end of options, while double quotes preserve the spaces in the filename.
