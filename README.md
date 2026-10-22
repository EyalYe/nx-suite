# nx-suite

Wrappers that feed the ENICS password (same as the VPN one) from GNOME Keyring.

- `nxconnect` — connect to the ENICS_LAB FortiVPN
- `nxssh` — ssh wrapper (`nxssh enicsnx01`)
- `nxscp` — scp wrapper, symlink to `nxssh` (`nxscp file.txt enicsnx01:~/`)
- `nxsshfs` — sshfs wrapper (`nxsshfs enicsnx01:/path ~/remote`)

Store the password once:

    secret-tool store --label='ENICS VPN' service fortivpn user yeminie

Install by copying (keep the symlink) into `~/.local/bin`.
