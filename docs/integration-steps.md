---
title: Integration Steps
nav_order: 2
layout: default
---

# Integration Steps

{: .no_toc }


## Table of contents

{: .no_toc .text-delta }

1. TOC
{: toc }

---

## Generate Credentials

Before starting, you’ll need to create a unique key pair to secure your integration with the Sync Savings platform, this will be made up of a private key and public key.

### How to Generate the Key Pair

Generate the key pair with the following specifications:

- **Key Type**: Ed25519
- **Format**: PEM format (the standard for web security)

Generate your key pair using the below steps:
```bash
openssl genpkey -algorithm ed25519 -out sync-plugin-private.pem
```
```bash
openssl pkey -in sync-plugin-private.pem -pubout -out sync-plugin-public.pem
```

**Action**: Generate your key pair as described, then securely send the public key to your Sync Savings integration contact. You will also receive your distributor ID during this process.

## Customise your plugin

To provide a seamless and personalised experience, the platform can be customised to reflect your brand design.

**Provide the following design assets during onboarding:**

- **Typography**:
  - **Title Font**: Specify the font family and weight for headings.
  - **Body Font**: Specify the font family and weight for general text.

{: .note }
💡 For fonts that are publicly available, please share the font name and weight. If the fonts are proprietary or purchased, provide either the font files or a functional CDN link.

- **Colours (RGB values)**:
  - **Heading Colour**: For main headings and titles.
  - **Body Colour**: For general text.
  - **Primary Colours**: To highlight buttons and interactive elements.
  - **Background Colour**: Main background colour of the platform.
- **Logo**:
  - Displayed during the user sign-up journey within the platform.

{: .note }
💡 Please provide a high-definition image with transparent background.

**Action**: Send your design assets, including font information, colour codes, and logo files, to your Sync Savings integration contact.

## Generate JWT Tokens

To access the platform, you'll need to generate a JWT token containing your user's data.

**Steps to Generate a JWT Token:**

1. **Authenticate the User**: Ensure the user is logged into your system.

{: .warning }
❗Only allow logged-in users to generate a token with their email and user ID. Failing to enforce this could expose sensitive user data to attackers.

2. **Prepare User Data**: Collect the required user information (see [Token Payload Structure](https://syncsavings.github.io/integration-guide/docs/token-payload-structure.html)).
3. **Create the Token Payload**: Construct a JSON object with the user's data.
4. **Sign the Token**: Use your private key to sign the JWT token.

{: .note }
💡 The token expiry (`expiresIn`) does not affect the session length, as Sync Savings will validate the token and create a session that lasts for 1 hour, regardless of the token's own expiry time.

**Example in Node.js using `jsonwebtoken`:**

```js
import { SignJWT } from 'jose';

const userData = {
  userId: 'abc123',
  distributorId: 'my-company',
  title: 'mr',
  firstName: 'Christopher',
  lastName: 'Robin',
  email: 'christopher.robin@sync-savings.com',
  dateOfBirth: '1969-12-31',
  mobileNumber: '+447123456789',
  address: {
    property: '145',
    street: 'London Street',
    city: 'London',
    country: 'GB',
    postCode: 'EC3N 4AB',
  },
  sourceAccountDetails: {
    accountNumber: '11223344',
    sortCode: '608371',
    accountOwner: 'Christopher Robin',
  },
  institution: 'Winslow Luggages',
  employment: {
    industry: 'marketing-advertising-and-pr',
    status: 'employed',
    income: {
      currency: 'GBP',
      value: 54321.09,
    },
  },
  sourceOfFunds: 'salary-or-bonus',
  taxResidency: 'GB',
};

// Add your private key here
const privateKey = `-----BEGIN PRIVATE KEY-----
abcdefgh12345678
-----END PRIVATE KEY-----`;

const privateKeyObj = await importPKCS8(privateKey, "EdDSA");

const jwt = await new SignJWT(userData)
  .setProtectedHeader({ alg: 'EdDSA' })
  .setIssuedAt()
  .setExpirationTime('30m')
  .sign(privateKeyObj);
```

{: .warning }
Implement secure token generation in your backend, ensuring only authenticated users can generate tokens.

## Direct Users to the Platform

Once the JWT token is generated, redirect the user to the Sync Savings platform.

**Access URL Format:**

```
https://app.sync-savings.com?token=<token>
```

{: .important}
Update your application to redirect users to the Sync Savings platform with the token appended to the URL.
