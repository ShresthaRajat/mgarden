## Hashing
#cyber-security #security #encryption

Hashing uses an algorithm to convert text to a _unique_ fixed-length value called a hash. Each time the same text is hashed using the same algorithm, the same hash value is produced. That hash can then be used as a unique identifier of its associated data.

Hashing is different to [Encryption](Cyber%20Security/Encryption.md) in that it doesn't use keys, and the hashed value isn't subsequently decrypted back to the original.

Hashing is used to store passwords. When a user enters their password, the same algorithm that created the stored hash creates a hash of the entered password. This is compared to the stored hashed version of the password. If they match, the user has entered their password correctly. This is more secure than storing plain text passwords, but hashing algorithms are also known to hackers. Because hash functions are deterministic (the same input produces the same output), hackers can use brute-force dictionary attacks by hashing the passwords. For every matched hash, they know the actual password. To mitigate this risk, passwords are often “salted”. This refers to adding a fixed-length random value to the input of hash functions to create unique hashes for same input.

![The concept of hashing](https://learn.microsoft.com/en-us/training/wwl-sci/describe-security-concepts-methodologies/media/6-hashing-3-inline.png)