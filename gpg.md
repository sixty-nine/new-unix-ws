# GPG

## Keys

### Create a key

```bash
gpg --full-generate-key
```

### List keys

```bash
gpg --list-secret-keys
```

### Import public key

```bash
gpg --import yourfriends.key
```

### Export public key

```bash
gpg --export -a "Your Name" > your.key
```

### Export/import private key

```bash
gpg --export-secret-keys $KEY_ID > my-private-key.asc
gpg --import my-private-key.asc
```

## Encrypt and decrypt

```bash
# Encrypt
gpg -e text.txt

# Decrypt
gpg -d text.txt.gpg > text.txt

# Decrypt to terminal
gpg -d text.txt.gpg 2>/dev/null
```

## Links

* [How to Encrypt and Decrypt Individual Files With GPG](https://linuxconfig.org/how-to-encrypt-and-decrypt-individual-files-with-gpg)
* [GPG: Extract private key and import on different machine](https://makandracards.com/makandra/37763-gpg-extract-private-key-and-import-on-different-machine)
* [GPG Command Cheat Sheet](https://guides.library.illinois.edu/data_encryption/gpgcheatsheet)
