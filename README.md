# Secure File Encryption System

This project is a **secure file encryption and decryption system** implemented in Python. It combines symmetric (AES) and asymmetric (RSA) cryptography to securely encrypt, decrypt, and sign files.

---

## Table of Contents

- [Features](#features)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Encryption Workflow](#encryption-workflow)
- [License](#license)

---

## Features

- Symmetric encryption using AES.
- Asymmetric encryption and decryption using RSA.
- Digital signature generation and verification.
- Key management system for secure key storage.
- CLI interface for easy usage.

---

## Project Structure

```

project-name/
├── README.md
├── LICENSE
├── requirements.txt
├── .gitignore
├── src/
│   ├── main.py               # Entry point
│   ├── app/                  # CLI or web interface
│   ├── crypto/               # Crypto modules
│   │   ├── asymmetric.py
│   │   ├── symmetric.py
│   │   └── kms/              # Key management system
│   └── keys/                 # Additional project keys
└── venv/                     # Python virtual environment

````

---

## Installation

1. Clone the repository:

```bash
git clone <repository_url>
cd project-name
````

2. Create and activate a virtual environment:

```bash
python -m venv venv
# Windows
venv\Scripts\activate
# Linux/Mac
source venv/bin/activate
```

3. Install dependencies:

```bash
pip install -r requirements.txt
```

---

## Usage

Run the main program:

```bash
python src/main.py
```

Or use the CLI module:

```bash
python src/app/cli.py --help
```

### Example commands

* Encrypt a file:

```bash
python src/main.py encrypt test.txt
```

* Decrypt a file:

```bash
python src/main.py decrypt test.txt.enc
```

* Sign a file:

```bash
python src/main.py sign test.txt
```

* Verify a signature:

```bash
python src/main.py verify test.txt test.txt.sig
```

---

## Encryption Workflow

1. Generate an AES session key for the file.
2. Encrypt the file with AES.
3. Encrypt the AES key with the recipient's RSA public key.
4. Send the encrypted file and key securely.
5. Recipient decrypts AES key using RSA private key and decrypts the file.

---

## License

This project is licensed under the [MIT License](LICENSE).
