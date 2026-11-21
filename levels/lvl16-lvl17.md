# Bandit Level 16 → Level 17

> The credentials for Level 17 can be retrieved by submitting the current level's password to the correct service listening on a port between `31000` and `32000`. Only one service provides the next credentials through SSL/TLS.

## Steps

1. **Scan Open Ports:** Run `nmap -Pn -sT -n -p31000-32000 127.0.0.1` to discover open TCP ports in the specified range.
2. **Identify SSL/TLS Services:** Use `ncat localhost PORT --ssl` to test the open ports and identify the service that accepts SSL/TLS connections.
3. **Submit Password:** Connect to port `31790` using `ncat localhost 31790 --ssl` and submit the current level's password.
4. **Retrieve SSH Private Key:** The service returns an SSH private key after validating the password.
5. **Save Private Key:** Save the returned key locally as `sshkey2.private` and set its permissions using `chmod 600 sshkey2.private`.
6. **Login to Level 17:** Run `ssh -i sshkey2.private bandit17@bandit.labs.overthewire.org -p 2220` to authenticate using the private key.
7. **Verify Access:** Run `cat /etc/bandit_pass/bandit17` to verify access to the next level and retrieve its password.
