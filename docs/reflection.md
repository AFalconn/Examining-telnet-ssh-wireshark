# Reflection

## Why is SSH preferred over Telnet for remote connections?

SSH is preferred because it encrypts the connection, helping protect authentication credentials and session data while they travel across the network. Telnet does not encrypt its traffic, so usernames, passwords, and commands may be readable to someone who can capture the packets. SSH also supports stronger authentication and integrity protections when properly configured. For secure remote administration, use SSH and disable Telnet wherever possible.
