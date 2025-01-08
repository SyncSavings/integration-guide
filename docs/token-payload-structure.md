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
    "sortCode": "60-83-71",
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

- **userId**: _(string, required)_ A unique identifier for the Saver.
- **firstName**: _(string, required)_ The given name of the Saver.
- **lastName**: _(string, required)_ The family name of the Saver.
- **email**: _(string, required)_ The email address of the Saver.
- **dateOfBirth**: _(string <date>, required)_ The date of birth of the Saver in ISO 8601 format.
- **mobileNumber**: _(string, required)_ The mobile phone number of the Saver in international format (e.g., "+447123456789").
- **address**: _(object, required)_ The Saver's UK address details:
  - **property**: _(string, required)_ How the Saver's residence is identified.
  - **street**: _(string, required)_ The street name of the Saver's address.
  - **city**: _(string, required)_ The city name of the Saver's address.
  - **country**: _(string, required)_ A 2-character country code in ISO 3166 format (e.g., "GB").
  - **postCode**: _(string, required)_ The postal code for the Saver's address.
- **sourceAccountDetails**: _(object, required)_ This is the bank account where Withdrawal Transactions will be paid to:
  - **accountNumber**: _(string, required)_ The bank account number.
  - **sortCode**: _(string, required)_ The sort code of the bank account.
  - **accountOwner**: _(string, required)_ The name of the account owner.
- **institution**: _(string, optional)_ If applicable, this can identify the Saver's employer or the source of aggregated data.
- **employment**: _(object, required)_ The Saver's employment details:
  - **industry**: _(string, required)_ The industry in which the Saver works. Allowed values include:
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
  - **occupation**: _(string, required)_ The Saver’s specific job role or occupation. This is a very long enum of possible values (e.g., "marketer", "software-engineer", "nurse"). The full list of values can be provided upon request.
  - **status**: _(string, required)_ The Saver's employment status. Allowed values:
    - "employed"
    - "retired"
    - "self-employed"
    - "unemployed"
  - **income**: _(object, required)_ Details of the Saver's income:
    - **currency**: _(string, required)_ The currency of the Saver's income in ISO 4217 format (e.g., "GBP").
    - **value**: _(number, required)_ The monetary value of the Saver's income.
- **sourceOfFunds**: _(string, required)_ The nature of the money being used to fund the bank account. Allowed values include:
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
- **taxResidency**: _(string, required)_ The country where the Saver is a tax resident. Currently limited to "GB".

{: .important }
Ensure data accuracy to prevent account creation issues.
