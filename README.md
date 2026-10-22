# nx-suite

Wrappers that feed the ENICS password (same as the VPN one) from GNOME Keyring.

- `nxconnect` — connect to the ENICS_LAB FortiVPN
- `nxssh` — ssh wrapper (`nxssh enicsnx01`)
- `nxscp` — scp wrapper, symlink to `nxssh` (`nxscp file.txt enicsnx01:~/`)
- `nxsshfs` — sshfs wrapper (`nxsshfs enicsnx01:/path ~/remote`)
- `nxpasswd` — store or change the password in the keyring

Store the password once (and again whenever it changes):

    nxpasswd

Install by copying (keep the symlink) into `~/.local/bin`.
