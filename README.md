# nx-suite

Wrappers that feed the ENICS password (same as the VPN one) from GNOME Keyring.

- `nxconnect` — connect to the ENICS_LAB FortiVPN
- `nxssh` — ssh wrapper (`nxssh enicsnx01`)
- `nxscp` — scp wrapper, symlink to `nxssh` (`nxscp file.txt enicsnx01:~/`)
- `nxsshfs` — sshfs wrapper (`nxsshfs enicsnx01:/path ~/remote`)
- `nxtiger` — open a VNC session in TigerVNC Viewer, logged in automatically (`nxtiger enics01:11`); doesn't block the terminal, log in `~/.local/state/nxtiger.log`
- `nxpasswd` — store or change the password in the keyring

Requirements: `tigervnc` (for `nxtiger`).

Store the password once (and again whenever it changes):

    nxpasswd

Host names resolve via `~/.ssh/config`, e.g.:

    Host enicsnx01 enics01
        HostName 192.168.50.91
        User yeminie

(`enicsnx02`–`04` are `.92`–`.94`; `nxtiger` uses the same names.)

Install by copying (keep the symlink) into `~/.local/bin`.
