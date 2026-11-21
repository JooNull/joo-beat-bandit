# Bandit Level 7 → Level 8

> The password for Level 8 is stored in the `data.txt` file next to the word `millionth`.

## Steps

1. **List Files:** Run `ls` to locate the `data.txt` file in the home directory.
2. **Inspect File Statistics:** Run `wc data.txt` to display the number of lines, words, and bytes in the file.
3. **Search for the Word:** Run `cat data.txt | grep -i millionth` to search for the word `millionth`. The `grep` command filters the file contents and `-i` makes the search case-insensitive.
4. **Retrieve the Password:** Read the value displayed next to `millionth` to obtain the password for Level 8.
