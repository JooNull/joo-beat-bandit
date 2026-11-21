# Bandit Level 8 → Level 9

> The password for Level 9 is stored in `data.txt` and is the only line that occurs exactly once.

## Steps

1. **List Files:** Run `ls` to locate the `data.txt` file.
2. **Inspect File Statistics:** Run `wc data.txt` to display the number of lines, words, and bytes.
3. **Find Unique Line:** Run `sort data.txt | uniq -u` to sort the lines and display the only line that occurs once. `sort` groups identical lines together, while `uniq -u` filters out repeated lines.
