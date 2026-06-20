# RSA Protocol Verification with ProVerif

Formal verification of RSA-based cryptographic protocols using ProVerif 2.05.
This project analyzes confidentiality and authentication properties across 4 protocol stages,
against a Dolev-Yao active attacker.

## Files

| File | Description | Confidentiality | Authentication |
|------|-------------|-----------------|----------------|
| 01_rsa_confidentiality.pv | RSA encryption only | ✅ holds | — |
| 02_rsa_authentication_vulnerable.pv | Naive auth (no signature) | — | ❌ fails |
| 03_rsa_sign_and_encrypt_detached.pv | Detached sign + encrypt | ❌ fails | ✅ holds |
| 04_rsa_sign_then_encrypt_secure.pv | Sign-then-encrypt | ✅ holds | ✅ holds |

## How to Run

Install ProVerif: https://bblanche.gitlabpages.inria.fr/proverif/

```bash
proverif 01_rsa_confidentiality.pv
proverif 02_rsa_authentication_vulnerable.pv
proverif 03_rsa_sign_and_encrypt_detached.pv
proverif 04_rsa_sign_then_encrypt_secure.pv
```

## Author
MESSAOUDI KHADIJA — University of Urbino Carlo Bo
Supervisor: Prof. Alessandro Aldini
