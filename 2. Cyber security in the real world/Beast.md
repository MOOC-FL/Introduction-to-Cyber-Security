#### What is BEAST?
- TLS 1.0 and earlier protocols suffer from a serious flaw: the Initialization Vector (IV) blocks that are used to mask data (plaintext) prior to encryption with a block cipher can be predicted by an active man-in-the-middle (MITM) attacker.
- IVs are used to prevent encryption from being deterministic; without them, every time you encrypt the same block of data with the same key, you get the same (encrypted) output. This is highly undesirable. A clever attacker who can
 1. predict IVs
 2. see what encrypted data looks like,
 3.  influence what is encrypted, is then able to make guesses about what plaintext looks like.
 Technically, he cannot decrypt any data, but he can find out if his guesses are right or wrong. With enough guesses, any amount of data can be uncovered.
