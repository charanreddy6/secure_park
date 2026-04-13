# 🔐 SecurePark — Vehicle Entry Management System

A browser-based secure parking management system built as a single HTML file. It demonstrates real-world security concepts including AES-256 encryption, SHA-256 hashing, multi-factor authentication (TOTP), and role-based access control — all running entirely client-side.

## Features

- **Multi-Factor Authentication (MFA)** — Two-step login with TOTP support (compatible with Microsoft Authenticator and any TOTP app). QR code setup on first login.
- **AES-256 Encryption** — Booking data is encrypted at rest using CryptoJS.
- **SHA-256 Hashing** — Passwords are salted and hashed; digital signatures use SHA-256 for entry verification.
- **Role-Based Access Control (ACL)** — Three roles: Regular User, VIP, and Administrator, each with different permissions.
- **Parking Slot Booking** — Visual grid of 20 slots with available / reserved / occupied states.
- **Entry Pass & QR Code** — Each booking generates a unique encrypted entry pass with a scannable QR code.
- **Vehicle Entry Verification** — Verify entry passes by booking ID with digital signature validation.
- **Admin Panel** — User management, access control matrix, and security audit logs (admin only).
- **Security Demo Tools** — Interactive demos for encryption/decryption, hashing, Base64 encoding, and digital signatures.
- **NIST SP 800-63-2 Compliant Registration** — Password policy enforced (min 8 chars, uppercase, lowercase, number, special character).

## Tech Stack

- Pure HTML, CSS, JavaScript — no build tools or frameworks
- [CryptoJS](https://cryptojs.gitbook.io/docs/) (via CDN) — AES & SHA-256 cryptography
- [QRCode.js](https://davidshimjs.github.io/qrcodejs/) (via CDN) — QR code generation
- Google Fonts: Orbitron + Space Mono

## Getting Started

No installation needed. Just open the file in a browser:

```bash
# Clone the repo
git clone https://github.com/your-username/SecurePark.git

# Open in browser
open SecurePark_Code/secure-parking-system.html
```

> Requires an internet connection on first load to fetch CDN scripts (CryptoJS, QRCode.js, Google Fonts).

## Usage

1. **Register** — Create an account with your vehicle details and choose a role.
2. **Login** — Enter credentials, then verify with your TOTP code (scan the QR on first login).
3. **Book a Slot** — Pick an available parking slot and set the duration.
4. **Entry Pass** — View your encrypted booking and QR code under "My Bookings".
5. **Verify Entry** — Use the booking ID or QR to verify an entry pass at the gate.
6. **Admin** — Log in as an admin to manage users, view the ACL matrix, and audit security logs.

## Security Concepts Demonstrated

| Concept | Implementation |
|---|---|
| Password Hashing | SHA-256 with random 128-bit salt |
| Data Encryption | AES-256 (CryptoJS) |
| MFA / TOTP | RFC 6238 compliant, ±1 window tolerance |
| Digital Signatures | SHA-256 hash of booking payload |
| Access Control | Role-based ACL (user / vip / admin) |
| Audit Logging | Timestamped security event log |

## Notes

- All data is stored in memory (no backend / no localStorage persistence). Refreshing the page resets the state.
- This project is intended for educational and demonstration purposes.

## License

MIT
