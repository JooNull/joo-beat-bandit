# Bandit Level 10 → Level 11

> The password for Level 11 is stored in `data.txt`, which contains Base64-encoded data.

## Steps

1. **List Files:** Run `ls` to locate the `data.txt` file in the home directory.
2. **Identify File Type:** Run `file data.txt` to identify the file type.
3. **Read Encoded Data:** Run `cat data.txt` to display the Base64-encoded content.
4. **Decode Base64:** Run `cat data.txt | base64 -d` to decode the content and retrieve the password for Level 11.
