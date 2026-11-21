# Bandit Level 20 → Level 21

> The home directory contains a SetUID binary called `suconnect`. It connects to a specified localhost port, reads a password from the connection, and sends the next level's password if the received password matches the current level's password.

## Steps

1. **Start a Netcat Listener:** Run `nc -nlvp 4444` to listen for incoming connections on port `4444`.
2. **Connect Using the SetUID Binary:** In another terminal session, execute `./suconnect 4444` to connect to the listener.
3. **Verify the Password:** Send the Bandit 20 password through the Netcat connection. The binary compares the received password with the expected password.
4. **Retrieve the Password:** Once the password matches, `suconnect` sends the Bandit 21 password through the established connection.
