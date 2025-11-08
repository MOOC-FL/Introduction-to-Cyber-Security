### Certificates 
- While encryption makes sure that the 3rd party cannot eavesdrop on the communication,
  it is still still vulnerable to a man-in-the-middle attack: the 3rd party
  can pretend that it is the server to which the user wishes to contact. The attack is done as follows. Consider two parties, Alice and Bob, and an attacker Melissa. Alice wishes to send safely a message to Bob, and Melissa wishes to intercept the message.
1. Melissa makes Alice believe that she is Bob.
2. Alice asks Bob (Melissa in disquise) for a public key. Instead Melissa provides Alice with her own public key.
3. Alice encrypts the information with the spoofed key and sends it back to Melissa.
4. Melissa decrypts the information using her secret key.
> The crux of the problem is that Alice cannot verify whether the public key belongs to Bob. To solve this problem certificates are used.
- Certificates work as follows. Consider that there is an additional party, Benedict. Alice wants to send an encrypted message but is not sure whether Bob's public key is really his. However, Alice knows and trusts Benedict's public key. The verification consists of the following steps:

1. Bob asks Benedict to sign his public key.
2. Benedict uses Bob's public key and his identity to construct a signature, that is encrypted with Benedict's secret key, and sends Bob the signature.
3. Upon request, Bob sends Alice the certificate, that is, his information and the encrypted signature.
4. Alice decrypts the signature using Benedict's public key and verifies that the information in the certificate matches the decrypted signature.
5. Alice checks that the identity in the certificate is indeed Bob.
6. Alice can now trust the public key provided in Bob's message.
- Let's look more closely at the sequence of these events. First, note that signature is done by encrypting using a secret key, instead of a public key. Since Benedict is the only one that knows the secret key, he is the only one that can produce the signature. The signature contains Bob's identity as well as the public key, so Alice can trust that the information is correct by trusting Benedict's action.
- This is how certificates work. In the above example, Benedict is known as a Certificate Authority (CA), Bob is a web server, and Alice is a normal user. Certificate Authorities are companies that provide certificates for web servers, essentially giving them means to prove who they are.
- Melissa cannot fake being Bob, because she needs to provide a fake certificate for Bob. She has 3 options, none of them will succeed:
1. She can use Bob's certificate, but she cannot decrypt the incoming traffic because Alice will encrypt the data with Bob's public key.
2. She can obtain her own valid certificate, but Alice will notice that the certificate is Melissa's and not Bob's.
3. She can modify the certificate by replacing Bob's key with her own but the content no longer match the signature, so Alice rejects the tampered signature.

- The key assumption here is that Alice trusts Benedict. In practice, a computer has a list of trusted certificate authorities, that are obtained via a secure channel, for example, when installing a new operating system.
- In practice, there may be intermediate parties, meaning Bob doesn't use Benedict directly, instead he asks a mediator, say William, to issue a certificate. William has his own certificate that he has obtained from Benedict. Alice then needs verify both Bob's and William's certificates.
- Similar scheme is also for signing executables.





