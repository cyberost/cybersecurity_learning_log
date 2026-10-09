# Password Hash Auditing with John the Ripper

## Objective

Evaluate the strength of sample password hashes using a password-auditing tool in a controlled lab.

## Lab Environment

* Operating system: Kali Linux
* Tool: John the Ripper
* Hash type: Raw MD5
* Technique: Wordlist-based password auditing

## Methodology

1. Prepared a file containing five sample MD5 hashes.
2. Ran John the Ripper against the hashes.
3. Reviewed recovered passwords using the results command.
4. Tested wordlist-based cracking.

## Results

* Total sample hashes: 5
* Hashes recovered: 4
* Hashes not recovered: 1

The results demonstrate that some passwords were recoverable with the tested approach. The remaining hash was not recovered during the exercise; this does not prove that its password is secure.

## Security Recommendations

* Use Argon2id or another suitable password-hashing algorithm.
* Generate a unique salt for every password.
* Enforce long, unique passwords and support a password manager.
* Use multifactor authentication where appropriate.

## Conclusion

This lab demonstrated how password-auditing tools can identify weak passwords and why secure password storage is essential.

## Ethical Use

Testing was performed on sample hashes in a controlled educational environment.
