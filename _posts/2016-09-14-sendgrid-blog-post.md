---
layout: post
title:  "Versatility vs. Usability: Revamping SendGrid’s Inbound Parse Documentation"
date:   2016-09-14
excerpt: "My main project over the summer was writing and updating SendGrid's Inbound Parse documentation. In this post I explain some use cases for Inbound Parse and talk about my process."
project: true
tag:
- Content Development
comments: false
---
[See it live](https://sendgrid.com/blog/versatility-vs-usability-revamping-sendgrids-inbound-parse-documentation/){: .btn}

## Making Email A Two-Way Conversation
Everyone expects a company like SendGrid to send email—it’s literally in our name. But good communication goes both ways, and our Inbound Parse Webhook makes that possible. It can do fun things like [imitate Pokemon battles](https://sendgrid.com/blog/pokemon-sendgrid/) or [tally votes for the best nearby bar](https://sendgrid.com/blog/choosing-my-first-drink-with-sendgrid-foursquare-node-js-and-socket-io/), but it can also do super useful things like automatically respond to incoming email with the [optimal Taco Bell order for the amount of cash in your wallet](https://sendgrid.com/blog/optimize-fourthmeal-tacos-knapsacks-webhooks/) or [business card details](https://sendgrid.com/blog/oh-cardless-business-card-email-app/).

The Inbound Parse Webhook isn’t just part of an autoresponder. It can create and update support tickets from incoming email, let users reply to comments without leaving their inbox, and even store attached documents—and those are just some of the ways our users have configured it!

As cool and useful as the Inbound Parse Webhook could be, its documentation needed a little bit of touching up. Thanks to customer feedback, I had an opportunity to address specific trends from both support tickets and GitHub issues. I started by cleaning up all of the parse docs to be more clear and concise.

## Setting Up the Parse Webhook
You can set up the Inbound Parse Webhook in three steps:

1. Point a domain or subdomain to mx.sendgrid.net
2. 3Add that domain or subdomain and a URL to POST the parsed data
3. Write and install code to consume the data

But adding an MX record requires messing with DNS records, and most people either don’t feel comfortable making changes or don’t even have permission to access DNS records.

To help mitigate concerns, I wrote a step-by-step workflow: [Setting Up The Inbound Parse Webhook](https://sendgrid.com/docs/Classroom/Basics/Inbound_Parse_Webhook/setting_up_the_inbound_parse_webhook.html). While I couldn’t document every DNS provider, I was able to add callouts and warnings to help prevent common pitfalls, like not changing the MX records for the current domain responsible for email or only trying to POST to a public URL.

## Making Parse Useful
Setting up the Parse Webhook is really just the first step. To actually get value from the parsed data, developers have to write their own application. Based on customer feedback, we learned that developers wanted a little more information. We had a thorough table that listed every parameter that would be POSTed to the customers Webhook URL, and in my own testing, I felt their concerns. One of the biggest concerns is that the default Inbound Parse payload contains different parameters from the the Raw MIME payload, and the existing table didn’t differentiate which parameters were included with which payload.

I created two separate tables to indicate which parameters are included by default and in raw. I also added example payloads so developers can see the exact payload the Parse Webhook POSTs. These examples show developers how the data is structured and allows them to test their code by sending these payloads to themselves.

A compelling book throws its reader into the action instead of telling it through exposition, and the same rings true for documentation: provide enough context and examples so readers can get back to coding more effectively.

## Hopes for Inbound Parse
nbound Parse is a ridiculously versatile feature, and I hope that the new workflow, specified parameters, and example payloads will help our customers discover new and interesting ways to use this tool.

Last quarter Inbound Parse averaged 44 tickets a month. The ticket data post-docs launch is still coming in, but in the couple weeks since going live, the new workflow is in the top 5 Parse-related articles in our docs for page views!

Unfortunately, I won’t get to see the ongoing impact directly because I fly back to Ohio for one last year of school, but I now know that my degree doesn’t resign me to writing instructions for turning on printers or exporting PDFs. And that’s a pretty awesome feeling. I’m going to miss real-world projects with measurable impacts, but I suppose that’s my motivation to finish soon!


