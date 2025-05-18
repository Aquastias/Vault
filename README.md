# Vault

> This repository holds various notes and secrets in an encrypted archived/unarchived format.

## Archive encryption / decryption using OpenSSL and Age
### OpenSSL
#### Encryption

```sh
tar czf - file1 file2 dir1/ file3 | openssl enc -aes-256-cbc -pbkdf2 -iter 100000 -salt -e -out archive.tar.gz.enc
```

#### Decryption

```sh
openssl enc -aes-256-cbc -d -pbkdf2 -iter 100000 -salt -in test.tar.gz | tar xzf - -C target_directory
```

### Age
#### Encryption

```sh
age -e -p -o output_file input_file
```

#### Decryption

```sh
age -d -o output_file input_file
```
