# Bandit Level 4 → Level 5

> The password for Level 5 is stored in the only human-readable file inside the `inhere` directory.

## Steps

1. **Navigate to Directory:** Run `cd inhere/` to enter the `inhere` directory.
2. **List Files:** Run `ls` to list the files. Notice that all filenames start with `-`.
3. **Identify File Types:** Run `file ./'-file00'` to check the file type. The `./` prefix prevents the filename from being interpreted as an option.
4. **Find Human-Readable File:** Repeat the `file` command for the remaining files until you find the one identified as `ASCII text`, which is `-file07`.
5. **Read the File:** Run `cat ./-file07` to display its contents and retrieve the password for Level 5.
