---
title: "REST API Platform Overview"
slug: "rest-api-platform-overview-alt-1"
excerpt: "Let's get started with some basics to help familiarize you with Linear's API suite."
hidden: false
metadata: 
  image: []
  robots: "index"
createdAt: "Sat Jul 27 2019 19:22:42 GMT+0000 (Coordinated Universal Time)"
updatedAt: "Mon Nov 01 2021 19:55:34 GMT+0000 (Coordinated Universal Time)"
---
> 🚧 Access & Utilization of Linear's API Endpoints
> 
> Due to the sensitive nature of information exchanged, Linear reserves the right to restrict access to certain API endpoints.

Linear's **Embedded Credit Platform** allows authorized partners to offer Linear's suite of business credit products and services to their customers. From application submission, to booking, to post-booking activities, our suite of API endpoints cover the entire account lifecycle.  The following sections provide a high-level summary of the various endpoints available and suggestions on how to go about using them.  For a more in-depth view, you can head on over to our complete **[API Rest Documentation](https://linear-documentation-hub.readme.io/reference)**.

# General Note Regarding Terms Used throughout this Guide

The following sections make reference to several terms that are key to understanding the vernacular around submitting an application for credit and the subsequent lifecycle of customer accounts.

- An **Application** is a record submitted to Linear that provides the required information we need to initiate our credit decision.  At times, we use "Application" and "Account" interchangeably.  Once an “Application” is submitted, it becomes an **Account** and the account identifier provided can be utilized across many of the other endpoints.
- A **Draw** is a disbursement of funds made by Linear on a Line of Credit.  Throughout the customer lifecycle, there will typically be many Draws on a given Line of Credit Account.
