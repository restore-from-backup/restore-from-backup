NOTE: Must only commit to this file from the web gui - DO NOT use git client
#  Restore Process
## DR Scenario Yubikey unavailable
- Access vault-gpg-and-keytocard-only virtual machine
- There will be a folder in the home drive with paperkey and public_key
- Import public key
- Import paperkey (private key)
- Private key is passphrase protected (see keys.md)
- There is a revocation cert in the same folder. Consider revocation depending on where the yubikey went.
- Import subkeys onto new yubikey

## DR Scenario Laptop unavailable + Yubikey unavailable
- Rebuild new laptop
- Login to NAS (see keys.md)
- Decrypt (load nas key) to decrypt NAS zfs volume (see keys.md)
- Login to sshfs lxc (see keys.md)
- set sshfs to allow password login to account (see keys.md)
- create backup virtual machine mount sshfs
- source real paperkey - OCR and restore key
- restore from backup (see keys.md)
- Follow DR Scenarion Yubikey unavailable
  
## DR Scenario Laptop unavailable
- Rebuild new laptop
- Login to NAS (see keys.md)
- Decrypt (load nas key) to decrypt NAS zfs volume (see keys.md)
- Login to sshfs lxc (see keys.md)
- create backup virtual machine mount sshfs
- restore from backup (see keys.md)
  
# Backup
## Android

- Contacts - no backup
- Photos - email service providers android app
- Signal - linked device on linux regularly used

## Laptop
- regular full backups to NAS, keeping existing backups
- regular full backups to email provider, removing existing backups
