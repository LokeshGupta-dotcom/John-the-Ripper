# John-the-Ripper

## Objective
The Detection Lab is aimed to demonstrate the process of password cracking using John the Ripper. This simulation showcases how password hashes can be tested for weaknesses using dictionary attacks and highlights the importance of removing sensitive files and tools after use to maintain a secure environment.

## Skills Learned
- Installed and configured John the Ripper for password cracking simulations.
- Generated and analyzed password hashes using OpenSSL for MD5 hashing.
- Created and managed password hash files for testing purposes.
- Decompressed and managed large wordlists for effective penetration testing.
- Performed password cracking with John the Ripper using default and custom wordlists.
- Gained hands-on experience with ethical use of cybersecurity tools.

## Tools Used
- Linux Operating System (Kali Linux): Used as the offensive security platform for password cracking and testing.
- Password Cracking Tool (John the Ripper): Utilized for analyzing and cracking password hashes using default methods and dictionary attacks.
- Cryptographic Utility (OpenSSL): Employed to generate MD5 password hashes for testing.

## Steps

#### On Kali Linux VM
- Update the system:
```bash
  sudo apt update && sudo apt upgrade -y
```
-Install John the Ripper, a password-cracking tool:
![image](https://github.com/user-attachments/assets/bf99c82a-8471-4dd7-97e6-e0bbd8ca8ba2)

- Create an MD5 hash of the password password123 using OpenSSL:
```bash
  echo -n 'abc123' | openssl dgst -md5
```
![image](https://github.com/user-attachments/assets/6268d6aa-ad69-4903-a3fc-897588306629)
This hash will be used to simulate a password cracking scenario.

-Store the MD5 hash in a file named password.txt in the format expected by John the Ripper
```bash
  echo "lokeshUser1:e99a18c428cb38d5f260853678922e03" > password1.txt
```
![image](https://github.com/user-attachments/assets/8fb439e1-9e21-4cc7-affa-0eb1f41b33d3)


-Run John the Ripper to attempt cracking the password
```bash
  john password1.txt
```
![image](https://github.com/user-attachments/assets/28c7341d-30ab-42ff-a0b6-a94a3e50e03d)

-
#### If the default method fails or is too slow, use a dictionary attack with the RockYou wordlist.
- sudo gunzip /usr/share/wordlists/rockyou.txt.gz
```bash
  sudo gunzip /usr/share/wordlists/rockyou.txt.gz
```
- Run John with the wordlist
  
```bash
  john --wordlist=/usr/share/wordlists/rockyou.txt password1.txt
```
![image](https://github.com/user-attachments/assets/173e17b5-5000-46ed-8844-944708980fcd)


- Verify the Cracked Password
 ```bash
  john --show password.txt
```
![image](https://github.com/user-attachments/assets/493d089a-b6bf-4d6e-ab83-39ea20054170)

#### To ensure a secure environment, remove all traces of the test
- Delete the Password File
```bash
  rm password1.txt
```
- Uninstall John the Ripper
```bash
  sudo apt-get remove john
```

## Conclusion
This project highlights the importance of strong password policies and demonstrates the potential risks associated with weak passwords. It also underscores the responsibility of cybersecurity professionals to handle sensitive data ethically and securely.












