---
title: "Line of Credit Functionality"
slug: "line-of-credit-functionality"
excerpt: ""
hidden: false
metadata: 
  image: []
  robots: "index"
createdAt: "Sat Jul 27 2019 21:54:44 GMT+0000 (Coordinated Universal Time)"
updatedAt: "Fri Apr 30 2021 14:51:23 GMT+0000 (Coordinated Universal Time)"
---
Depending on the type of partnership you have with Linear, your clients may have the ability to secure Line of Credit financing with us.  The Line of Credit Product allows the customer to make draws for funds as needed.  In some relationships, we allow our authorized partners to initiate draw requests on behalf of customers through their own platform. In order to facilitate all of this, we have created a series of endpoints specific to the Line of Credit product.

# Submitting a Draw

| Endpoint                                  |
| :---------------------------------------- |
| **[Submit Draw](ref:ideaapi_submitdraw)** |

Depending on the nature of your relationship with us, Linear can allow customers to initiate draws directly from your platform. Using the Submit Draw endpoint, a draw can be securely triggered to Linear. Combining this resource with the ones identified in **[Getting Updates on Your Accounts](doc:getting-updates-on-your-submissions-booked-accounts)** can provide a full suite of services to allow your customers to see available balances and manage their Line of Credit product all within your platform.

# Getting Draw Economics Prior to Submission with "GetDrawEconomics"

| Endpoint                                            |
| :-------------------------------------------------- |
| **[Draw Economics](ref:ideaapi_getdraweconomics) ** |

Because our Line of Credit product is an “evergreen” product, the economics of the product could change from time-to-time (although it is rare).  You can use our Draw Economics endpoint to ensure that customers are made aware of the economics of their Line of Credit before a draw is initiated.

To do this, you could calculate the fee breakdown yourself - all the information needed is available using the endpoints identified in **[Getting Updates on Your Accounts](doc:getting-updates-on-your-submissions-booked-accounts)** - however, due to varying fee structures, etc. we recognize managing this internally can quickly become a nuisance.  To help alleviate this, we've created our **Draw Economics** endpoint.  Simply call it with the dollar amount the customer is looking to draw and we'll return a detailed breakdown of that draw request's economics.  This resource is ideal for embedding into a workflow immediately prior to having a customer submit their actual draw request.

# Getting a List of Draws

| Endpoint                                  |
| :---------------------------------------- |
| **[Draw List](ref:ideaapi_getdrawlist) ** |

The **Draw List** endpoint provides functionality similar to that of the **Account List** endpoint, however, instead of returning all accounts associated with a given partnership, it will return all draws submitted by clients that are associated with a given partnership.  The responses received from this call contain key, high-level, details on each draw, allowing you to stay informed about things like status.  You can further refine down the number of responses returned by passing in additional parameters like date, customer, status, etc.

# Getting Detailed Information on a Specific Draw

| Endpoint                                 |
| :--------------------------------------- |
| **[Draw Info](ref:ideaapi_getdrawinfo)** |

Just like using the **Account Info** endpoint provides you with the ability to take a deeper dive into an individual account, using the **Draw Info** endpoint allows for a more in-depth view of an individual Draw.
