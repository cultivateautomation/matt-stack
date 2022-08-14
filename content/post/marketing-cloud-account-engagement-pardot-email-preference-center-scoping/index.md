---
author: Matt Lincoln
title: 10 Questions to help you scope your Marketing Cloud Account Engagement (Pardot) Email Preference Center
date: 2022-06-12
description: Getting the business analysis considered early on in your Email Preference Center project will make the whole implementation run more smoothly
image: pardot-email-preference-center-scoping.jpg
categories:
- pardot
- email
- gdpr
---

How many times a day do you receive unwanted or irrelevant emails? Five times? Ten times? As a marketer, we want to ensure that we're only sending emails to our Prospects, which they want to receive, so that we avoid receiving spam complaints and harming our brand reputation. From a GDPR perspective, giving your Prospects better visibility and more control over the types of emails they're agreeing to receive from you, can only be a good thing, too!
<!--more-->
Implementing a Marketing Cloud Account Engagement (Pardot) Email Preference Center is an important step towards ensuring that you're sending emails which your Prospects actually want to receive from you. However, Email Preference Centers can be complex projects from a technical perspective, but also because they require process changes to how your users send emails, to ensure that marketers understand and obey the preferences captured.

In my client engagements, I've seen that the most challenging part of these projects is the business analysis and solution design of the preference center. To aid these discussions with your own internal team and implementation partner, I've outlined a set of questions for you to start thinking about internally whilst building your requirement documents:

## 1. What's the main driving need/requirement for you to want to implement the email preference center?
In the past, I've come across everything from "We've been threatened by a regulator that we'll receive a fine if we don't do this", to "We've already got a preference center with way too many options and it just doesn't work well", to "Our Sales team needs better visibility and control over preferences".
Beyond this, what's the overarching scope of your project? Does "email preferences" fully cover it, or do you also want to consider non-native Pardot channels such as Direct Mail/SMS/in-app Push notifications? Surprisingly this is often assumed by clients to be included in a project such as this, but isn't covered by standard in a Pardot Preference Center.
Your answer here will help your implementation partner drill down specifically into any specific functional/regulatory requirements and ensure your needs are met.
## 2.  What types of emails do you send in Pardot, or want to send in future?
One of the first things to consider if the actual preferences which will be displayed to Prospects. General best practice (but not an absolute rule, as there are always exceptions) is to keep this to around 4 or 5 preferences, which match the themes of communications you send, for example, "Event and Webinar Communications" might be one preference option, "Industry News" could be another, and "Product Updates" might be a third option. Note that these don't refer necessarily to specific individual types of emails, but instead, broad categorisations of the themes your Prospects may want to receive or not receive from you.
The general best practice is to avoid having preferences for "Product A", "Product B" or "Service C", because this type of intent tends to be very dynamic, instead we could use their behaviour, or data we hold about them in our CRM platform to determine which Products they should receive communications about, but align this to the thematic communication preferences as outlined above, e.g. Newsletters, Events/Webinars, Product Updates.
## 3.  Should certain preference options only be available to specific prospects?
To take the concept from point 2 a step further, if we consider what we know about our Prospects and their behaviour, might there be some preferences which are only relevant to certain subsets of your Prospects? What if you run a loyalty club, but only for customers of a certain product? Should I see the option for certain preferences only if I'm an existing client or a potential client, or a user of a specific product or service?
## 4.  Is localisation required?
Whilst this may seem similar to point 3, the distinction here is purely a question of language localisation. Does your preference center need to support multiple languages, and if so, do you hold a (reliably accurate) Language field against your Prospect records? If yes, your implementation partner can implement a Dynamic Content solution for multiple languages
## 5.  Are there any conceptual groupings to your preference options?
This is a question more appropriate if you identified a large list of preferences in point 2 - your implementation partner can add custom structure to your email preference page to cluster the preferences into groups with section headings, or implement structures such as accordions if displaying a single list of all your preference options would be overwhelming to your prospects. Although keeping the amount of preferences small is definitely best practice, I once worked with a large client which had a complex requirement for over 40 different preference options, so structure was an absolute necessity!
## 6.  How should existing records in your database be handled - do you already have clear, pre-existing opt-ins?
Consider how your signup forms are messaged today, and how you obtained your existing database - for all the preferences you create, you'll need to make a conscious decision about whether your existing Prospects should be opted in or out of those new preferences. This doesn't need to be a one-size-fits all approach; you may decide that only Prospects who submitted an inbound marketing form and ticked a pre-existing opt-in checkbox should receive your newsletter emails. On the other hand, you may decide that your active customer base should receive emails about new product features on a 'legitimate interest' basis as per GDPR. Outline the logic you'd like to follow, and document it for your implementation partner.
## 7.  Do you need to share consent with any other systems?
Is Pardot the only system where email preferences are mastered? Do you also use other promotional email tooling, such as Salesforce High Velocity Sales, or are you in a dual-MAP environment with another solution such as Salesforce Marketing Cloud Engagement, Eloqua or Marketo? Do you also need the preferences which are selectable by your prospects to be displayed in Salesforce or your data warehouse such as Snowflake?
Importantly, do you expect consent to be purely controlled by Prospects, or is there a requirement for Sales/Account Managers to update consents? What traceability do you need around who/when/how the preferences were updated?
## 8.  How will consents be applied to new data gathered?
Which preferences will you apply to newly onboarded clients, or Prospects who submit your web forms? Will you have an opt-in checkbox, and if this is checked, would they be opted in to all, or a subset of the preference lists? How do you want this to be explained to your Prospects?
## 9.  How do you currently build segmentation lists?
This may seem an innocuous question, but has added hidden complexity to many an email preference project. Some clients have a high dependency on segmentation data which does not or cannot be consumed by Pardot, such as complex segmentation based on real world digital product telemetry, or daily client performance metrics. In these scenarios, segmentation for list building purposes may have a high dependency on imports into Pardot. Where a non-standard sales cycle is followed, e.g. digital-only onboarding from a web property not integrated with Pardot/Salesforce, your Pardot Prospect list may not be a real-time reflection of your current client list and require frequent manual uploads. In this case, how should preferences be applied to newly imported records?
Even in the most simple of cases, your implementation partner will want to understand your current list building process, in order to provide training/process documentation for you to ensure that your teams will comply with your new preference management process when sending out emails - implementing a new back end process is fruitless if the preference data is not obeyed in your emails.
## 10. What do you want it to look like?
Although this question is simpler from a technical perspective, it can massively speed up your project if you have some ideas/inspiration about the visual appearance of your email preference page. Should it be based on one of your existing Pardot landing pages, a page on your website such as your Privacy policy page, or do you have any examples from competitors or other brands, which your implementation partner can leverage?
## Summary
Once you've considered the questions above, I would recommend putting a briefing document together to share with your consulting partner. This can make your requirements much clearer, ensure that you will have a more accurate estimate of time and cost from your partner, and also reduce the risk of any incorrect assumptions being made.