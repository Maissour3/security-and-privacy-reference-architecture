# Hardware Enclaves & Confidential Computing

Modern privacy-preserving computing platforms protect sensitive data in memory using hardware-isolated execution environments (confidential enclaves).

## Enclave Attestation Flow

Hardware enclaves execute within encrypted memory regions, proving their software integrity to remote clients through cryptographic attestation reports signed by hardware root-of-trust keys.

| Stage | Operational Action | Cryptographic Mechanism |
| :--- | :--- | :--- |
| Initialization | Measure binary code hash during enclave load | SHA-256 Measurement Register |
| Quote Generation | Hardware root key signs measurement report | ECDSA Silicon Certificate |
| Remote Verification | Client validates certificate chain and measurements | Intel SGX / AMD SEV Verification |
| Secret Provisioning | Client securely delivers decryption keys to enclave | Ephemeral Diffie-Hellman Key Exchange |

## Memory Encryption Primitives

Memory controller hardware executes AES-128 or AES-256 encryption across memory bus traces in real time, preventing physical memory snooping attacks by malicious infrastructure operators.
