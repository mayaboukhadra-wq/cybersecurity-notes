# Domain 1: Security Principles - CIA Triad Hands-on Lab

This lab demonstrates the practical application of **Confidentiality**, **Integrity**, and **Availability** (The CIA Triad) using native tools in **Kali Linux**.

---

## Full Terminal Execution 

```bash
# [1] Integrity Tasks: Checking and modifying file hashes
mkdir -p Certifications/isc2_cc
cd Certifications/isc2_cc

echo "My name is maya" > test_hash.txt
md5sum test_hash.txt
# Output: a043103d804ba5c9cac72f8de6bd7ba6

echo "My name is maya." > test_hash.txt
md5sum test_hash.txt
# Output: 5a8d1e23ff9ddac7a12576f3f84cbed5

# [2] Confidentiality Tasks: Creating and encrypting a secret file
echo "This is a secret password: maya2026" > secret.txt
gpg -c secret.txt
cat secret.txt
gpg -c secret.txt
cat secret.txt

# [3] Availability Tasks: Backing up and restoring data
tar -czvf backup_tar.gz test_hash.txt secret.txt
rm secret.txt test_hash.txt
ls -l
tar -xzvf backup_tar.gz

## Lab Proof 
[Kali Linux CIA Triad Lab](cia-triad-terminal.png)

