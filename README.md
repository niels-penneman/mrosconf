# MikroTik RouterOS Configuration Downloader

Downloads the configuration of Mikrotik RouterOS devices for backup purposes
over SSH.

Mikrotik and RouterOS are trademarks of Mikrotikls SIA.

## Usage

SSH access must be set up on your RouterOS device. The script can authenticate
using a provided username and password, or using a private key. The private key
can be protected with a passphrase when using `ssh-agent`.

Authentication parameters must be set through environment variables:
* `MIKROTIK_ROUTEROS_USERNAME`: optionally specifies the username; only required
  when different from the user under which the script is executed.
* `MIKROTIK_ROUTEROS_PASSWORD`: specifies the password for password-based
  authentication; when set, the script will never attempt key-based
  authentication.
* `MIKROTIK_ROUTEROS_IDENTITY`: optionally specifies the name of a specific
  identity file (private key) to use for key-based authentication; when omitted,
  the SSH client will decide which key to use from the user's default key store.

The script must be invoked as follows:

  mrosconf HOST_OR_IP EXPORT_FILE SYSTEM_BACKUP_FILE

Parameters:
* `HOST_OR_IP`: host name or IP address of the Mikrotik RouterOS device.
* `EXPORT_FILE`: destination file name for the text-based backup using the
  export command.
* `SYSTEM_BACKUP_FILE`: destination file name for the unencrypted binary system
  backup file.