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
