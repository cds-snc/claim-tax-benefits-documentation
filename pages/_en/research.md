---
layout: page
title: Research
lang: en
trans_url: Recherche
---

## Introduction

The Claim tax benefits project was designed and developed with the needs of tax filers at the heart of every decision. Using generative design research methods, we developed an understanding of what tax filers need in order to file a tax return and access benefits. We then used evaluative methods such as usability testing to validate or challenge hypothesized solutions. The process of designing, testing, and iterating provided us with further insight into what works and what doesn’t when meeting the needs of tax filers in the context of a remote service.

Over the course of the partnership, we surveyed 152 people, conducted interviews and usability tests with 82 people, and conducted 13 studies. This is an abridged version of the full research report for this project. The full report includes all of the research insights and full methodology overview.

## Current state insights

Generative research is a category of design research methods that aim to produce deep understanding of an experience or behaviour in order to identify a problem to solve and to generate potential solutions. During the discovery and early alpha phases of this project, we used generative research to understand tax filing as it stands today.

This project started in partnership with the Community Volunteer Income Tax Program (CVITP) within CRA. Two of our generative research studies focused on the experiences of tax clinic clients and another focused on the experiences of tax filers with limited mobility more broadly.

### Tax filing goals: what motivates someone with low income to file a tax return?

<ol class="strong">

<li>
<span>To meet their responsibilities as Canadian residents or citizens and avoid punishment by CRA.</span><br />
<p>For many, receiving benefit payments is not the primary motivation for filing a tax return. Participants felt a strong obligation to file a return as Canadian citizens or residents. Most assumed that failing to do so would result in some kind of negative sanction from the government.</p>
</li>

<li>
<span>To get and maximize benefits</span><br />
<p>At the tax clinic we interviewed tax filers who had planned tight monthly budgets according to the benefits they expected to receive, and knew exactly what they were going to spend their return on: children’s clothes, groceries, or paying off debt. They turned to the tax clinic for help because they trusted volunteers to get them all of the benefits they were eligible for.</p>
</li>

<li>
<span>To access other programs that require proof of income</span><br />
<p>Various social assistance programs external to CRA are income tested and require proof of having filed a tax return. Some clients visit tax clinics with the explicit purpose of obtaining proof of filing so that they can access other supports.</p>
</li>

</ol>

### Barriers

**Tax filers seek in-person assistance because they lack confidence in their own ability to file a return without making a mistake or accidental omission.**

- Determining which steps to take, which information to divulge, and how to interpret eligibility criteria for individual claims and benefits is not intuitive: it requires background knowledge or research
- Tax filers with simple tax situations may have complex life situations that are difficult to communicate to CRA. The answers to seemingly simple questions, like “what was your address last year?” can be ambiguous for someone who is experiencing or recovering from a turbulent period in their life.

**This lack of confidence becomes a barrier because it is connected to a fear of negative outcomes.**

- Tax filers believe that mistakes in their tax return will result in negative outcomes such as financial penalties, legal action, or heightened future scrutiny from CRA. The participants we interviewed came to the tax clinic because they believed that they would make mistakes if they filed by themselves.

### In-person assistance is not always possible to reach

Our generative research indicated that lack of confidence acts as a barrier to filing and accessing benefits, and that free, in-person assistance offered at tax clinics helps tax filers overcome that barrier.

Physically getting to in-person assistance can be an insurmountable barrier to tax filing for some, while adding a layer of complexity to the process for others. Travelling outside the home can be particularly difficult and time consuming to coordinate for tax filers with mobility-related disabilities, especially when the task is time sensitive. For others, lack of transportation or time can make it difficult to get to free, in-person services.

> “We come to the clinic so that they can help you do everything – all the math... if the computer can do \[it automatically] then maybe there’s a chance we could do it at home and just stay at home.”

A tax filer might have difficulty accessing in-person services because:

- There is no clinic nearby, particularly in rural and remote areas
- There is no transportation to get to the clinic
- The tax clinic environment can be challenging for people with mental illnesses
- In-person services can be difficult to get to for people with disabilities

Of the 13.4 million individuals across Canada with income under \$35,000 around 741,460 file returns through the Community Volunteer Income Tax Program each year. While brick and mortar tax clinics are effective for those who can reach them, program data indicates that expansion of the program is seeing diminishing returns of impact for investment.

## Future state insights

We know which features of tax clinics and other services work well for tax filers with low income and limited mobility: asking a limited number of simple, personalized questions, and providing guidance on how to complete the process.

To address mobility barriers we designed a service that does not include in-person touchpoints. It allows tax filers to complete and submit their return entirely online or by mail.

### What do tax filers need in order to file taxes without assistance?

While self-serve, remote tax filing services can help address mobility barriers, the absence of in-person assistance may present other channel-specific barriers. During alpha and beta phases of the project we used evaluative research methods such as validation and usability testing to uncover barriers unique to a remote service. Evaluative studies were conducted primarily with participants recruited at food banks, who had varying degrees of familiarity with different tax filing methods. This section outlines the specific needs we identified over the course of our research with tax filers, and the design decisions that resulted.

#### Tax filers need to feel confident that they will not get in trouble with the CRA if they do their taxes alone.

Tax filers make decisions based on what they think will help them avoid negative outcomes after their return is filed.![](https://lh4.googleusercontent.com/FPR1Uj0UpJfw2PREdZqxoBJ02BM-XxwmwBz83lYSwhvyVqYApwzcAfmxLB8TBKxTGa8rDw-Gh0KoxNINgQFYqxBnwAlQXHf_IpwOzEL7Atl1caUri6n5fi8V-vn5P7kbzEtWiLRE)

##### Present only the questions that are necessary and relevant to the tax filer

When completing a paper tax return, tax filers are presented with a long list of blank fields. Tax filers can feel overwhelmed by the apparent number of decisions about which boxes to fill out and whether they qualify for each benefit or credit.

The MVP Claim tax benefits service emulates the personalized guidance available at tax clinics by showing only questions that apply to tax filers with income under roughly $12,000 per year ($19,000 for individuals under 65) and simple tax situations. The online channel further eliminates questions that don’t apply based on answers to preceding questions.

##### Eliminate steps and required documents wherever possible

Tax slips are typically required when completing a tax return. Without the guidance of volunteers, tax clinic clients worry that they are unknowingly missing a required tax slip or other document and may not know how to replace a document if it is missing.

Claim Tax Benefits does not require tax filers to input specific information from their tax slips, as that information is already known by CRA. Instead, they confirm that their income is below the MVP threshold, and that they do not have additional income to declare.

##### Ask simple, unambiguous questions

Our research found that tax filers lose confidence or may unknowingly give the wrong answer, when the “right answer” is ambiguous. During usability testing, participants had trouble answering “yes or no” when there was qualifying information embedded in the question. In an earlier iteration of the service, a question asked tax filers if they had home energy costs, but only if they also lived on a reserve.

![Example of question on website: Question: In 2018, did you live on a reserve and pay home energy costs. Yes no radio buttons. Continue or cancel buttons.](/assets/img/screen-shot-2020-03-18-at-19.17.33.png "Original question design")

We decided to break down complex questions like this into multiple questions with clear “yes or no” answers, presented in sequential order. If the question contained a term that might not be familiar, a definition was provided in an accordion menu below.

![](https://lh6.googleusercontent.com/oz3FPSygo3lZzD2JPssnfwpFh69IDObvbxJGgyXj7s63UnVGCy5hTFa_V15Z0mPKz31FDu5kRbUcn3AvZu08Im3i1oha1O3K69_xB4EvOBlF33naByWMUD07b8rlWiXcInnVHO9k)

#### Tax filers need to use the channel that is most accessible to them.

Channels are the medium through which people convey and receive information in order to use a service.

**When paper is inaccessible**

Many people with mobility and vision-related disabilities use screen readers and other assistive technology to find and access information. Paper communications are not accessible by default. Our research with participants with limited mobility found that accessing the information written on a piece of paper can compromise tax filers’ agency and privacy. This is because it forces tax filers with disabilities to choose between spending valuable time converting paper to digital format, or asking someone else for help with a task that they could otherwise complete independently on the computer.

**When digital is inaccessible**

For tax filers who do not use digital assistive technology, being required to use a digital channel can be equally problematic due to lack of access to a computer, low computer literacy, or mistrust in digital communication channels.

##### Work towards an end-to-end service path through single channels

Tax filers need to be able to complete the entire service using the channel that works for them. In order to do this, in future iterations of the service Claim Tax Benefits would work towards providing electronic invitations to tax filers who prefer digital communications, as an alternative to mailed invitations.

#### Tax filers need to feel confident that the service isn’t a scam

Scams are top of mind for tax filers: many have either experienced contact attempts from someone pretending to be the CRA, or know someone else who has. We heard from research participants who had been legitimately contacted by CRA, but remained unsure as to whether or not the communication was trustworthy.

This research insight suggests that new services that are offered remotely, and in an environment where malicious actors are present, face a unique barrier to uptake: proving their legitimacy to tax filers. While building familiarity and trust in the service over time may be the primary solution to this problem, research with tax filers uncovered some additional approaches.

##### Cater to existing methods of distinguishing between scams and legitimate services

When determining whether or not a communication or service is indeed from CRA and not a criminal trying to defraud them, participants looked for:

**Familiar visual cues**

_Does a letter or online message look similar to others they’ve received in the past? Is it something that would be difficult to recreate?_

The CBT service maintains a similar look and feel to existing CRA communications and services – we were cautious about introducing radically new design patterns.

**Logical consistency**

_Does this seem like something CRA would ask or do, based on their understanding of how taxes work and CRA’s motivations and goals?_

We made sure to clearly communicate major departures from the filing process that tax filers are accustomed to, such as no longer requiring that they input their income information.

**Official confirmation**

_Can a tax expert or trusted CRA information source reassure them that the service is real?_

In validation and usability testing, participants indicated that they would call CRA to verify that the service was real. Plans for live release of the service included making sure that call agents have the information to answer questions about the new service.

## Next Steps – Further evaluative research

### Usability testing with participants who use assistive technology

Tax filers with limited mobility were identified as an underserved population that could benefit from a free, remote service. Usability testing with screen reader users may uncover barriers to access not covered by WCAG 2.1 requirements.

### Mediated concierge testing – usability testing with real outcomes

Our research indicates that **confidence** and **risk-based decision making** are the key factors in tax filing behaviour. These concepts in particular hinge on the presence of real or perceived risks and potential outcomes. This is why, for tax-related services in particular, it is critical to test with a high level of realism. Conducting usability tests where participants are filing real returns and making real decisions based on expectations about real outcomes could reveal previously hidden confidence barriers.

### Performance monitoring and analytics

On an agile product, design iterations do not stop once the product is live. Monitoring outcomes and use patterns provides valuable information about how the service is performing at scale. Usage analytics like bounce rates, time on page, and navigation flows are useful diagnostic tools for identifying where usability problems might lie. Knowing which pages are associated with unexpected behaviour can help researchers decide how to focus future usability testing sessions to find out why tax filers are interacting with the service in a given way.
