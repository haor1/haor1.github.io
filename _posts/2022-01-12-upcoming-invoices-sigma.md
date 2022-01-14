---
layout: post
title: Upcoming Invoices in Stripe Sigma
subtitle: Upcoming Invoices are not stored in Stripe Sigma
gh-badge: [star, fork, follow]
tags: [SQL]
comments: true
---

I recently had a User inquire about how to retrieve Upcoming Invoices in Stripe Sigma.
The User was essentially asking how to perform the API command below but in Stripe Sigma.

[https://stripe.com/docs/api/invoices/upcoming](https://stripe.com/docs/api/invoices/upcoming)

The User was interested in using SQL Sigma as an alternative to the API command because the User 
had a high volume account and using the API command above to retrieve upcoming invoices would mean 
performing 1000's of additional API requests per day.

If you open the Sigma Schema docs in your Stripe Dashboard you can find an 'Invoices' table 
that includes a column "billing_reason" with type Varchar. The documentation states the following

{: .box-note}
**Note:** The 'upcoming' value is reserved for simulated invoices per the upcoming invoice endpoint. 

However, this is inaccurate and needs to be updated. The upcoming invoices cannot be retrieved in 
Stripe Sigma. Upcoming invoices can only be retrieved via the API command above. Hopefully the 
documentation can be updated soon to reflect this information. I informed the User not to worry about 
making 1000's of API calls a day as Stripe Users can make up to 25 requests/second in test mode and up to 
100 requests/second in live mode.

