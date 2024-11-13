---
title: "Sandbox Integration and Testing"
slug: "sandbox-integration-and-testing"
excerpt: ""
hidden: false
metadata: 
  image: []
  robots: "index"
createdAt: "Sat Oct 05 2019 17:22:55 GMT+0000 (Coordinated Universal Time)"
updatedAt: "Fri Apr 30 2021 14:52:35 GMT+0000 (Coordinated Universal Time)"
---
Linear provides a sandbox environment to enable partners who are in the process of integrating the ability to test various endpoints. The sandbox environment supports all APIs in our production environment. To accommodate this, and facilitate speedy testing during the integration phase, we have created resources specifically for our Sandbox environment enabling partners to move their applications to booked statuses. This allows partners to test our line of credit APIs in addition to the behavior of the various account endpoints for booked Accounts. There are two resources you can call to book Accounts in the sandbox environment, depending on the type of product.

# Booking a Line of Credit

| Endpoint                                       |
| :--------------------------------------------- |
| **[Book Line Of Credit](ref:ideaapi_bookloc)** |

This will book an application as a Line of Credit.  Once booked, you can utilize the various Line of Credit functionality allowed through our API.  The API contains an optional history parameter.  

   _NOTE: Calling this resource will ignore the product type requested in the initial application submission.  Regardless of what was entered in the request, the account will be booked as a Line of Credit._

# Booking a Term Loan

| Endpoint                                   |
| :----------------------------------------- |
| **[Book Term Loan](ref:ideaapi_bookterm)** |

This will book an application as a Term Loan. Once booked, you can utilize the various account and status functionality allowed through our API. This API contains an optional history parameter.

   _NOTE: Calling this resource will ignore the product type requested in the initial application submission.  Regardless of what was entered in the request, the account will be booked as a Term Loan._
