# Module 2 – Password Cracking with NetworkWalks Tools

## Objective

Use the **NetworkWalks Hash Calculator** and **NetworkWalks Password Cracker** to recover the password for the supplied protected PDF, `My Locked PDF1.pdf`.

This browser-based exercise demonstrates the two main stages of a password-cracking workflow: extracting the PDF hash and testing password candidates against that hash. It also reinforces why weak passwords can put protected files at risk.

## What this lab demonstrates

- Extracting a PDF hash using a browser-based tool.
- Understanding why the complete hash value and correct format matter.
- Submitting the extracted hash to a password-cracking tool.
- Verifying the recovered password by opening the protected PDF.

## Environment and tools

| Item | Details |
|---|---|
| Operating system | Windows laptop (the tools also run in a browser on Kali Linux) |
| Hash extraction | [NetworkWalks Hash Calculator](https://networkwalks.com/hash-calculator/) |
| Password recovery | [NetworkWalks Password Cracker](https://networkwalks.com/password-cracker/) |
| Test file | `My Locked PDF1.pdf`, supplied for the lab |

No local cracking-tool installation was required for this exercise because both NetworkWalks tools run in a web browser.

## Walkthrough

### 1. Obtain the supplied protected PDF

Download `My Locked PDF1.pdf` from the [NetworkWalks lab instructions](https://networkwalks.com/project-task-lab-password-cracking-with-networkwalks-tools/).

### 2. Extract the PDF hash

Open the [NetworkWalks Hash Calculator](https://networkwalks.com/hash-calculator/) in a browser and upload the protected PDF. The tool processes the file and returns a PDF hash beginning with `$pdf$`.

![NetworkWalks Hash Calculator used to extract the PDF hash](1.%20Extract%20Hash.png)

*Figure 1: Extracting the hash from the supplied protected PDF.*

Copy the complete hash value. The lab instructions emphasise that the full value must be copied without missing any characters.

### 3. Submit the hash to the Password Cracker

Open the [NetworkWalks Password Cracker](https://networkwalks.com/password-cracker/) and paste the extracted hash into the input field. Start the attack and allow the tool to test password candidates.

The time required can vary depending on the password and the cracking process.

### 4. Review the recovered password

The tool reports the recovered password when it finds a match. The lab result is shown in the screenshot below. The actual password is intentionally not repeated in this documentation.

![Password recovery result from the NetworkWalks Password Cracker](2.%20Extracted%20Password.png)

*Figure 2: The Password Cracker reporting the recovered password.*

### 5. Verify the result

Open the original protected PDF and enter the recovered password. Confirm that the document opens successfully.

![Lab completion and captured flag](3.%20Captured%20Flag.png)

*Figure 3: Completion evidence from the exercise.*

The recovered password and challenge flag are not reproduced in this README.

## Key takeaways

- A password-protected file can expose a hash that may be tested offline by a password-cracking tool.
- The extracted hash must be complete and in the format expected by the cracking tool.
- Password-cracking tools test candidate passwords; they do not simply reverse a secure hash to reveal the original password.
- Weak and commonly used passwords are more susceptible to guessing attacks.
- The browser-based workflow makes the process accessible without installing a local cracking application, but the security principles are the same.

## Defensive relevance

Use long, unique passwords or passphrases for protected documents. Avoid common words and predictable patterns, and do not reuse passwords across services or files. A password manager can help generate and store unique credentials. For accounts that support it, multi-factor authentication provides additional protection, although it does not directly protect a standalone PDF file.

## References

- [NetworkWalks – Week 3, Module 2 lab instructions](https://networkwalks.com/project-task-lab-password-cracking-with-networkwalks-tools/)
- [NetworkWalks Hash Calculator](https://networkwalks.com/hash-calculator/)
- [NetworkWalks Password Cracker](https://networkwalks.com/password-cracker/)

---

*Completed as part of the NetworkWalks Week 3 cybersecurity learning activities. Use password-cracking tools only on files and hashes you own or are explicitly authorised to assess.*
