# Lesson Plan: Cryptography Fundamentals

**Overview**

Hello! And welcome to an introduction to **Cryptography!** Lets face it. Whether you're a SOHO or a large corporation, seems like every twist and turn bad guys are finding new ways to get to our sensitive data. Thats where cryptography comes in. Cryptography is the practice and study of techniques for securing information and communication mainly to protect the data from third parties (bad guys) that the data is not intended for. Because modern cryptography contains sophisticated algorithms, we will touch on a few key ones. Also we will focus on the strength of different kinds of encryption used today. So without further ado, let's jump in and get to it!


**Workshop Objectives**
By the end of this lesson we will be able to define and understand:

 - Goals of Cryptography / **PAIN** framework
	 - **P**rivacy/Confideniality
	 - **A**uthenticity
	 - **I**ntegrity
	 - **N**on-repudiation
 - Symmetric Key Encryption
	 - Block Algorithms
	 - Streaming Algorithms
 - Asymmetric Key Encryption
 - Potential Interview Questions


## Goals of Cryptography

 - **Privacy / Confideniality** - is protecting the information from disclosure to unauthorized parties.
	 - A key component in protecting information confidentiality is encryption. Encryption ensures that only the right people can read the information. 
	 - Another way of enforcing privacy is file permissions to restrict access to sensitive information.
 - **Authenticity** - means that the initial sender is who they claim to be.
	 - Digital signatures are the best tool to use to verify the authenticity of data. Digital signatures use asymmetric cryptography. 
 - **Integrity** - refers to protecting information from being modified by unauthorized parties. 
	 - Say you want to transfer money to someone for $100 but the data was tampered with in such a way that you actually sent $1000. 
	 - a common way to ensure integrity is through hashing.
 - **Non-repudiation** - is the assurance that someone cannot deny the validity of something. It provides proof of the origin of data. Non-repudiation is closely linked to authentication. 
	 - Say Alice sent a nasty email to a co-worker. Non-repudiation is the element that inhibits Alice from blaming it on something or someone else.

## A bit of Cryptography Background

**Caesar cipher** is a substitution cipher in which letters change during encryption. Caeser used a very simple rule to replace each letter with another letter from the alphabet. He shifted letters by 3 places further along in the alphabet where **3** is the **'key'**. For example, the letter **B** would become **E**, and so on. The use of keys in cryptography is integral to creating secure ciphers. By giving the recipient a choice, it makes it harder for an interceptor to decipher the original message. One of the strengths of the Caesar cipher is its ease of use. In addition, encryption and decryption could be done quickly using a wheel. However, these strengths come at a cost of security. There are only a total of 25 encryption keys. Thus, each could be tried until the message was deciphered.

![Caesar Cipher example](https://www.cdn.geeksforgeeks.org/wp-content/uploads/Caesar-Cipher-3.png)

**Vigenere cipher** is a method of encrypting alphabetic text by employing a series of interwoven Caesar ciphers based on the letters of a keyword. It uses a simple form of polyalphabetic substitution. A **polyalphabetic substitution** is any cipher based on using multiple substitution alphabets. The encryption is done using a Vigenere Square. 

![Vigenere Cipher example](https://www.researchgate.net/profile/Amin_Subandi/publication/318260132/figure/fig3/AS:513402955104258@1499416211147/Vigenere-Cipher-table.png)



# Symmetric Key Encryption - *One key to rule them all!*
**Symmetric Key Encryption** is fairly straightforward. You have one secret key that that is used to both encrypt and decrypt electronic information. When we use symmetric key encryption, information is transformed so that it cannot be decrypted by anyone who does not possess the secret key. Once the recipient obtains the secret key and the data, the algorithm is reversed and returned to its original state and is able to be understood. The secret key could be a special code or a randomly generated password. 

![Symmetric Encryption Diagram](https://www.cheapsslshop.com/blog/wp-content/uploads/2017/09/Symmetric_Encryption.png)


There are two types of symmetric key encryption:

 - **Block algorithms** - A method of encrypting in which a key and algorithm are applied to a block of data instead of one bit at a time. The simplest modes where the message is divided into blocks and encrypted separately is the **Electronic Codebook mode**. 
![Electronic Codebook Mode Diagram](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d6/ECB_encryption.svg/2880px-ECB_encryption.svg.png)

 It is common to apply the cipher text from the previously encrypted block to the next block so that blocks do not get encrypted the same way. This is what is called **Cipher Block Chaining**.
 ![Ciper Block Chaining Mode Diagram](https://upload.wikimedia.org/wikipedia/commons/thumb/8/80/CBC_encryption.svg/2880px-CBC_encryption.svg.png)
 
 - **Stream algorithms** - Data is encrypted as it streams one bit at a time instead of being retained in memory. This method is not commonly used in modern cryptography.

Some examples of symmetric key encryption algorithms are:

 - AES - Advanced Encryption Standard
 - DES - Data Encryption Standard
 - IDEA - Internation Data Encryption Algorithm
 - BLOWFISH - Replacement for DES and IDEA
 - RC4 - Rivest Cipher 4
 - RC5 - Rivest Cipher 5
 - RC6 - Rivest Cipher 6

Let's look at a couple.

**DES** - The original block cipher algorithm was developed by IBM in the 70s. However, with a key length of 56 bits, by the 90s it became apparent it wasn't sufficiently secure against brute force attacks with modern computers.

**Triple DES** - Introduced in the late 90s, Triple DES employs 3 keys with a strength of 168 bits. But this comes at a price: slow performance.

**AES** - Replacing DES in the early 2000s, it features a block size of 128 or 256 bits and three key length options: 128, 192, and 256.

# Asymmetric Key Encryption
As you can probably surmise, symmetric key encryption has its limitations. How does one exactly get the secret key to the recipient securely?  **Asymmetric Key Encryption** aims to solve some of the issues that arise from symmetric key encryption. Lets use a mailbox as an analogy. The mailbox is available to the public which represents the public key. Everyone who knows the address can reach the mailbox and put a package in it. However, only the owner has a key to open it and access the packages. Let's get a bit more technical since asymmetric key encryption is widely used in HTTPS, Bitcoin, PGP (to securely send emails) and SSH.

Both parties involved must generate key pairs on their computers: a public key and a private key. Lets say Alice wants to encrypt a message for Bob. They first start by exchanging their public keys. Alice takes Bobs public key and encrypts the message. She then sends the encrypted message to Bob who uses his private key to unlock it and read it. Even Alice would not be able to decrypt the message because she does not have Bobs private key. The strength of asymmetric encryption now lies with Alice and Bob to securely store their private keys.


![Asymmetric Encryption Diagram](https://www.cheapsslshop.com/blog/wp-content/uploads/2017/09/Asymmetric-Encryption.png)



Some examples of asymmetric key encryption algorithms are:

 - Diffie-Hellman key exchange
 - RSA - Rivest–Shamir–Adleman
 - DSA - Digital Signature Algorithm
 - ECC - Eliptic Curve Cryptography

Lets take a closer look.

**Diffie-Hellman** - The Diffie-Hellman key exchange is an important milestone in the world of cryptography and is still widely used today. It allows two parties who have not met to securely establish a key which they can use to secure their connection. Basically you will exchange public variables and combine them with private variables you've kept hidden so that both parties can create the same key.

![Diffie-Hellman Diagram](https://i.stack.imgur.com/n4jBE.png)


**RSA** - RSA is still a worldwide standard used today. In this cryptosystem, the encryption key is public and is distinct from the decryption key which is private. The magic behind RSA lies within the difficulty of factoring the product of two large prime numbers. RSA is less commonly used because of it being a slow algorithm.

**ECC** - ECC is a relatively new algorithm that creates encryption keys based on using points on a curve to define the public and private keys. 

# Potential Interview Questions
1. **What is the goal of Cryptography?**
- to ensure the confidentiality and integrity of any data or system. The content and images must remain private between the sending and the receiving parties; while they are in transit across the Internet, assurances must be provided that they will remain intact and not altered in any way.

2. **What are symmetric and asymmestric key systems?**
- A symmetric key system uses only the private key, and the asymmetric key system makes use of both the public key and the private key.

3. **What are the mathematical algorithms used in asymmetric cryptography?**
- RSA, Diffie-Hellman, ECC