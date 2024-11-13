---
title: "Submitting an Application"
slug: "submitting-an-application"
excerpt: ""
hidden: false
metadata: 
  image: []
  robots: "index"
createdAt: "Sat Jul 27 2019 19:23:23 GMT+0000 (Coordinated Universal Time)"
updatedAt: "Fri Apr 30 2021 14:48:06 GMT+0000 (Coordinated Universal Time)"
---
The most common use of Linear's API suite is submitting an application for credit on behalf of a customer.  To help make this process quick and easy, we provide two separate endpoints providing you with flexibility over the customer experience you wish to build.

# Submitting a Complete Application

| Endpoint                             |
| :----------------------------------- |
| **[Submit App](/linear-v1/linear-api-v1-schema.html#tag/Applications/operation/IdeaApi_Submit)** |

The **Submit App** endpoint submits a full application (request for credit) on behalf of the customer.  For the function to work successfully, all _required_ fields must be present when the endpoint is called.  This call will initiate Linear's automated credit strategy and will return an instant decision.  Calling this endpoint is ideal in situations where you have all the required fields on-hand or are willing to capture the supplemental data points we need, over and above what you customarily have available on your customer.  If that isn't possible we suggest using our **Prefill App** endpoint.

# Initiating an Application with Partial Required Data

| Endpoint                               |
| :------------------------------------- |
| **[Prefill App](/linear-v1/linear-api-v1-schema.html#tag/Applications/operation/IdeaApi_Prefill)** |

If you don't have all the fields we require to use the Submit App endpoint, chances are the **Prefill App** endpoint should do the trick.  Unlike Submit App, this endpoint does not submit an application on behalf of a customer.  Instead, this call will return a secure link that you can use to redirect the customer to an application site (hosted by Linear) that will pre-fill the data points you have supplied us with, only asking the customer for the supplemental data points we need to submit the application.  The only required fields to initiate this call are _Legal Business Name_ and _Customer Email Address_.
