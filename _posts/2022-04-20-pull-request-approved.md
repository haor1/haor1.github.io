---
layout: post
title: Open Source Software Contribution
subtitle: My pull request was approved and merged in the Stripe CLI repository
gh-badge: [star, fork, follow]
tags: [Open Source Software contribution]
comments: true
---

Stripe has a list of all the types of events we currently send. There are well over 100 events. However, only a fraction of these events are supported in the Stripe CLI.
So if a User would like to trigger, for example, 'customer.source.expiring' in the Stripe CLI for testing purposes, this is not possible at the moment. Therefore, I went
ahead and submitted a pull request to the Stripe CLI repository on Github in order to have reporting.report_run.succeeded added to the list of events that are 
supported in the Stripe CLI. After a review by a member of the Stripe team, my pull request was approved and merged to the main repository. Thanks to my contribution, you can now  run the following trigger in the Stripe CLI:


~~~
$stripe trigger reporting.report_run.succeeded  
~~~


in the Stripe CLI and thus test the behavior of this event in your integration. There are still dozens of events 
that are not supported in the Stripe CLI. I will add more in the coming months. In my next post I will create a tutorial on how to submit a pull request and add one of the missing events to the Stripe CLI, so that if there is an event you would like to have added to the Stripe CLI, you can add it yourself by writing the code that is required to do so.
The code required to add one of the missing events to the Stripe CLI is not complicated so I think almost anyone with minor previous programming experience can do this.

[https://github.com/stripe/stripe-cli/pull/842](https://github.com/stripe/stripe-cli/pull/842)


