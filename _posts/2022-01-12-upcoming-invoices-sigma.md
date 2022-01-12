---
layout: post
title: Upcoming Invoices in Stripe Sigma
subtitle: Upcoming Invoices are not stored in Stripe Sigma
gh-repo: daattali/beautiful-jekyll
gh-badge: [star, fork, follow]
tags: [SQL]
comments: true
---

I recently had a User inquire about how to retrieve Upcoming Invoices in Stripe Sigma.
The User was essentially asking how to perform the API command below but in Stripe Sigma.

[https://stripe.com/docs/api/invoices/upcoming](https://stripe.com/docs/api/invoices/upcoming)

If you open the Sigma Schema docs in your Stripe Dashboard you can find an 'Invoices' table 
that includes a column "billing_reason" with type Varchar. The documentation states the following

{: .box-note}
**Note:** The 'upcoming' value is reserved for simulated invoices per the upcoming invoice endpoint. 

However, this is inaccurate and needs to be updated. The upcoming invoices cannot be retrieved in 
Stripe Sigma. Hopefully the documentation can be updated soon to reflect this information.

