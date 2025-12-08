# Symmetric vs Asymmetric Encryption Notes

## Symmetric Encryption
- One shared key encrypts and decrypts.
- Fast and efficient for bulk data.
- Used in VPNs, disk encryption, HTTPS sessions.

## Asymmetric Encryption
- Public key encrypts; private key decrypts.
- Solves key exchange over untrusted networks.
- Used for authentication, signatures, TLS handshakes.

## AES (Symmetric)
- Standard algorithm for fast data encryption.
- Powers HTTPS traffic after handshake, WPA, disk encryption.

## RSA (Asymmetric)
- Older key exchange and signing system.
- Based on factoring large primes.
- Used in certificates, signatures.

## ECC (Asymmetric)
- Modern algorithm offering stronger security with smaller keys.
- Ideal for cloud, mobile, IoT due to speed and low overhead.

## Trade-off Model
- Asymmetric for key exchange and identity.
- Symmetric for data transport due to speed.

## Hybrid TLS Pattern
Client → Asymmetric handshake → Shared secret generated → AES session encryption
