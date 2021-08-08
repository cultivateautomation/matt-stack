---
author: Matt Lincoln
title: What we learned from a crowdsourced Pardot Health Check Audit of over 100 accounts
date: 2021-05-30
description: Looking at the value of proactively auditing your Pardot account...
image: pardot-audit.jpg
categories:
- pardot
- audit
- data
---


## Introduction

If you manage one or multiple Pardot business units, you’re probably well aware of the importance of keeping your accounts in good shape. Since account maintenance isn’t always the most glamorous part of your role, you may end up putting it off for a rainy day. However, this can often have consequences, such as a poorly-optimised campaign, or a lack of insight into key metrics.

One of the most important steps to maintaining a successful marketing technology platform is making sure that your process is set up optimally for the way your organisation works. It takes time to set up your Pardot account, which is why it’s important to know how to do it, and what 'gotchas' to look out for.

At Pardreamin' 2020, I wanted to give some best practice tips on doing a Pardot health assessment. However it was a great opportunity to make a hands-on session, and allow participants to not only see their own org's health in isolation, but also to compare their org against their peers in the first crowdsourced Pardot health check. I'm often asked "what's the average of this or that metric?" by clients, but this was a chance to get some concrete data for comparison.

Want to participate yourself?

[Follow the walkthrough guide on The DRIP.](https://www.salesforceben.com/the-drip/how-to-measure-your-pardot-prospect-data-quality-fast/)

Watch the session recording:

{{< youtube "OAzaP7gJmgk" >}}

The session took the following structure:

*   [Training on Dynamic Lists for reporting](https://docs.google.com/presentation/d/1YqtPWdGt2RnHvYLsb6bmYKP3yJJuy5ZeR_bzzzLDDeA/edit#slide=id.p7)
*   [Users enter their data into a Google Form anonymously](https://docs.google.com/forms/d/e/1FAIpQLSeiWyP4JsdvABKZ8YSh6TsB9EI_cTOm9IgSPO5IS5i1731gCw/viewform)
*   [Metrics review](https://docs.google.com/spreadsheets/d/1FEPhJOwmqBc1lS_cO_HCcvtvGLrKXEluh5D-XMGswl4/edit#gid=564400163)

## Average % of Mailable Prospects = 78.4%

### **How did we measure this?**

This metric was calculated by dividing the total number of Prospects who can receive emails, e.g. not marked as Opted Out, Bounced or Do Not Email, by the total number of Prospects, then calculating the average across each org.

### **What can we learn from this?**

The metric tells us that on average, around 1 in 4 Pardot Prospects are not eligible to receive emails.

It's a fairly high number, and tells us that perhaps Pardot Admins aren't spring cleaning their account regularly. It's worth asking yourself if your marketing team has a good reason to be holding data in Pardot which you can't send emails to.

The interesting thing is that the actual number of mailable Prospects will be even lower than this in the real world. The limitation in this measurement is that for clients using [Email Preference Pages](https://help.salesforce.com/articleView?id=sf.pardot_emails_preference_center_parent.htm&type=5), prospects can opt out of specific communications without being counted as a globally opted out Prospect in your account. Only accounts exclusively using the "[global unsubscribe](https://help.salesforce.com/articleView?id=sf.pardot_emails_unsubscribe_page.htm&type=5)" option get an accurate number of "opted out" Prospects.

### **What can I do if I score poorly (low percentage)?**

It’s not necessarily a negative - unmailable Prospects don’t count towards your database limit. Consider whether the prospects are Opted Out or set as Do Not Email, or both. They're all different scenarios and require different approaches:

**Opted Out and Do Not Email:**
*   Clicks the unsubscribe link in a Pardot email or email preference page.
*   Reports an email as spam.

**Do Not Email:**
*   Has a hard bounce or five soft bounces.

**Opted Out:**
*   Is imported as opted out.
*   Is opted out in Salesforce.
*   Is manually opted out in Pardot.

### **Next Steps**

*   Reading the [Pardot Database Cleaning Guide](https://www.pardot.com/training/database-cleaning-guide/)
*   Consider archiving Prospects if they don't want to receive comms from you, or you've already imported as "Import prospects and global opt-out"
*   Enabling [Prospect Resubscribe](https://help.salesforce.com/articleView?id=sf.pardot_prospect_resubscribe_parent.htm&type=5)
*   Cleansing any “bounced” emails - expose these Leads or Contacts to reps in Salesforce List Views by using the [Pardot Hard Bounced field or enabling Salesforce Bounce Management](https://help.salesforce.com/articleView?id=pardot_default_prospect_field_mapping.htm&type=0).

## Mailable Prospects who have been emailed? - 76.1%

### **How did we measure this?**

This metric was calculated by taking the number of mailable prospects and dividing it by the number of prospects who have ever been sent an email to in your Pardot org.

### **What can we learn from this?**

The aim of this metric is to understand wasted database capacity.

If around 25% of mailable Pardot Prospects are never sent emails, it means that Pardot customers are generally overpaying for their license subscription.

If we do some really rough maths, our experiment gives an average of 79,169 mailable Prospects across the participating accounts, and the average account has emailed 50,114 mailable Prospects. This equates to a 29055 average "overage" in unneeded Prospect capacity.

The latest US pricing PDF shows that at the minimum pricing level, 10,000 additional Prospects are priced at $1,200 per year. This means that the average client is paying for 2.9 "blocks" which it doesn't need (29055/10000).

Salesforce tells us that the Plus tier is the most popular, so if we extrapolate out $1,800 x 2.9 = this means an average of $5,220 per year in unnecessary spend for each account participating in the benchmark.

### **What can I do if I score poorly (low percentage)?**

The first thing to check is whether you score low because you use an Email Preference Page. There is a limitation that clients using an Email Preference Page may have Prospects who are mailable from a technical perspective, but unmailable from a permissions perspective.

If not, it's time to start thinking about why you hold prospect data which you don't send emails to.

Consider why are these Prospects in your database and should they still be there? The Dynamic List created as part of the experiment brought back a list of Prospects who HAD been emailed, but let's create a new Dynamic List to fetch the records which HAVEN'T, by filtering for Prospects who are not on the list of mailable Prospects who have received an email.

Take a look at the Prospects which enter this Dynamic List. Work out how they entered your database by looking at the Campaign, Conversion Point, or the audit tab.

Are your prospects missing key segmentation fields? Alongside checking individual Prospect records for missing data, take a look at the last 10 or 20 emails sent from your Pardot account across List Emails and Engagement Studio start lists. Whilst using Dynamic Lists in Pardot for segmentation purposes is generally best practice, you might not realise that large parts of your database just don't get picked up due to the filter criteria you use.

## Prospects never active, or not active in the last 6 months? - 70.3%

### **How did we measure this?**

A prospect is known as active when they interact with our Pardot assets, such as clicking a link, viewing a page or submitting a form. However, email opens are not counted as many spam filtering applications open emails to check the content. It's easy to measure this using the Prospect time filter on Dynamic Lists. In the audit,

### **What can we learn from this?**

This metric is a great indicator of understanding how engaged your database has been recently with your Pardot marketing activities. We can see that 70.3% of prospects have never been active on average, meaning that the vast majority of a Pardot org's Prospects aren't interested in the emails you're sending them.

To the marketer clicking the send button, every email they're churning out feels important, but sadly that's rarely the case for the recipient. This metric highlights the importance of considering every member of your database as an individual, and targeting them as specifically as possible based on the segmentation information you hold about them in your database.

### **What can I do if I score poorly (high percentage)?**

The measurement of a Prospect as being 'active' revolves around the concept of '[conversion](https://help.salesforce.com/articleView?id=pardot_converting_visitors_to_prospects.htm&type=0)' in your Pardot org. Conversion is the link between a cookied 'visitor' on your website and Prospect in your database. To measure a Prospect being active, they must have converted. It's worth thinking about how you elicit prospects to complete your webforms and click on CTA buttons in your email templates - issues with these normally goes hand in hand with low conversion rates.

The other common reason for a poor performance for this metric is if you're not actually sending emails to your database, it's only natural that you're consequently going to have a lower level of activity. It's worth combining this Dynamic List with the previous one, to get a feel for which Prospects aren't engaging with your marketing assets because you've not been emailing them, versus who isn't engaging because they just aren't interested.

Check email click through rates overall. Do you use A/B testing to see what makes your audience 'tick'? SPF authentication? Email CTAs?

What’s the source of the Prospects? Are they not interested in your marketing efforts because you're targeting the wrong audience? Or, if you're definitely targeting the right audience, can you segment them more finely based on what you know about them to improve engagement?

If all else fails, should these Prospects or a subset of them be “spring cleaned” and put into the recycle bin, in order to tidy up your account and keep within your mailable Prospect limit? Before you do this, is a re-engagement campaign appropriate?

## First Name Missing? - 5.0%

### **How did we measure this?**

This Dynamic List used the "Prospect field "is empty" criteria. We divided the number of Prospects with a missing first name, by the total number of Prospects in each account.

### **What can we learn from this?**

The point here wasn't really about understanding the level of which the first name field is populated. That's one small data point amongst many fields used for personalising emails.

Even so, the number is surprisingly high. That's 1 in 20 records on average which is missing a first name. This is typically seen alongside what I call a "Mailchimp mentality" of just uploading email addresses for a particular unpersonalised "email blast". One of the biggest mentality shifts for a new client is that you should consider Pardot not as a tool to send individual emails, but instead think of it as a platform to build a long term Prospect Database.

### **What can I do if I score poorly (high percentage)?**

The most successful Pardot users have a defined set of data points required before a Lead can be passed across from Marketing to Sales. If you haven't already, define your MQL (Marketing Qualified Lead) criteria. This ensures that Sales receive Leads which are well qualified, consistent in quality and are more likely to convert. Could a Sales rep work a Lead which doesn't have a name? Every sales process is different, but it's likely for most organisations that the answer is no. Audit all the data collection points where Prospects enter your Pardot database. Whether it's through Pardot forms, imports, Connectors, or the API, ensure that you're not missing the chance to collect data in fields which are required for your Sales process - or put in a plan to collect them using Pardot functionality such as Progressive Profiling.

Ask yourself, for Prospects missing key data points, are those records really good quality data? Typically it can be the sign of a bad quality dataset being imported into your account. Do you really have permission to hold this data in your org? Consider sending these records to the recycle bin until they submit a form and provide complete information. If you don't even hold a first name for a Prospect, how can you be sure you know enough information about them to know which types of emails you should be sending them?

Also consider exposing these records to your Sales team using List Views in Sales Cloud. Perhaps they can populate the missing information (were the records synced from Salesforce in the first place and reps didn't complete the first name or any other field because it wasn't mandatory? Perhaps alternatively, a data provider could enrich your database with missing infromation?

Have a backup plan for blank values used as merge fields:

*   Ensure a [default merge value](https://help.salesforce.com/articleView?id=sf.pardot_add_default_mail_merge_values.htm&type=5) is set in case of a blank field value
*   Use [HML conditional statements](https://help.salesforce.com/articleView?id=pardot_hml_conditional.htm&type=0) to have more fine-tune control, for example:

```
    {{#if Recipient.FirstName}}
    Hi {{Recipient.FirstName}},
    {{else}}
    Hello!
    {{/if}}
```

Apply this approach to check other fields, e.g....

*   Last Name
*   Job Title
*   City
*   Country
*   Segmentation
*   Industry
*   Company Size (Employees/Turnover)

## What could have been better?

It wasn't a perfect experiment. There were some nonsensical submissions which I've removed from the data set, for example, submissions where the number of Prospects which had never received an email were higher than the total number of Prospects in the database! If I were to do this Pardot health check again, I would:

*   Encourage participants to take numbers from the email showing that a Dynamic List has completed refreshing, as I suspect some participants didn't give their Dynamic Lists enough time to refresh
*   Should have showed participants how to clear any existing filters in the Prospect table before checking the total number of prospects
*   Based on the comments and questions I've received, I'd encourage participants to not take the Dynamic Lists I shared too literally - e.g. checking blanks in the first name field is just an introductory concept - apply it to your other fields!
*   If I were to run the session again, I'd try to squeeze in the following health check points:
    *   **Prospects not synced to Salesforce** - there's less of a "correct" answer here, but it's an important metric to evaluate the qualification process used across Pardot and Salesforce.
    *   **Prospects who have been overemailed -** this can be done easily using the "Prospect has been emailed at least X times in the last X days" criteria and is particularly important in accounts with high numbers of different users with permissions to send emails.

In summary, it's best practice to regularly run a Pardot health-check auditon your account to make sure you're getting the most from the system, and that yourmarketingchannels are giving you the best possible return on your investment.

## Methodology Note

There were two options for methodolgy here when calculating the averages used below:

a) Calculating statistics on a prospect level across Pardot accounts, e.g. creating a total sum of Prospects across all orgs, then using this as a denominator for each calculation, e.g. with total sum of mailable Prospects as a numerator.

b) Calculating an average of each Pardot account's metrics, e.g. finding the percentage of mailable Prospects for each Pardot account individually, then calculating an average of each metric across all accounts

Option B was selected as a better fit as it was less impacted by org-level outliers, e.g. the potential for a huge Pardot org with 2 million prospects to wildly skew the average number of prospects and consequently the averages for each of the metrics covered in this article.

## Further Reading

If you need a helping hand to perform this type of analysis, Salesforce offers a guided [Pardot Health Assessment Accelerator](https://help.salesforce.com/articleView?id=000312990&type=1&mode=1) for clients on a Premier Success Plan.