# Bandit Level 15 → Level 16

> The password for Level 16 can be retrieved by submitting the current level's password to port `30001` on `localhost` using SSL/TLS encryption.

## Steps

1. **Connect Without Encryption:** Run `nc localhost 30001` to test the connection. The service requires SSL/TLS, so a regular Netcat connection is insufficient.
2. **Connect Using Ncat:** Run `ncat localhost 30001 --ssl` to establish an SSL/TLS-encrypted connection.
3. **Submit Password:** Enter the current level's password into the connection.
4. **Retrieve Next Password:** The service validates the password and returns the password for Level 16.
5. **Alternative Using OpenSSL:** Run `openssl s_client -connect localhost:30001` to establish a TLS connection, then submit the current password to retrieve the next one.
