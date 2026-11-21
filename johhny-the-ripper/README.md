# Module 1 – Password Cracking with John the Ripper

## Objective

Use **John the Ripper (JTR)** and its graphical interface, **Johnny**, to recover the password for the NetworkWalks-provided protected PDF file, `My Locked PDF1.pdf`.

The exercise demonstrates a typical password-recovery workflow: extract the PDF's password hash, save it in a format that John the Ripper can process, run an attack against that hash, and verify the recovered password by opening the PDF.

## What this lab demonstrates

- The role of password hashes in password-recovery testing.
- How a PDF hash extractor can produce a cracking target from a protected PDF.
- How Johnny provides a graphical way to configure and run John the Ripper.
- Why weak or predictable passwords are vulnerable to offline guessing attacks.

## Environment and tools

| Item | Details |
|---|---|
| Operating system | Windows PC |
| Cracking tool | John the Ripper |
| Graphical interface | Johnny |
| Hash extraction | OnlineHashCrack PDF Hash Extractor |
| Test file | `My Locked PDF1.pdf`, supplied for the lab |

John the Ripper is also available on Kali Linux, where it may already be installed. The documented workflow here follows the Windows instructions from the lab.

## Walkthrough

### 1. Obtain John the Ripper and Johnny

Download John the Ripper from the [official Openwall website](https://www.openwall.com/john/). Download the Johnny graphical interface from the [Johnny project page](https://openwall.info/wiki/john/johnny), then install and launch it.

### 2. Configure Johnny to use John the Ripper

Open Johnny's settings and browse to the John the Ripper executable, `john.exe`, in the extracted John the Ripper folder. In the lab package, the executable is located in the `run` directory.

![Johnny configured to use the John the Ripper executable](1.%20Configuring%20Johnny%20The%20Ripper.png)

*Figure 1: Configuring Johnny with the John the Ripper executable.*

### 3. Extract the PDF hash

Download the supplied protected PDF. Use the [OnlineHashCrack PDF Hash Extractor](https://www.onlinehashcrack.com/tools-pdf-hash-extractor.php) to upload the file and extract its PDF hash.

The extracted value uses a PDF hash format beginning with `$pdf$`. Copy the complete value. The lab instructions note that any wrapper characters added by the extractor, such as a leading `b'`, should be removed so that the saved hash is in the expected format.

![Extracted PDF hash](2.%20Extracted%20Hash.png)

*Figure 2: The PDF hash extracted for the password-recovery exercise.*

### 4. Save the hash to a text file

Open a text editor, paste the complete hash and save it as `hash1.txt`. Keep the hash intact and ensure that it is the only relevant hash value in the file.

![Saving the extracted hash as hash1.txt](3.%20Saving%20hash%20as%20hash1.txt.png)

*Figure 3: Preparing the extracted hash in a text file.*

### 5. Load the hash into Johnny

Return to Johnny and select **Open password file**. Browse to the `hash1.txt` file and open it. Johnny should load the PDF hash as the password-cracking target.

![Opening the password file in Johnny](4.%20Open%20Password%20File%20format.png)

*Figure 4: Loading the prepared hash file into Johnny.*

### 6. Start the password-recovery attempt

Select **Start new attack** in Johnny. The tool will test password candidates against the loaded hash. The time required depends on the password, the attack method and the available computing resources.

![Starting the password-cracking attack](5.%20Start%20Attack.png)

*Figure 5: Starting the attack in Johnny.*

### 7. Review the result and verify the PDF

The lab evidence shows that Johnny recovered the password. Use the recovered password to open the supplied PDF and confirm that the document is accessible.

![John the Ripper reports a recovered password](6.%20Password%20Found.png)

*Figure 6: Password recovery reported by Johnny.*

![Lab completion evidence](7.%20Flag%20Found.png)

*Figure 7: Completion evidence from the lab.*

The recovered password and challenge flag are not reproduced in this README.

## Key takeaways

- **Hash extraction comes before cracking:** the tool needs a supported hash representation to test password candidates.
- **Hash format matters:** an incomplete or incorrectly formatted hash may prevent the cracking tool from processing the target.
- **Weak passwords are vulnerable:** passwords that are short, common or predictable are more likely to appear in candidate lists.
- **Johnny is a graphical front end:** it simplifies configuration and interaction with John the Ripper, but the underlying cracking engine performs the work.
- **Recovery is not guaranteed:** a tool may fail to recover a password if the password is not covered by the attack strategy or available candidates, or if the computational cost is too high.

## Defensive relevance

This exercise reinforces the importance of using long, unique and unpredictable passwords. Organisations should also use secure password-storage mechanisms, prevent password reuse, enable multi-factor authentication where possible, and monitor for exposed credentials.

## References

- [John the Ripper – Official website](https://www.openwall.com/john/)
- [Johnny GUI – John the Ripper front end](https://openwall.info/wiki/john/johnny)
- [OnlineHashCrack – PDF Hash Extractor](https://www.onlinehashcrack.com/tools-pdf-hash-extractor.php)
- [NetworkWalks – Week 3, Module 1 lab instructions](https://networkwalks.com/project-task-lab-password-cracking-with-jtr/)

---

*Completed as part of the NetworkWalks Week 3 cybersecurity learning activities. Use password-cracking tools only on files and hashes you own or are explicitly authorised to assess.*
