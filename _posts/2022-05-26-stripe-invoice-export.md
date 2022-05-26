---
layout: post
title: Stripe Invoice Exporter
subtitle: Ruby script to download all your Stripe PDF invoices in bulk.
gh-badge: [star, fork, follow]
tags: [Open Source Software contribution]
comments: true
---

In the Stripe API a helper method is provided to download the PDF of a quote [1], but not for an invoice [2].

[1] [https://stripe.com/docs/api/quotes/pdf](https://stripe.com/docs/api/quotes/pdf)
[2] [https://stripe.com/docs/api/invoices](https://stripe.com/docs/api/invoices)

It is not feasible for a User to go into the Dashboard to download each and every invoice manually. This becomes especially
cumbersome if a User's account contains thousands of invoices or more. I have created a simple Ruby program which when executed
downloads all of your Stripe invoices and stores them in a /invoices directory on your computer. The program gives you the option of
dowloading all of your invoices or only invoices starting after or before a given invoice. I have made the Ruby program Open Source,
you can find it at the link below [3]. I have also created a Ruby gem for it so that it is more visible to the Ruby community
(also linked below).

[3] [https://github.com/haor1/stripe_invoice_pdf](https://github.com/haor1/stripe_invoice_pdf)
[4] [https://rubygems.org/gems/Stripe_Invoice_Gem](https://rubygems.org/gems/Stripe_Invoice_Gem)
