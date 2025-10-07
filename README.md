![Welcome Header](assets/welcome-header.gif)

This is AURAK's Coding Club official verification system for certificates! <br> This guide will help you verify your hard-earned achievements.

### Method 1: QR Code Scan (Recommended)

1. **Locate the QR Code** on your certificate
2. **Scan it with your phone's camera** app
3. **Tap the notification/link** that appears
4. **You'll see a verification page** confirming your achievement!

### Method 2: Manual Verification

If you can't scan the QR code:

1. Visit our verification portal: `undetermined`
2. Enter your **Certificate ID** (found on your certificate)
3. Click "Verify" to see your achievement details

### Certificates Tier System
| **Titan Tier** | **Trophy Tier** | **Tutor Tier** | **Taskforce Tier** |
|:----------:|:----------:|:--------------:|:---------------:|
| <img src="./assets/tier1.png" alt="Legend Certificate" width="120" height="90"> | <img src="./assets/tier2.png" alt="Leader Certificate" width="120" height="90"> | <img src="./assets/tier3.png" alt="Competitor Certificate" width="120" height="90"> | <img src="./assets/tier4.png" alt="Contributor Certificate" width="120" height="90"> |

###  Certificate JSON Structure

```json
{
  "certificateId": "YYYY-MM-STUDENTID (e.g., 2025-10-2021004938)",
  "issuer": "Always 'AURAK-Coding-Club' for authenticity",
  "achievement": "Description of accomplishment with tier level",
  "date": "Issue date in YYYY-MM-DD format",
  "tier": "Tier level (1-4): 1=Titan, 2=Trophy, 3=Tutor, 4=Taskforce",
  "status": "Certificate status: 'valid' or 'revoked'",
  "digitalSignature": "Base64-encoded RSA-PSS signature for verification"
}
```

> [!TIP]
> A revoked certificate means that it has been invalidated, but its signature remains verifiable.

### FAQ
__1. What if the verification fails?__ <br> Try scanning again with better lighting or with an adjusted distance (closer/further). If it still doesn't work, contact the club's crew with your Certificate ID. <br> 

__2. Can I share my verified certificate online?__ <br> Absolutely! Share your achievement on LinkedIn, portfolio, or social media. The verification link will always work. <br>

__3. What if I lost my certificate?__ <br> Contact the club's crew with your name and approximate issue date. We can reissue it. <br>

__4. How long does verification last?__ <br> Forever! Your achievements are permanently recorded in our system. <br>

__5. What is a Digital Signature?__ <br> A digital signature is a cryptographic mechanism that proves the authenticity and integrity of digital documents. In our certificate system, each certificate is digitally signed using RSA encryption with a 2048-bit key pair. <br>

__6. How do we create digital signatures?__ <br> 1. We create a SHA-256 hash of the certificate data (excluding the signature field). The hash is then encrypted using AURAK Coding Club's private RSA key. The encrypted signature is encoded in Base64 format for storage. Finally, the unique signature is added to the certificate JSON files hosted on this repository. <br>

__7. How can I verify my certificate's validity?__ <br> Scan the QR code on your certificate. This should direct you to the .json file in this repository, which contains information about your certificate. Finding your certificate's .json file on our repository is a positive indicator of its validity, but if you wish to go the extra mile, you can proceed to download your .json file and use our [cryptography-based web verification system](). This means that tampering with any certificate data will invalidate the digital signature. <br>

__8. Why do we use .json files to store data about your certificates?__ <br> JSON (JavaScript Object Notation) files are ideal for storing certificate information because they provide a structured, human-readable, and standardized format that works seamlessly across different platforms and programming languages. JSON's key-value pair structure perfectly matches the certificate data model (ID, issuer, achievement, date, etc.), making it easy to organize and access specific fields. Unlike binary formats, JSON files can be easily inspected, validated, and modified by both humans and machines, which is crucial for transparency in a certificate verification system. Additionally, JSON's lightweight nature ensures fast parsing and minimal storage overhead, while its universal support in web browsers, servers, and mobile applications makes it the perfect choice for a certificate system that needs to work across different environments. <br>

### 🎉 Congratulations on your achievement!
