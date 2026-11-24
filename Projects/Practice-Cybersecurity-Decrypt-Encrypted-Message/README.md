# Activity: Decrypt an Encrypted Message

- **Course:** Google Cybersecurity Certificate — Course 5 (Assets, Threats, and Vulnerabilities)
- **Platform:** Google Skills
- **Category:** Cryptography & Linux Command Line
- **Tools Used:** Linux Bash (`ls`, `cat`, `tr`), OpenSSL (`aes-256-cbc`)

## 1. Objective

Explore a target Linux home directory to locate hidden files, break a Caesar cipher substitution using character translation, and decrypt an AES-256-CBC encrypted file to recover a hidden message.

## 2. Methodology & Steps

### Step 1: Explore the Home Directory

Listed the contents of `/home/analyst` and read `README.txt` to locate the next clue inside the `caesar` subdirectory.

```bash
ls
cat README.txt
```

![Explore Directory](./images/01-explore-directory.png)

### Step 2: Locate Hidden File & Decrypt Caesar Cipher

Navigated into `caesar`, used `ls -a` to reveal the hidden `.leftShift3` file, and shifted the alphabet back by 3 characters with `tr` to uncover the OpenSSL decryption command.

```bash
cd caesar
ls -a
cat .leftShift3 | tr "d-za-cD-ZA-C" "a-zA-Z"
cd ~
```

![Caesar Cipher Decryption](./images/02-caesar-decrypt.png)

### Step 3: Decrypt the Target Data File

Executed the recovered OpenSSL command using AES-256-CBC with PBKDF2 key derivation and the passphrase `ettubrute` to decrypt `Q1.encrypted` into `Q1.recovered`.

```bash
openssl aes-256-cbc -pbkdf2 -a -d -in Q1.encrypted -out Q1.recovered -k ettubrute
cat Q1.recovered
```

![OpenSSL File Decryption](./images/03-openssl-decrypt.png)

## 3. Key Takeaways

- **Classical vs. Modern Encryption:** Substitution ciphers like Caesar are trivial to reverse once the shift pattern is identified, whereas symmetric algorithms like AES-256 require both the exact cipher mode and a secret passphrase (`-k`).
- **Linux Forensics:** Using `ls -a` is essential during initial triage because configuration files and hidden clues often use leading dots (`.`) to stay hidden from standard directory listings.
