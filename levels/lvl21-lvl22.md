# Bandit Level 21 → Level 22

> A cron job runs automatically as `bandit22`. The script copies the Bandit 22 password into a temporary file and makes it readable.

## Steps

1. **Inspect Cron Jobs:** Run `ls /etc/cron.d` to locate the configuration file `cronjob_bandit22`.
2. **Read the Cron Configuration:** Run `cat /etc/cron.d/cronjob_bandit22` to identify the scheduled command. The job runs `/usr/bin/cronjob_bandit22.sh` every minute as `bandit22`.
3. **Inspect the Script:** Run `cat /usr/bin/cronjob_bandit22.sh` to understand its actions:
   - Changes the permissions of a temporary file to `644`.
   - Copies the contents of `/etc/bandit_pass/bandit22` into that file.
4. **Retrieve the Password:** Read the temporary file using `cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv` to obtain the password for Level 22.
