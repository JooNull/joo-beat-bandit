# Bandit Level 6 → Level 7

> The password for Level 7 is stored somewhere on the server in a file owned by user `bandit7`, group `bandit6`, and exactly 33 bytes in size.

## Steps

1. **Search for the File:** Run `find / -type f -size 33c -user bandit7 -group bandit6 2> /dev/null` to search the entire filesystem for regular files matching the specified size, owner, and group. Redirect error messages to `/dev/null` to suppress permission errors.
2. **Read the File:** Run `cat /var/lib/dpkg/info/bandit7.password` to display its contents and retrieve the password for Level 7.
