# AES Shellcode Payload Encryptor

A small Windows utility that encrypts raw shellcode using **AES-256-CBC**.  
It is designed to be used as a preprocessing step before embedding shellcode into a custom loader.

## Overview

This tool takes a raw shellcode file, generates a random AES key and IV, encrypts the payload, and outputs the encrypted data in formats that can be directly reused in C source code.
The focus is on simplicity and reliability, relying on native Windows CryptoAPI functions. 

---

## Features

- AES-256-CBC encryption
- Random key and IV generation
- PKCS#7 padding
- Outputs encrypted payload, key, and IV as C arrays

## Build

```bash
gcc encrypt_payload.c modules/crypto.c -o encrypt_payload.exe -lAdvapi32
```

## Usage

```bash
encrypt_payload.exe <shellcode_file>
```

## Output

Files generated in `payload/`:

- `shellcode_aes.bin` – encrypted shellcode (binary)
- `shellcode_aes.txt` – encrypted shellcode as C array
- `key_iv.txt` – AES key and IV as C arrays

---

## License

MIT License


## Disclaimer

For educational and research use only.
