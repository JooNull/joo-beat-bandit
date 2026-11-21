# Bandit Level 25 → Level 26

> The SSH private key for `bandit26` is available from the previous level. However, logging in does not provide a normal shell. The user has a custom login shell that runs `more` to display a text file. The goal is to escape this restricted environment and obtain shell access.

## Steps

1. **Connect to Bandit26:** Use the private key obtained from the previous level:

   ```bash
   ssh -i bandit26.sshkey bandit26@bandit.labs.overthewire.org -p 2220
   ```

   The connection closes immediately after displaying the login information.

2. **Inspect the Custom Shell:** Examine `/usr/bin/showtext` from the previous level:

   ```bash
   #!/bin/sh

   export TERM=linux

   exec more ~/text.txt
   exit 0
   ```

   - `#!/bin/sh`: Executes the script using the Shell interpreter.
   - `export TERM=linux`: Sets the terminal type for programs.
   - `exec more ~/text.txt`: Replaces the current shell process with `more`, displaying `text.txt`.
   - `exit 0`: Not reached because `exec` replaces the shell process.

3. **Reduce Terminal Dimensions:** Before connecting again, reduce the local terminal dimensions to make `more` enter interactive mode:

   ```bash
   stty rows 10 cols 80
   ```

4. **Force SSH to Allocate a Pseudo-Terminal:** Connect again using `-tt`:

   ```bash
   ssh -tt -i bandit26.sshkey bandit26@bandit.labs.overthewire.org -p 2220
   ```

   With the smaller terminal dimensions, `more` pauses instead of displaying the entire file and exiting.

5. **Escape from more:** When the `--More--` prompt appears, press `v` to open the file in Vim.

6. **Spawn a Shell from Vim:** Execute the following Vim commands:

   ```vim
   :set shell=/bin/bash
   :shell
   ```

   This configures Vim to use Bash and launches an interactive shell.

7. **Retrieve the Password:** Once shell access is obtained, run:
   ```bash
   cat /etc/bandit_pass/bandit26
   ```
   The command displays the password for Level 26.
