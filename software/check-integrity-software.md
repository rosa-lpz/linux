# Check integrity of the software

## Generating an SHA-256 Hash From the Command Line

The SHA-256 algorithm is used to check the integrity of the data. The hashes generated using SHA-256 can verify the integrity and authenticity of the data. We can use an SHA-256 checksum/hash, a string of numbers and letters, to determine whether a given file is the same as the original. An extremely different checksum or hash can be produced from a small change in the data. This can be used to determine whether the file was compromised during transmission or storage, either by attackers or by other technical issues. When you have a file that must be 100% accurate, it is a very good idea to perform an SHA-256 hash comparison check. As its name suggests, an SHA-256 hash is 256 bits long. In this article, we will have a look at how to generate an SHA-256 Hash/Checksum using the command line. 

### What Is SHA256?

[SHA-256 (Secure Hash Algorithm 256-bit)](https://www.geeksforgeeks.org/computer-networks/sha-256-and-sha-3/) is a cryptographic hash function designed by the NSA and part of the SHA-2 family. It produces a 256-bit (32-byte) fixed-size hash value from an input of any length. SHA-256 is widely used for security applications and protocols, including [TLS and SSL,](https://www.geeksforgeeks.org/computer-networks/difference-between-secure-socket-layer-ssl-and-transport-layer-security-tls/) for integrity verification and [digital signatures. ](https://www.geeksforgeeks.org/computer-networks/digital-signatures-certificates/)It is considered secure and resistant to collisions, where two different inputs produce the same hash value. SHA-256 operates by repeatedly applying a series of bitwise operations and modular additions to process data in 512-bit chunks. 

***\*Note:\**** Refer to this [article](https://www.geeksforgeeks.org/java/sha-256-hash-in-java/) to generate a SHA-256 Hash

### sha256sum on Linux

`sha256sum` is a command-line utility in Linux used to compute and verify SHA-256 hash values of files. You can use it to ensure data integrity and verify that files have not been altered.

To generate a SHA-256 checksum for a file:

```
sha256sum filename
```

To verify a file against a provided checksum:

```
sha256sum -c checksumfile
```

The `checksumfile` should contain the expected hash followed by the filename.

# References

* https://www.geeksforgeeks.org/linux-unix/generating-an-sha-256-hash-from-the-command-line/
