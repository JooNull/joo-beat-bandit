# Bandit Level 22 → Level 23

> A cron job runs a script as `bandit23`. The script generates an MD5 hash based on the username and uses it as the filename when copying the user's password into `/tmp`.

## Steps

1. **Inspect the Cron Configuration:** Run `cat /etc/cron.d/cronjob_bandit23` to identify the scheduled script `/usr/bin/cronjob_bandit23.sh`, which runs every minute as `bandit23`.
2. **Analyze the Script:** Run `cat /usr/bin/cronjob_bandit23.sh` and identify its operations:
   - `whoami` gets the current username.
   - `echo I am user $myname | md5sum | cut -d ' ' -f 1` generates an MD5 hash of the username-based string.
   - The script copies the corresponding password file into `/tmp/` using the hash as the filename.
3. **Calculate the Target Filename:** Set `myname="bandit23"` and run:
   ```bash
   echo I am user $myname | md5sum | cut -d ' ' -f 1
   ```
   This generates the filename `8ca319486bfbbc3663ea0fbe81326349`.
4. **Retrieve the Password:** Read the generated file:
   ```bash
   cat /tmp/8ca319486bfbbc3663ea0fbe81326349
   ```
   The output contains the password for Level 23.
