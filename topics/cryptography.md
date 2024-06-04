# Cryptography

<br>![cryptography image](https://raw.githubusercontent.com/AnselmoGPP/Learn_Computer_Science/master/resources/miscellany.jpg)

## Table of Contents
+ [Introduction and Classical Cryptography](#introduction-and-classical-cryptography)
+ [Computational Secrecy and Principles of Modern Cryptography](#computational-secrecy-and-principles-of-modern-cryptography)
+ [Private-Key Encryption](#private-key-encryption)
+ [Message Authentication Codes](#message-authentication-codes)
+ [Number Theory](#number-theory)
+ [Key Exchange and Public-Key Encryption](#key-exchange-and-public-key-encryption)
+ [Digital Signatures](#digital-signatures)
+ [References](#references)


## Introduction and Classical Cryptography

Cryptography is everywhere: passwords, password hashing, secure internet credit-card transactions, encrypted Wi-Fi, disk encryption, digitally signed software updates, bitcoin, etc.

**Historical cryptography** (until 1970s): Art of writing and solving codes. It focused exclusively on ensuring secret communication between two parties sharing secret information in advance (key, or "codes").

**Modern cryptography**: Science about design, analysis, and implementation of mathematical techniques for securing information, systems, and computation against adversarial attack.

**Modular arithmetic**:

- $x = x' \mod N$ if and only if N divides $x-x'$   (i.e. x and x' have the same remainder when divided by N) (i.e. n divides x-x')
- $[x \mod N]$ = Remainder when x is divided by N
  - i.e. the unique value $x'\in{0, ..., N-1}$ such that $x = x' \mod N$

Example:

- $25 = 35 \mod 10$ (because both have the same remainder)
- $25 \neq [35 \mod 10]$
- $5 = [35 \mod 10]$

**Private-key cryptography** (AKA secret-key/shared-key/symmetric-key cryptography): Alice and Bob want to share secret information. Both have a shared secret key in advance. The sender encrypts a message/plaintext using the key, generating a cyphertext that is sent over a public communication channel. The receiver decrypts that cyphertext using the key to recover the original message. This is also commonly used for ensuring secrecy for a single user communicating with himself over time. This is defined by:

- **m**: Message from message space M
- **Gen** (key-generation algorithm): Generates k randomly
- **Enc** (encryption algorithm): Takes m and k, and outputs ciphertext **c** ($c&larr;Enc_{k}(m)$)   (&larr; denotes assignment of randomized value)
- **Dec** (decryption algorithm): Takes k and c, and outputs m ($m:=Dec_{k}(c)$)   (:= denotes assignment of deterministic value)
- For all $m \in M$ and k output by Gen, $Dec_{k}(Enc_{k}(m)) = m$

Example (The shift cipher):

- M = {strings over lowercase English alphabet}
- $Gen: choose uniform k \in {0, ..., 25}$
- $Enc_{k}(m_{1}...m_{t}): output c_{1}...c_{t}, where c_{i} := [m_{i} + k \mod 26]$
- $Dec_{k}(c_{1}...c_{t}): output m_{1}...m_{t}, where m_{i} := [c_{i} - k \mod 26]$

Given $k \in {0, 1, ... 25}$ and m = plaintext, we encript m by shifting every letter of the plain text by k positions (with wraparound). Decryption just does the reverse. This way, if we use key c (=2), "helloworld" becomes "jgnnqyqtnf".






## Computational Secrecy and Principles of Modern Cryptography
## Private-Key Encryption
## Message Authentication Codes
## Number Theory
## Key Exchange and Public-Key Encryption
## Digital Signatures

## References

- Jonathan Katz, Yehuda Lindell (2014) *Introduction to modern cryptography, 2nd ed*. Chapman and Hall/CRC. 