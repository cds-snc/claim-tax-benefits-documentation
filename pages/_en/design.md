---
layout: page
title: Design
lang: en
trans_url: Conception
---
Our service design was informed by best practices and research insights. Research showed that tax-filers need to:

* be able to file without travelling for help
* feel confident that they will not get in trouble if they do their taxes alone
* feel confident that the service is not a scam
* get proof of filing to access other programs and benefits
* use the channel that is most accessible to them

Based on these considerations, we developed an invitation only service with both an online and a paper channel. Invitees can use this simplified method to file their taxes and access benefits. To learn more, read [the service blueprint.](https://drive.google.com/a/cds-snc.ca/file/d/1SSZd7L7hbdRh37qrSVWZHzbzWFF4zS4w/view?usp=sharing)

**The service touchpoints are:**

* a[ letter ](/assets/pdf/invitation-letter-en.pdf)inviting people to use this service,
* a [paper form](/assets/pdf/paper-form-en.pdf) for people who will not file online
* an [online tool](https://claim-tax-benefits.azurewebsites.net/start) which allows people to file taxes through a website, and which can take the form of:

  * a ‘lite’ journey that requires no security questions and no corresponding disclosure of financial information. Tax-filers must wait two weeks to receive their notice of assessment by mail.
  * an ‘authenticated’ journey which requires answering security questions and disclosure of financial information. Tax-filers will receive an immediate notice of assessment online.

There is potential to develop an internal tool that CRA staff can use to process the paper form. This tool could then be adapted for processing of other simplified forms.

## Invitation Letter

CRA will send the invitation letter to select participants to on-board them onto the service. The letter gives context about the service and explains how to access both channels.

**Core research insights**

* The invitation letter must provide context for the service, predominantly display the options (paper or online channel) and explain what is required to complete the service.
* The letter must be in a form that can be mailed or sent electronically depending on preference. Electronic notification is particularly important for tax-filers who use screen readers.

**Organizational Constraints**

Printing

* The CRA printing services face several limitations, in particular the inability to include boxes or customized information (i.e. location of personal access code) in the body of the letter. 
* Due to timelines, we were unable to create a dynamic field to display the personal access code in the letter. The current process requires approximately 12-15 months in order to incorporate this field, or to create a similar field for display of the tax-filer’s name in the paper form.
* The tax-filer’s name must appear on the form to ensure that the individual does not provide their form to another person who is not eligible to use this service. The team has initiated discussions with the appropriate areas.

Electronic notifications 

* At this time, it is not possible to notify tax-filers of this service by email to their My Account. 
* We are unable to provide personalised information such as the access code in the letter for security reasons. This requires further examination in collaboration with the appropriate areas.

**Design Interventions**

* Clear context at the beginning of letter to invite tax filer to use service, and explain what the service provides
* Headings that explain the option between online and paper, and what the tax-filer needs in order to use the service

**Next Steps**

* Work with the CRA team responsible for printing to display the options in a table
* Determine how to notify tax-filers using MyAccount. It may also be possible to allow direct log-in through My Account without an access code.

## Paper Form

The paper channel is a simplified form submitted by mail as a tax return.

**Core research insights**

* Paper is a necessary channel for people who do not feel confident, comfortable, or have access to use a computer.
* The paper form needs to be simple and in plain language, following clearly explained steps.
* The form should not rely on any appendix or external information sheet. All required information should be contextualized on the page so that the tax-filer does not need to check other documents in order to complete the form.

**Organizational constraints**

* Limited information can be pre-filled due to printing constraints and security risks. Only the name and a reference code for CRA use can be pre-filled

**Design Interventions**

* Form headings appear in a sequence of easy to follow steps.
* Relevant information appears in each step of the form, to prevent the need for external instruction and reduce cognitive load

**Next Steps**

* Content testing to ensure that instructions are clearly understood, so the form is easy to complete.
* Stress test a completed form with the processing team to confirm the form can be used to file a tax return
* Investigate potential for building internal tool to streamline processing.

## Online Tool

The online channel is a web application via which invited tax-filers can submit their return.

**Core Research Insights**

* Avoid double barrelled questions which put onus on tax-filers as these can cause confusion and can lead to critical error when completing the service
* People are easily overwhelmed by tax questions, so we need to ask questions that they immediately believe they can answer
* A majority of users could not answer two enhanced security questions, meaning an alternative journey should be provided

**Organizational Constraints**

* Authentication through security questions is required to disclose financial information and provide an Express Notice of Assessment as soon as the return is submitted online
* The service is unable to automatically pre-screen potential tax-filers since it cannot predict changes in personal circumstances that may make someone ineligible

**Design interventions**

* Use one question per page
* Use a consistent pattern of yes or no questions
* Ask questions about the tax-filer rather than questions about their taxes
* Only use a checkbox on the screen where the tax filer must confirm their income; every other screen should use binary radio buttons
* Provide a ‘lite’ journey (no disclosure with a two week wait to receive a Notice of Assessment by mail) so that people can still use the service if they are unable or unwilling to answer security questions.

**Next Steps**

* Implement content [suggestions](https://crazee-docs.netlify.com/assets/pdf/cra-content-suggestions.pdf) 
* Additional user testing
* Design a simplified authentication flow using questions that most tax-filers are able to answer so that the CRA can disclose their financial information

## Product states

### Minimal Viable Product

The Minimal Viable Product (MVP) is the first iteration of the service. We had intended the MVP to be available to selected tax-filers through a pilot or private beta release, with limited features and eligibility criteria.

<table>
  <tbody>
    <tr>
      <th>Eligibility Criteria</th>
      <th>Features</th>
    </tr>
    <tr>
      <td>
        <ul>
          <li>People who earn 12k if under age 65, or 19k if age 65 or above</li>
          <li>Resident of Ontario</li>
          <li>No spouses or dependent children</li>
          <li>No students</li>
        </ul>
      </td>
      <td>
        <ul>
          <li>File tax return</li>
          <li>Register for Ontario trillium benefits</li>
          <li>Register for Climate action incentive</li>
          <li>Change address (<strong>paper only</strong>)</li>
          <li>Notice of assessment by mail in up to 2 weeks (online) and 8 weeks (paper)</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

The mature state will provide both a ‘lite’ and ‘authenticated’ journey within the online channel. Individual tax-filers can opt to answer security questions in order to access more features.

### Mature State

The mature state is a later iteration with broader eligibility criteria and a wider range of features. These features and criteria will be scaled up incrementally and iteratively.

<table>
  <tbody>
    <tr>
      <th>Eligibility Criteria</th>
      <th>Features</th>
    </tr>
    <tr>
      <td>
        <ul>
          <li>People who earn 35k or less</li>
          <li>Any province of residence</li>
          <li>Includes spouses and dependent children</li>
          <li>No students</li>
        </ul>
      </td>
      <td>
        <ul>
          <li>File tax return</li>
          <li>Register for Ontario trillium benefits</li>
          <li>Register for Climate action incentive</li>
          <li>Change address (<strong>paper and authenticated journey only</strong>)</li>
          <li>Claim charitable donations, political contributions, medical expenses, etc (for people who earn above basic personal amount)</li>
          <li>Notice of assessment immediately (authenticated journey), up to 2 weeks by mail (lite journey) and 8 weeks (paper)</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

The mature state will provide both a ‘lite’ and ‘authenticated’ journey within the online channel. Individual tax-filers can opt to answer security questions in order to access more features.