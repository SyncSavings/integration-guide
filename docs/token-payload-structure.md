---
title: Token Payload Structure
nav_order: 3
layout: default
---

# Token Payload Structure

```json
{
  "userId": "abc123",
  "distributorId": "my-company",
  "title": "mr",
  "firstName": "Christopher",
  "lastName": "Robin",
  "email": "christopher.robin@sync-savings.com",
  "dateOfBirth": "1969-12-31",
  "mobileNumber": "+447123456789",
  "address": {
    "property": "145",
    "street": "London Street",
    "city": "London",
    "country": "GB",
    "postCode": "EC3N 4AB"
  },
  "sourceAccountDetails": {
    "accountNumber": "11223344",
    "sortCode": "608371",
    "accountOwner": "Christopher Robin"
  },
  "institution": "Winslow Luggages",
  "employment": {
    "industry": "marketing-advertising-and-pr",
    "occupation": "marketer",
    "status": "employed",
    "income": {
      "currency": "GBP",
      "value": 54321.09
    }
  },
  "sourceOfFunds": "salary-or-bonus",
  "taxResidency": "GB"
}
```

**Field Descriptions:**

{: .important }
All fields are required unless agreed otherwise.

- **userId**: A unique identifier for the Saver.
- **firstName**: The given name of the Saver.
- **lastName**: The family name of the Saver.
- **distributorId**: The ID unique to your platform (Provided by Sync Savings)
- **email**: The email address of the Saver.
- **dateOfBirth**: The date of birth of the Saver in ISO 8601 format.
- **mobileNumber**: The mobile phone number of the Saver in international format (e.g. "+447123456789").
- **address**: The Saver's UK address details:
  - **property**: How the Saver's residence is identified.
  - **street**: The street name of the Saver's address.
  - **city**: The city name of the Saver's address.
  - **country**: A 2-character country code in ISO 3166 format (e.g. "GB").
  - **postCode**: The postal code for the Saver's address.
- **sourceAccountDetails**: This is the bank account where Withdrawal Transactions will be paid to:
  - **accountNumber**: The bank account number.
  - **sortCode**: The sort code of the bank account.
  - **accountOwner**: The name of the account owner.
- **institution**: _(optional)_ If applicable, this can identify the Saver's employer or the source of aggregated data.
- **employment**: The Saver's employment details:
  - **industry**: The industry in which the Saver works. Allowed values include:
    - "marketing-advertising-and-pr"
    - "sales"
    - "law"
    - "hospitality-and-events-management"
    - "personal-care-and-lifestyle"
    - "creative-arts-and-design"
    - "information-technology"
    - "environment-and-agriculture"
    - "media-and-internet"
    - "healthcare"
    - "property-and-construction"
    - "public-services-and-administration"
    - "law-enforcement-and-security"
    - "engineering-and-manufacturing"
    - "energy-and-utilities"
    - "recruitment-and-hr"
    - "teacher-training-and-education"
    - "leisure-sport-and-tourism"
    - "business-consulting-and-management"
    - "charity-and-not-for-profit-organizations"
    - "transport-and-logistics"
    - "science-and-pharmaceuticals"
    - "social-care"
    - "accountancy-banking-and-finance"
    - "retail-and-wholesale"
    - "social-and-humanities-scientists"
  - **occupation**: The Saver’s specific job role or occupation. This is a very long enum of possible values (e.g. "marketer", "software-engineer", "nurse"). The full list of values can be provided upon request.
  - **status**: The Saver's employment status. Allowed values:
    - "employed"
    - "retired"
    - "self-employed"
    - "unemployed"
  - **income**: Details of the Saver's income:
    - **currency**: The currency of the Saver's income in ISO 4217 format (e.g. "GBP").
    - **value**: The monetary value of the Saver's income.
- **sourceOfFunds**: The nature of the money being used to fund the bank account. Allowed values include:
  - "gambling-or-lottery"
  - "investments"
  - "property-or-asset-sale"
  - "business-income"
  - "savings"
  - "salary-or-bonus"
  - "student-loans-or-bursary"
  - "retirement-or-pension"
  - "legal-settlement"
  - "family-or-gifted"
  - "loan"
  - "inheritance"
- **taxResidency**: The country where the Saver is a tax resident in ISO 3166 format . Currently limited to "GB".

{: .important }
Ensure data accuracy to prevent account creation issues.
