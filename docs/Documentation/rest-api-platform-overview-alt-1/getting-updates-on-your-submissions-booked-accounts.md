---
title: "Getting Updates on Your Accounts"
slug: "getting-updates-on-your-submissions-booked-accounts"
excerpt: ""
hidden: false
metadata: 
  image: []
  robots: "index"
createdAt: "Sat Jul 27 2019 19:27:24 GMT+0000 (Coordinated Universal Time)"
updatedAt: "Fri Nov 01 2019 16:57:12 GMT+0000 (Coordinated Universal Time)"
---
We understand the importance of staying up to date on the key details of your application submissions – both during the underwriting process and post-booking.  To help manage this process, we've created a series of endpoints that can be called at anytime.

# Getting a List of Accounts

| Endpoint                                       |
| :--------------------------------------------- |
| **[Account List](ref:ideaapi_getaccountlist)** |

Calling the **Account List** endpoint will return a list of all Accounts we have received from you.  The responses received from this call will contain key, high-level, details on each Account.  You can control the number of Account records returned by passing in additional parameters like date, product type, status, etc.

# Getting Detailed Information on an Individual Account

| Endpoint                                       |
| :--------------------------------------------- |
| **[Account Info](ref:ideaapi_getaccountinfo)** |

Should you want or need detailed account level information (beyond what is returned in the Account List call) you should use our **Account Info** endpoint. Simply supply the Account ID that we have provided you with and a detailed breakdown of that account will be returned.
