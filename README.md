# nx-suite (macOS)

Wrappers that feed the ENICS password (same as the VPN one) from the macOS Keychain.
This is the `mac` branch; `main` is the Linux version (GNOME Keyring + `fortivpn`).

- `nxconnect` — connect to the ENICS_LAB FortiVPN with `openfortivpn` (asks for your Mac's sudo password); goes to the background once the tunnel is up, `nxconnect -d` disconnects, log in `~/Library/Logs/nxconnect.log`
- `nxssh` — ssh wrapper (`nxssh enicsnx01`)
- `nxscp` — scp wrapper, symlink to `nxssh` (`nxscp file.txt enicsnx01:~/`)
- `nxsshfs` — sshfs wrapper (`nxsshfs enicsnx01:/path ~/remote`)
- `nxpasswd` — store or change the password in the Keychain

Requirements (Homebrew): `openfortivpn`, `sshfs-mac` + macFUSE.

Store the password once (and again whenever it changes):

    nxpasswd

The first time a tool reads it, macOS may ask to allow `security` access to the
Keychain item — choose "Always Allow".

If `nxconnect` complains about the gateway certificate, pass the digest it prints:

    nxconnect --trusted-cert=<digest>

Host names resolve via `~/.ssh/config`, e.g.:

    Host enicsnx01
        HostName 192.168.50.91
        User yeminie

(`enicsnx02`–`04` are `.92`–`.94`.)

Install by copying (keep the symlink) into `~/.local/bin`.
