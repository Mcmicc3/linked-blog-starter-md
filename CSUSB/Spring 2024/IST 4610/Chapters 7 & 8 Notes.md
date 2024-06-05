## Asymmetric Cryptography
Public and private key exchange

The advantage of ElGamal is that it was released into the public domain
- This algorithm doubles the size of any message it encrypts.

Quantum Cryptography and how it creates something called qubits. How there is no standard for quantum computers, and is continously being researched. The technology could potentially upend many of the principles of modern cybersecurity

Hash functions
- create message digests
- digital signatures

SHA & MD5

Different hash algortihms create different hash value lengths.
- For hackers, this could be used to identify which algorithm was used to encrypt a message. 

Digital signatures assures the recipient that the message comes from its claimed sender, and it also ensures that the message has not been altered in anyway. 
- Digital signatures rely on Public Key Cryptography and Hashing Functions

Alternative hashed algorithms like HMAC can ensure the integretiy of a message during transmission, but does not provide nonrepudiation. 

Public Key Infrastructure
- Certificates and certificate authorities
- Certifiactes are endorsed copies of an individuals public key. 
- Certificates contain specific identifying information and is governed by the X.509 standard. Page 248 contains a list of the data in a certificate
- There are widely accepted CAs 
- **The certificates issues by a CA are only as good as the trust placed in the CA that issued them**

 Certificate lifecycle
 - Enrollment
 - Verification
 - Revocation - certifcates can be revoked

Certificates have differnt formats including DER, PEM, PFX and P7B. Each use a distinct format, either Binary or text, and each have their own extension.

PGP - pretty good privacy, and S/MIME

Web applications use SSL and TLS for encyrption and security through the open web

Tor, Steganopgraphy and Watermarking

Networking
- Circuit Encryotion - **Link Encryption, and End-to-end Encryption**
- IPsec

Emerging technologies like Block chain, Lightweight Cryptography, Homomorphic encryption.
- The first major application for blockchain is cryptocurrency

Cryptographic Attacks
- Analytic attack, Implementation, Statistical, Brute-Force, Fault Injection, Side-channel, Timing attack

# Chapter 8

Zero Trust
- Nothing in the organization is automatically trusted. 
- We focus too hard on securing endpoint devices. 

Privacy by Design

Trust but verify 

#### Techniques for Ensuring CIA
Confinement
Bounds
Isolation
Access Controls
Trust and Assurance

Understanding the Fundamental Concepts of Security models
-  Trusted Computing Base
- A ton of different security models, the one above is one of them.

**Select Controls based on system requirements**
Common Criteria
- Seven different level assurance levels

Authorization to operate
- Authorizaxtion to operate, common control authorization, authorization to use, denial of authorization.

 Understanding Security Capabilities of Information Systems
 - Memory protection
 - Virtualization
 - Trusted Platform module
 - Interfaces
 - Fault tolerance
 - Encryption/Decryption 
