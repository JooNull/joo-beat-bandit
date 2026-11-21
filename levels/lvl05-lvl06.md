# Bandit Level 5 → Level 6

> The password for Level 6 is stored in a file under the `inhere` directory that is human-readable, exactly 1033 bytes in size, and not executable.

## Steps

1. **Find File by Size:** Run `find . -type f -size 1033c` to search for regular files that are exactly 1033 bytes in size.
2. **Identify File Type:** Run `file ./maybehere07/.file2` to verify that the file contains human-readable ASCII text.
3. **Read the File:** Run `cat ./maybehere07/.file2` to display its contents and retrieve the password for Level 6.
