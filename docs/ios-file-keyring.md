# Optional file keyring for iOS automation

The iOS build normally uses the system Keychain. In this fork, set
`IPATOOL_FILE_KEYRING=1` to use an encrypted file keyring in the normal ipatool
state directory instead. Set `IPATOOL_KEYCHAIN_PASSPHRASE` to supply its
passphrase without placing it on the command line.

The file keyring has a separate account session. Run `auth login` once with
both environment variables set, then use the same variables for later
`--non-interactive` downloads. Keep the passphrase and keyring file private.

The default Keychain behavior is unchanged when `IPATOOL_FILE_KEYRING` is not
set to `1`.
