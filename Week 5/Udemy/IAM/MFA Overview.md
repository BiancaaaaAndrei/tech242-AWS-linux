# AWS Certified Cloud Practitioner - Security Best Practices

## Overview

This section focuses on securing users and groups within AWS to protect against potential compromises. Two key defense mechanisms are discussed: Password Policy and Multi-Factor Authentication (MFA).

## Password Policy

- **Objective:** Strengthen account security through the implementation of a robust password policy.
  
- **Configuration Options:**
  - Set a minimum password length.
  - Specify character type requirements (uppercase, lowercase, numbers, non-alphanumeric characters).
  - Allow or disallow IAM users to change their passwords.
  - Enforce password expiration, e.g., every 90 days.
  - Prevent password reuse to enhance security.

## Multi-Factor Authentication (MFA)

- **Objective:** Add an extra layer of security by combining something the user knows (password) with something they own (security device).

- **Implementation Options:**
  1. **Virtual MFA Device:**
     - Use tools like Google Authenticator or Authy to generate tokens.
     - Support for multiple tokens on a single device for convenient use.

  2. **Universal 2nd Factor (U2F) Security Key:**
     - Physical device option, e.g., YubiKey by Yubico.
     - Supports multiple root and IAM users using a single security key.

  3. **Hardware Key Fob MFA Device:**
     - Provided by third-party vendors like Gemalto.
     - Offers a physical key fob for enhanced security.

  4. **Special Key Fob for AWS GovCloud:**
     - Exclusive option for users utilizing AWS GovCloud, provided by SurePassID.
- Example for Option 3 and Option 4:
![Key Fobs](<../../../readme-images/iam/mfa devices.png>)


