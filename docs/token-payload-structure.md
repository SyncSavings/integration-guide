---
title: Token Payload Structure
nav_order: 3
layout: default
---

# Token Payload Structure

```json
{
  "userId": "123abc",
  "email": "christopher.robin@sync-savings.com",
  "distributorId": "Sync",
  "firstName": "Christopher",
  "lastName": "Robin",
  "dateOfBirth": "1969-12-31",
  "mobileNumber": "447123456789",
  "property": "145",
  "street": "London Street",
  "city": "London",
  "country": "GB",
  "postCode": "EC3N 4AB",
  "isUkTaxpayer": true,
  "isUkResident": true,
  "employmentStatus": "employment-status",
  "primarySourceOfIncome": "salary",
  "industry": "sales",
  "occupation": "customer-service" 
}
```

**Field Descriptions:**

{: .important }
All fields are required unless agreed otherwise.

- **userId**: Unique identifier for the user in your system.
- **email**: User's email address.
- **distributorId**: Your assigned distributor ID, provided by Sync Savings.
- **firstName**/**lastName**: User's full name.
- **dateOfBirth**: Format `YYYY-MM-DD`.
- **mobileNumber**: UK phone number in international format.
- **property**, **street**, **city**, **country**, **postCode**: User's address details.
- **isUkTaxpayer**/**isUkResident**: Boolean values indicating UK tax and residency status.
- **employmentStatus**: User's current employment status (e.g., "employed", "self-employed", "unemployed", "retired").
- **primarySourceOfIncome**: User's main source of income (e.g., "salary", "business", "investments", "pension").
- **industry**: The industry sector in which the user works (e.g., "technology", "healthcare", "finance", "education").
- **occupation**: The user's specific job role or occupation (e.g., "software developer", "nurse", "accountant", "teacher").

{: .important }
Ensure data accuracy to prevent account creation issues.