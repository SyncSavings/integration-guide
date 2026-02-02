---
title: Know the Plugin
nav_order: 6
layout: default
---

# Getting to Understand your Plugin

As simple as the Plugin is to use, there are a number of ways it can adapt to it's surroundings. Use this page to help **you** know what to expect from **your** Plugin

## Landing Screen

### Existing Users

There are two possible landing spots for returning users, depending on whether a user that has been pre-authenticated (i.e. attached payload is generated and signed by **you** and is specific to that user) or needs to provide an email and password:

![Password Log-in Screen](/images/login_screen.png) | ![Account Screen](/images/account_screen.png)
:---:|:---:
Password users are directed to a branded login-screen | Pre-authenticated users are directed towards their account page

### New Users

New users are directed to our Onboarding flow. Which begins with our basic facts and information screen.

![Landing Explainer Screen](/images/image.png)

## Onboarding

All new users are required to provide a minimum amount of information needed to open their savings account, authorise withdrawals and be informed of updates. A large amount of this information will be prefilled from the token payload (see [here](https://syncsavings.github.io/integration-guide/docs/token-payload-structure.html)) to greatly simplify the process. The following pages are added to give new users the opportunity to double check data provided and provide missing data.

{: .note }
💡 Data provided by **you** in the token payload is not **overridable** by the user but is able to be **previewed**.
Data updated in your records (that are reflected in token payloads on subsequent logins) will be updated automatically in ours.

Below, we will go through key steps in the Onboarding flow and some of the behaviours implemented to help guide news users through the journey.

### Login Details

Password authenticated users must provide a valid email address and password (repeated). This page will be omitted from the flow for plugin distributors that pre-authenticate their users.

![Login Details Screen](/images/login_details.png)

### Eligibility

This page prompts users to provide some details about their employment and make declarations about their tax and residency statues and, therefore, their eligibility to access savings through Sync Savings.

There are a few different ways this page can present depending on distributor-level configuration and data within the token payload.

![Empty Eligibility Form](/images/signup_eligibility-empty.png) | ![Prefilled Eligibility Form](/images/signup_eligibility-prefilled.png) | ![Hidden Fields Eligibility Form](/images/signup_eligibility-hidden.png)
:---:|:---:|:---:
`employment.status` and `employment.industry` token payload fields are empty and configuration provides on default or fallback values | Token payload fields are empty and configuration values are marked as `PREFILLED`. Status and Industry fields are editable by user | Configuration values are marked as `FIXED` or values provided by token payload. If both are provided, configuration value is used as backing value.

<style>
td, th {
   border: none!important;
   text-align: center;
}
table {
  table-layout: fixed;
  width: 100%;
}
.table-wrapper {
  drop-shadow: none!important;
  box-shadow: none!important;
}

p:has(>img) {
    display:flex;
    justify-content: center;
}

img {
  /* max-width: 250px; */
}
</style>