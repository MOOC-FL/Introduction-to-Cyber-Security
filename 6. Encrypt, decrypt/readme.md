### Encrypt, decrypt
#### Encryption algorithms
- Encryption algorithms can be roughly divided into 3 categories:
1. algorithms without a key
2. algorithms based on a symmetric hidden key
3. algorithms based on an asymmetric public/private key
- The "security" of the encryption technique without a key comes from the idea that the decryption algorithm is not known. Perhaps the most known such algorithm is ROT13, where letters are shifted by 13 and wrapped around. Consequently, for example, 'a' becomes 'n'. Keyless algorithms are not considered to be secure, and should not be used outside newspaper puzzles.
- Algorithms based on a symmetric hidden key assume that both encryption and decryption algorithms are known but both parties share a hidden key so that without the key decryption is very difficult. Perhaps the most known such algorithm is Caesar cipher, named after Julius Caesar. The cipher involves shifting letters by a certain amount, and wrapping around. Here the key is an integer indicating the shift. ROT13 is a special case of Caesar cipher where the shift is specifically fixed to 13. Julius himself used a shift of 3 while his nephew Augustus used a shift of 1.

- It is crucial that the number of candidates for a key is very large, making a brute-force attack impossible. For example, Caesar cipher can be easily broken, even without a computer, since there are only 26 options. A more contemporary case is Content Scrambling System (CSS) for DVDs introduced in 1996, and compromised in 1999. CSS was using a 40-bit key, leaving 240 options for a key value. The reason for such a "small" key is at the time United States have restrictions on exporting strong cryptographic methods (nowadays, the restrictions have been loosened, but not completely removed). The short key allowed for a brute-force attack, breaking the encryption in 17 hours, using a contemporary computer.

- The major issue with using a symmetrical key is that both parties need to know the key in advance. To solve the issue, algorithms based on a public/private key are used. The main idea is as follows: A recipient has two keys one public and one private. A sender encrypts a message using an algorithm with a public key. This message can only be decrypted using a private key. Consequently, only the recipient can decrypt a message.

- Since the public key is known it is vital for the encryption algorithm that one cannot deduce the private key easily from the public key. In other words, there is no significantly better way of deducing a private key than just using a brute-force attack. If both public and private keys are long enough, then a brute-force attack becomes infeasible. The most used and known public/private encryption method is RSA, where the security comes from the common assumption that factorization of very large integers is computationally very expensive.

- Asymmetric encryption is often not efficient enough for encrypting large data streams. So in practice, it is used just to establish a symmetric hidden key that is only a valid for one session, and this key is then used with a more efficient algorithm based on a symmetric hidden key.


