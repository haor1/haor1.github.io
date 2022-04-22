---
layout: post
title: Tutorial to add a missing event to the Stripe-CLI
subtitle: Submitting an Open Source Contribution to the Stripe CLI
gh-badge: [star, fork, follow]
tags: [Open Source Software contribution]
comments: true
---

In this tutorial I will guide you through how to add one of the missing events to the Stripe CLI so that they may be triggered on-demand. I will be skipping the process of how to fork the Stripe CLI repository and how to push your local changes to the repository and submit the pull request. You can find how to do this elsewhere. I am strictly guiding you on what file needs to be created, what code needs to go in this new file, and what existing files need to be changed and how. Let's begin!   

Step 1: Go to the "Stripe-completion.bash" file in the main directory of the Stripe CLI repository [https://github.com/stripe/stripe-cli](https://github.com/stripe/stripe-cli). This file needs to be updated to include the following line:

~~~
must_have_one_noun+=("event_you_would_like_to_add_here")
~~~

Step 2: In the following file: "pkg/fixtures/triggers.go" you need to add a single line inside of the “var Events” as follows:

~~~
"event_you_would_like_to_add_here":     "triggers/event_you_would_like_to_add_here.json",
~~~

Step 3: You need to create a new file in the following folder "pkg/fixtures/triggers/". The file should have the following naming convention: "Event_you_would_like_to_add_here.json"

This is the most difficult part of the process. Inside of this file you will need to add data to the JSON response that is returned by this event. Here is where you will have to review the Stripe API to see what Object is returned in a successful API command for the event that you are looking to add to the Stripe CLI. You will need to include data in this file which will be returned to a User when they run the following command:

~~~
$stripe trigger event_you_would_like_to_add_here
~~~

Here is what the file includes for the event I added to the Stripe CLI ‘reporting.report_run.succeeded’, and here is the link to the Stripe API for this event so you can get a better understanding of what you need to include in this file.

[https://stripe.com/docs/api/reporting/report_run/create](https://stripe.com/docs/api/reporting/report_run/create)

~~~
{
  "_meta": {
    "template_version": 0
  },
  "fixtures": [
    {
      "name": "reporting",
      "path": "/v1/reporting/report_runs",
      "method": "post",
      "params": {
        "report_type":"balance.summary.1",
        "parameters": {
          "interval_start": 1641045832,
          "interval_end": 1646143432
        }
      }
    }
  ]
}
~~~


I plan to add several more of the missing events to the Stripe CLI, however, I won't be able to add all of them, which is why we need other people to contribute to this project. If you are following this tutorial and you experience any difficulty, feel free to reach out to me via email at hotero001@icloud.com and I would be happy to answer any questions.


