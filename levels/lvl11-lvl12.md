# Bandit Level 11 → Level 12

> The password for Level 12 is stored in `data.txt`, where all lowercase and uppercase letters have been encrypted using ROT13.

## Steps

1. **List Files:** Run `ls` to locate the `data.txt` file in the home directory.
2. **Read Encoded Data:** Run `cat data.txt` to display the encrypted text.
3. **Decode ROT13:** Run `cat data.txt | tr 'a-zA-Z' 'n-za-mN-ZA-M'` to rotate all lowercase and uppercase letters by 13 positions and retrieve the password for Level 12.
