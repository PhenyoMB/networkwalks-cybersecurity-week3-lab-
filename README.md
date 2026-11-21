# NetworkWalks Cybersecurity Labs – Week 3

## Overview

This week's labs focused on **password security and password recovery**. The exercises demonstrate how an attacker may attempt to recover a password from a protected file when the password is weak or predictable, and why strong passwords and secure credential practices are important.

A key concept across both exercises is the difference between **encryption** and **hashing**. Encryption is designed to be reversible when the correct key is available. Hashing is a one-way process that produces a value which can be checked against password guesses. In a password-cracking workflow, a tool attempts candidate passwords and compares their derived values with the extracted hash.

The practical work used two approaches:
- **John the Ripper (JTR) with Johnny:** a locally installed password-cracking tool and its graphical interface.
- **NetworkWalks online tools:** a browser-based Hash Calculator and Password Cracker workflow.

Both exercises used the supplied password-protected PDF as the test file. The purpose was to understand the process and demonstrate the security implications of weak passwords, not to access anyone else's files or accounts.

## Lab modules

| Module | Focus | Tools | Evidence |
|---|---|---|---|
| [Module 1 – John the Ripper](./johhny-the-ripper/README.md) | Extract a PDF hash and attempt password recovery using JTR through Johnny | John the Ripper, Johnny GUI, PDF hash extractor | Configuration, hash extraction, hash file preparation, attack and recovery screenshots |
| [Module 2 – NetworkWalks Tools](./networkwalks-tools/README.md) | Extract a PDF hash with the NetworkWalks Hash Calculator and recover the password using its Password Cracker | NetworkWalks Hash Calculator, NetworkWalks Password Cracker | Extracted hash, recovered-password and completion screenshots |

## What I learned

- Password cracking can be performed against an extracted hash without repeatedly opening the protected file.
- A weak or commonly used password can be recovered when it appears among the candidates tested by a cracking tool.
- The hash extraction step is important: the cracking tool needs the correct hash format and the complete value.
- Graphical tools such as Johnny can make password-cracking workflows easier to follow, while still relying on the underlying John the Ripper engine.
- A successful lab demonstration is not proof that every password can be cracked. Results depend on the password, the candidate set or attack method, the hash format and available computing resources.
- Strong, unique passwords and password managers reduce the risk associated with predictable or reused credentials. Where supported, multi-factor authentication adds another layer of protection.

## Evidence

Screenshots are embedded in the individual module READMEs so that each image appears alongside the step it documents.

- [John the Ripper / Johnny evidence](./johhny-the-ripper/README.md)
- [NetworkWalks tools evidence](./networkwalks-tools/README.md)

## Environment

- **Operating system:** Windows PC
- **File used:** NetworkWalks-provided password-protected PDF
- **Approach:** GUI-based password recovery workflows
- **Tools:** John the Ripper, Johnny, NetworkWalks Hash Calculator and NetworkWalks Password Cracker

The Week 3 task material also notes that John the Ripper is available on Kali Linux. The documented practical steps in this repository follow the Windows workflow.

## Security considerations

These exercises were completed for cybersecurity learning using the file supplied for the lab. Password recovery should only be performed against files, hashes or systems that you own or have explicit permission to assess.

The repository intentionally does not reproduce the recovered password, extracted hash or challenge flag. Avoid publishing credentials, hashes or other sensitive values in screenshots or source files.

## References

- [NetworkWalks – Password Cracking with John the Ripper](https://networkwalks.com/project-task-lab-password-cracking-with-jtr/)
- [NetworkWalks – Password Cracking with NetworkWalks Tools](https://networkwalks.com/project-task-lab-password-cracking-with-networkwalks-tools/)
- [John the Ripper – Official website](https://www.openwall.com/john/)
- [Johnny GUI – John the Ripper front end](https://openwall.info/wiki/john/johnny)
- [NetworkWalks Hash Calculator](https://networkwalks.com/hash-calculator/)
- [NetworkWalks Password Cracker](https://networkwalks.com/password-cracker/)

---

*This repository documents practical learning activities completed as part of the NetworkWalks cybersecurity labs. It is intended for educational purposes only.*
