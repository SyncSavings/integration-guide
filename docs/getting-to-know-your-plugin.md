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

<style>
td, th {
   border: none!important;
   width: 50%;
   text-align: center;
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
  width: 250px;
}
</style>