---
author: Matt Lincoln
title: How to report on specific form or landing page submissions in Pardot's Engagement Studio
date: 2024-05-02
description: Learn how to report on specific form or landing page submissions from Engagement Studio in Marketing Cloud Account Engagement.
image: report-form-landing-page-submissions-engagement-studio-pardot.png
categories:
- pardot
- marketing cloud account engagement
- reporting
- engagement studio
---

I recently had a question along the lines of, "How do I report on the number of form submissions that were generated via Engagement Studio for a Marketing Cloud Account Engagement form?"

<!--more-->

Breaking this down, there are a few considerations:

-   The Form is on the client's main website so people who are not part of the nurture, could also find the form
-   The Form is referenced in multiple Engagement Studio programs
-   There were no "Triggers" in the nurture

There are a lot of different ways this could be approached, and I gave three options:

1.  Add a tag to all prospects entering the program. Then go into reporting for the Form(s) you're interested in. Look at the Prospects section and filter the Prospects by your tag.
    1.  **Advantage:** You can do this retrospectively AND you'll see the reporting even if they go and submit any time into the future
    2.  **Disadvantages:** You don't see the reporting directly in the Engagement Studio and need to go elsewhere
2.  Add a Trigger step into your Engagement Studio program to check if Prospects have done what you're interested in. If they go down the "Yes" Path, they've done what you're interested in. If not, they won't.
    1.  **Advantage:** Can see it directly in the Engagement Studio program. Very visible.
    2.  **Disadvantages:** You'll need to think carefully about the timing. You can't evaluate this immediately, meaning you'll need to build your wait periods differently. It's also not retrospective in terms of reporting, i.e. if you add it in now, you won't see the reporting retrospectively (unless you add a check in as the very last step in the flow). Equally, these folks who submit the form could technically have found it directly on the website rather than due to a nurture email, and if they submit, they'll still go down the "Yes" path.
3.  Create a new form or landing page specifically for your Engagement Studio program. The metrics for that form or landing page will be specific to the participants of your program.
    1.  **Advantage:** Very clear reporting, simple for inexperienced users to set up and understand.
    2.  **Disadvantages:** Creates duplicates of forms or landing pages in your account, creating 'clutter' in your account.
4.  Create reports in B2B Marketing Analytics
    1.  **Advantage:** You have more flexibility here than native Pardot reporting. You can slice-and-dice the data in whatever way you need and visualise it more flexibly.
    2.  **Disadvantages:** This is the highest effort approach, and it's not easy out of the box to filter based on which Prospects have been part of a specific Engagement Studio program - you'll need to derive this indirectly, for example, by using tags, Salesforce Campaign Member Statuses, or by which Prospects have received an email from the nurture you're interested in.