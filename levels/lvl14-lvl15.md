# Bandit Level 14 → Level 15

> The password for Level 15 can be retrieved by submitting the current level's password to port `30000` on `localhost`.

## Steps

1. **Retrieve Current Password:** Run `cat /etc/bandit_pass/bandit14` to read the current level's password.
2. **Connect to Service:** Run `nc localhost 30000` to establish a connection to the service listening on port `30000`.
3. **Submit Password:** Enter the current level's password into the Netcat connection.
4. **Retrieve Next Password:** The service validates the submitted password and returns the password for Level 15.
