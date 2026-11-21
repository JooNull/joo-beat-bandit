# Bandit Level 9 → Level 10

> The password for Level 10 is stored in one of the human-readable strings in `data.txt`, preceded by several `=` characters.

## Steps

1. **Identify File Type:** Run `file data.txt` to check the file type. The output identifies it as generic data rather than a regular text file.
2. **Extract Readable Strings:** Run `strings data.txt | grep =====` to extract human-readable strings and filter the results for lines containing `=` characters.
3. **Retrieve the Password:** Locate the line containing `password` and read the value on the following line.
