# Bandit Level 12 → Level 13

> The password for Level 13 is stored in `data.txt`, which is a hexdump of a repeatedly compressed file.

## Steps

1. **Create Working Directory:** Run `mktemp -d` to create a temporary directory under `/tmp` for safely extracting and processing files.
2. **Copy the File:** Run `cp ~/data.txt .` to copy `data.txt` into the working directory.
3. **Convert Hexdump to Binary:** Run `xxd -r data.txt output.bin` to reconstruct the original binary file from the hexdump.
4. **Identify Compression Formats:** Run `file output.bin` to identify the file format before extracting it.
5. **Extract Compressed Files:** Rename files with the appropriate extensions and use the corresponding extraction commands:
   - `gunzip` for gzip files.
   - `bunzip2` for bzip2 files.
   - `tar -xf` for tar archives.
6. **Repeat Extraction:** Continue identifying and extracting the resulting files using `file` until reaching a human-readable text file.
7. **Retrieve the Password:** Run `cat data8` to display the final contents and retrieve the password for Level 13.
