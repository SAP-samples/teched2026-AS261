# AS261 — Explore Autonomous CX

Hands-on experience with AI assistants and AI agents across Autonomous CX. Explore the Deal Qualification Assistant and Case Management Assistant, and see how specialized AI assistants support and enhance key customer experience processes.


### [Part 1 · Sales Cloud — Deal Qualification Assistant](#sales-cloud---deal-qualification-assistant--hands-on-tutorial)

- [1. Session Overview](#dqa-1-session-overview)
- [2. What Is the Deal Qualification Assistant?](#dqa-2-what-is-the-deal-qualification-assistant)
- [3. Meet Felicia — Why This Matters](#dqa-3-meet-felicia--why-this-matters)
- [4. How the Assistant Works, End to End](#dqa-4-how-the-assistant-works-end-to-end)
- [5. Prerequisites and System Access](#dqa-5-prerequisites-and-system-access)
- [6. Hands-on Exercises](#dqa-6-hands-on-exercises)
  - [Exercise 1 — Create a Lead](#dqa-exercise-1--create-a-lead)
  - [Exercise 2 — Enrich the Lead](#dqa-exercise-2--enrich-the-lead-lead-enrichment-agent)
  - [Exercise 3 — Qualify the Lead](#dqa-exercise-3--qualify-the-lead-lead-qualification-agent)
  - [Exercise 4 — Simulate Engagement](#dqa-exercise-4--simulate-engagement)
  - [Exercise 5 — Convert to Account and Contact](#dqa-exercise-5--convert-the-lead-to-account-and-contact)
  - [Exercise 6 — Convert to an Opportunity](#dqa-exercise-6--convert-the-lead-to-an-opportunity)
  - [Exercise 7 — Joule Conversational Interface (Optional)](#dqa-exercise-7--explore-the-joule-conversational-interface-optional)
- [7. Sample Prompts to Try in Joule](#dqa-7-sample-prompts-to-try-in-joule)
- [8. Frequently Asked Questions](#dqa-8-frequently-asked-questions)
- [9. Wrap-up and Key Takeaways](#dqa-9-wrap-up-and-key-takeaways)

### [Part 2 · Service Cloud — Case Management Assistant](#case-management-assistant--hands-on-tutorial)

- [1. Session Overview](#cma-1-session-overview)
- [2. What Is the Case Management Assistant?](#cma-2-what-is-the-case-management-assistant)
- [3. Meet Sarah — Why This Matters](#cma-3-meet-sarah--why-this-matters)
- [4. How the Assistant Works, End to End](#cma-4-how-the-assistant-works-end-to-end)
- [5. Prerequisites and System Access](#cma-5-prerequisites-and-system-access)
- [6. Hands-on Exercises](#cma-6-hands-on-exercises)
  - [Exercise 1 — Open an Inbound Email Case and Copy](#cma-exercise-1--open-an-inbound-email-case-and-copy)
  - [Exercise 2 — Trigger the Case Preparation](#cma-exercise-2--trigger-the-case-preparation)
  - [Exercise 3 — Trigger the Next Action](#cma-exercise-3--trigger-the-next-action)
  - [Exercise 5 — Trigger Registration and Verify](#cma-exercise-5--trigger-registration-and-optional-verify)
  - [Exercise 6 — Send Confirmation Email](#cma-exercise-6--send-confirmation-email)
  - [Exercise 7 — Explore via Joule (Optional)](#cma-exercise-7--optional-explore-via-joule)
- [7. Sample Prompts for Joule](#cma-7-sample-prompts-for-joule)
- [8. Frequently Asked Questions](#cma-8-frequently-asked-questions)
- [9. Wrap-up and Key Takeaways](#cma-9-wrap-up-and-key-takeaways)

---

## Sales Cloud - Deal Qualification Assistant — Hands-on Tutorial

> Try the Lead Enrichment, Qualification, and Conversion agents on a preconfigured SAP system

---

## <a id="dqa-1-session-overview"></a>1. Session Overview

Welcome to the hands-on lab for the Deal Qualification Assistant, part of the Autonomous Sales and Revenue capabilities in SAP Sales Cloud. In this session you will work in a preconfigured SAP system and experience, first-hand, how a set of collaborating AI agents turns a bare lead into a qualified, context-rich opportunity — without the sales rep having to jump between screens.

### What you will do

- Create a lead with minimal information, the way it typically arrives from a web form or campaign.
- Trigger the Deal Qualification Assistant and watch the **Lead Enrichment Agent** add firmographic and technographic context.
- Trigger the assistant again and see the **Lead Qualification Agent** score fit and intent, moving the lead from Enriched to Accepted.
- Simulate rep engagement (emails, notes, an appointment) and optionally complete a qualification survey.
- Accept the assistant's proposal to convert the lead into an Account and Contact.
- Accept the assistant's proposal to convert the qualified lead into an Opportunity, complete with an AI-generated handover summary.
- Explore the same capability conversationally through Joule.

### Format

- **Duration:** approx. 60–75 minutes, self-paced with facilitators circulating.
- You will work individually on a preconfigured tenant assigned to your seat — do not use production or customer systems.
- **Facilitators:** Kiran and Vatsal. Raise your hand or flag a facilitator at any time.

> **Confidentiality:** This material is shared for the SAP TechEd hands-on session and for EAC (Early Adopter Care) participants only. The Deal Qualification Assistant is in Early Adopter Care and features, screens, and field names may change before general availability.

---

## <a id="dqa-2-what-is-the-deal-qualification-assistant"></a>2. What Is the Deal Qualification Assistant?

The Deal Qualification Assistant is the first of three planned assistants for Autonomous Sales and Revenue in SAP Sales Cloud. It works at the top of the funnel — the lead stage — acting as an orchestrator that invokes a set of specialized agents on your behalf.

*Figure 1 — Autonomous Agents in Sales Cloud: the Deal Qualification Assistant is one of three assistants planned for Autonomous Sales and Revenue.*

The three assistants are phased by where they sit in the deal lifecycle:

| Assistant | Lifecycle Stage | Status |
|---|---|---|
| Deal Qualification Assistant | Lead stage — enrichment, qualification, conversion | **In this hands-on session (EAC)** |
| Sales Assistant | Opportunity stage — deal management, meetings, email, risk | Roadmap |
| Deal Closing Assistant | Quote and order stage | Roadmap |

Within the Deal Qualification Assistant, five agents are planned. Three are available for this hands-on session; two are on the roadmap for a later quarter.

| Agent | Job to Be Done | Available Today? |
|---|---|---|
| Lead Enrichment Agent | Pulls firmographic, technographic, and sales signals from external sources to build an enriched profile. | **Yes** |
| Lead Qualification Agent | Applies scoring models to grade prospect fit and tracks intent to determine qualification. | **Yes** |
| Sales Engagement Agent* | Reaches out to qualified leads with personalized messages. | Roadmap — simulated in this lab |
| Lead Routing Agent* | Assigns the lead to the right sales rep or team based on territory, segment, and other factors. | Roadmap — simulated in this lab |
| Lead Conversion Agent | Converts qualified leads into opportunities, carrying full context forward. | **Yes** |

\* Because the Sales Engagement and Lead Routing agents are still on the roadmap, this hands-on session simulates engagement manually (Exercise 4) so you can still see how the Lead Qualification Agent reacts to engagement signals.

---

## <a id="dqa-3-meet-felicia--why-this-matters"></a>3. Meet Felicia — Why This Matters

Before you click anything, it helps to know whose problem this assistant solves. Felicia is a Sales Development Manager and the persona this assistant was designed around.

*Figure 2 — Felicia's three problems: lead quality, focus on the right leads, and effective conversion.*

### Felicia's three problems

- **Lead quality** — *"My SDRs waste time researching leads that arrive with no context. I need every lead automatically enriched and scored before it reaches the team."*
- **Focus on the right leads** — *"High-value leads get buried in the same queue as low-fit ones. I need leads pre-qualified against our target profile and routed to the right specialist."*
- **Effective conversion** — *"Leads stall because follow-up is inconsistent and conversion is manual. I need my team to engage leads with relevant outreach and convert them without loss of context."*

As you work through the exercises, keep Felicia's problems in mind — each agent you trigger is designed to solve exactly one of them: higher lead quality, faster response times, and more conversions from the same pipeline.

---

## <a id="dqa-4-how-the-assistant-works-end-to-end"></a>4. How the Assistant Works, End to End

The diagram below is the flow you will reproduce step by step in the exercises. Five data sources feed the agents, five agents each hand off a clear result to the next stage, and the end result is a qualified opportunity ready for pipeline execution.

*Figure 3 — Deal Qualification Assistant data flow: from raw lead data to a qualified opportunity.*

| Stage | Trigger | Result |
|---|---|---|
| Enrichment | Click **"Initiate Deal Qualification Assistant"** on an Open lead | Lead status → Enriched; AI Updates panel populated |
| Qualification | Click the assistant again on an Enriched lead | Fitment score calculated; status → Accepted (or Rejected) |
| Engagement (simulated) | Rep logs emails, calls, notes, an appointment | Interaction history available for the agent to factor in |
| Conversion (to Account) | Click the assistant again after engagement | Proposal to create Account + Contact; qualification may move to HOT |
| Conversion (to Opportunity) | Click the assistant again after BANT/qualification survey | Proposal to convert to Opportunity with an AI-generated handover summary |

> **Scope:** Today's demo scope does not integrate with S/4HANA or Master Data Governance (MDG); the Deal Qualification Assistant works purely within the lead-to-opportunity process in Sales Cloud.

---

## <a id="dqa-5-prerequisites-and-system-access"></a>5. Prerequisites and System Access

### What is already set up for you

- A preconfigured SAP Sales Cloud tenant with the Deal Qualification Assistant agents (Enrichment, Qualification, Conversion) activated.
- A user account with access to Leads, Accounts, Contacts, and Opportunities.
- Lead qualification settings (ICP fitment thresholds, status transitions) pre-configured by the facilitators.

### What you need to bring

- A laptop with a supported browser (Chrome or Edge, latest version).
- Your assigned login credentials, provided at the start of the session — check with a facilitator if you did not receive one.

### Good to know before you start

- Activation in a real tenant is a two-step process: (1) provisioning and connectivity, handled by SAP during onboarding, and (2) configuration of lead settings such as ICP fitment and status rules, done once by an admin. Both steps are already done for you in this lab.
- Any user with access to Leads can use the Deal Qualification Assistant — there is no separate agent-specific role to assign.
- If you want to try the conversational (Joule) experience in Exercise 7, this requires SAP Managed Joule for Sales and Service to be enabled on the tenant; the embedded, in-lead experience (Exercises 2–6) does not require this.

---

## <a id="dqa-6-hands-on-exercises"></a>6. Hands-on Exercises

### <a id="dqa-exercise-1--create-a-lead"></a>Exercise 1 — Create a Lead

Start where most leads start: with very little information. Imagine this lead just arrived from a web form.

1. In your Sales Cloud tenant, navigate to **Leads**.
2. Click **New** and enter only the basic details a web form would typically capture:
   - Company name
   - Contact first and last name
   - Contact email address
3. Save the lead. Note the **Lead Status** — it should be **Open**.
4. Open the lead record and look at the **AI Updates** section — it should be empty at this point.

> **Note:** This is intentional: with only a name, company, and email, a rep has almost nothing to work with, either to engage the prospect or to judge how important this lead is.

---

### <a id="dqa-exercise-2--enrich-the-lead-lead-enrichment-agent"></a>Exercise 2 — Enrich the Lead (Lead Enrichment Agent)

1. On the open lead, click **Initiate Deal Qualification Assistant**.
2. Wait for the assistant to run. Because the lead status is **Open**, the assistant invokes the **Lead Enrichment Agent**.
3. Review the **AI Updates** section — it should now list what the agent added, for example website and other firmographic/technographic details that belong to the lead data model.
4. Scroll to any **Notes** added by the agent — these capture details that aren't part of the formal data model but are useful talking points for the rep (e.g. recent company news, technographic signals).
5. Check the **Lead Status** — it should have moved from **Open** to **Enriched**.

> **Expected outcome:** → **ENRICHED PROFILE** is the agent's hand-off to the next stage, exactly as shown in Figure 3.

---

### <a id="dqa-exercise-3--qualify-the-lead-lead-qualification-agent"></a>Exercise 3 — Qualify the Lead (Lead Qualification Agent)

1. With the lead now **Enriched**, click **Initiate Deal Qualification Assistant** again.
2. This time the assistant invokes the **Lead Qualification Agent**, since the lead is already enriched.
3. Review the **AI Updates** — you should see a **Fitment Score** (for example, 70), calculated against your organization's Ideal Customer Profile (ICP).
4. Check the **Lead Status** — a fitment score high enough to pass your configured threshold moves the status from **Enriched** to **Accepted**.
5. Read the reasoning the agent provides for the score — this is what a rep would use to decide whether and how urgently to act.

> **Expected outcome:** → **SCORE & PRIORITY**. If your lead does not clear the threshold, the status may not change to Accepted — try enriching a second lead with different data to compare outcomes.

---

### <a id="dqa-exercise-4--simulate-engagement"></a>Exercise 4 — Simulate Engagement

In production, the future Sales Engagement Agent would draft and send this outreach automatically. Since that agent is still on the roadmap, this step is manual so you can see how the Lead Qualification Agent reads engagement signals.

1. On your **Accepted** lead, log at least two interactions, for example:
   - An email sent to the contact
   - A follow-up call or an appointment
   - A free-text opportunity note summarizing what was discussed
2. **Optional but recommended:** complete the qualification survey (BANT or your organization's equivalent criteria) attached to the lead. Submitting it produces a survey score that also feeds the qualification agent.
3. Save your changes before moving to the next exercise.

---

### <a id="dqa-exercise-5--convert-the-lead-to-account-and-contact"></a>Exercise 5 — Convert the Lead to Account and Contact

1. Click **Initiate Deal Qualification Assistant** again.
2. The assistant now proposes converting the lead into a proper **Account and Contact** (rather than staying a prospect), and the qualification may change to **HOT**.
3. Read the reasoning shown — it should reference the fitment score and the interactions you just logged.
4. Accept the proposal.
5. Open the newly created Account and confirm that the context captured by the Lead Enrichment Agent (e.g. the notes) has carried over automatically.

> **Note:** Notice what did not happen: you did not have to navigate to a separate menu to manually create the Account and Contact records — the assistant did it for you and preserved context.

---

### <a id="dqa-exercise-6--convert-the-lead-to-an-opportunity"></a>Exercise 6 — Convert the Lead to an Opportunity

1. Back on the lead, click **Initiate Deal Qualification Assistant** one more time.
2. The assistant now proposes converting the lead into an **Opportunity**, again with reasons tied to the interactions and survey responses collected so far.
3. Accept the proposal.
4. Open the new Opportunity and locate the **AI-generated lead handover summary** — this briefing means an account executive does not have to review every individual lead activity to pick up the deal.
5. Return to the **AI Updates** history on the original lead and review the full trail of updates from Open through to conversion — this is the transparency record of everything AI touched, from a bare lead to a converted opportunity.

---

### <a id="dqa-exercise-7--explore-the-joule-conversational-interface-optional"></a>Exercise 7 — Explore the Joule Conversational Interface (Optional)

If SAP Managed Joule for Sales and Service is enabled on your tenant, try the same capability conversationally instead of clicking through the lead record.

1. Open **Joule** and start a conversation.
2. Ask: *"What leads do I focus on today?"* — Joule invokes the relevant agent and returns a prioritized list with reasoning; selecting a lead populates its details.
3. Ask Joule to enrich a specific lead by name — if it is already enriched, Joule returns the enrichment details rather than re-running the agent.
4. Try a broader question, such as *"What are the leads that were recently updated?"*
5. Try a pointed question about a specific lead, such as *"Does [lead/company name] fit our ICP?"* — this invokes the Lead Qualification Agent for a direct answer.

*Figure 4 — Joule work: Conversations, Spaces, and Develop bring the same agents into a chat-first experience.*

---

## <a id="dqa-7-sample-prompts-to-try-in-joule"></a>7. Sample Prompts to Try in Joule

Use these as a starting point, then try your own. Facilitators recommend testing prompts against your own data set before rolling this out to business users.

- *"What leads do I focus on today?"*
- *"Enrich the lead for [Company Name]."*
- *"What leads were updated in the last 24 hours?"*
- *"Does [Company Name] fit our ideal customer profile?"*
- *"Summarize the AI updates for [Lead Name]."*
- *"Which of my leads are ready to convert to an opportunity?"*

---

## <a id="dqa-8-frequently-asked-questions"></a>8. Frequently Asked Questions

**Do I need SAP Managed Joule to use the Deal Qualification Assistant?**
No. The embedded, in-lead experience (Exercises 1–6) works without it. SAP Managed Joule is only required for the conversational experience in Exercise 7.

**Can I skip straight from a new lead to a converted opportunity?**
Not today. Each stage currently requires an explicit invocation of the assistant (either the button in the embedded experience or a Joule request) — there is no automatic background fast-tracking yet, partly to keep token consumption predictable. This is a known area the product team is exploring for the future.

**Does this check against Master Data Governance (MDG) or integrate with S/4HANA?**
Not in this release. The Deal Qualification Assistant is scoped to the lead-to-opportunity process in Sales Cloud and does not check MDG or touch S/4HANA. The upcoming Deal Closing Assistant will have S/4 touchpoints on the quotation and order side.

**Is there a special role needed to use these agents?**
No separate agent role is required. If a user already has access to Leads, they can use the Deal Qualification Assistant.

**How is usage/consumption estimated?**
As a rough approximation for forecasting, multiply the number of users who have Lead access by the number of assistant invocations (actions) you expect them to perform.

**Where can I try this after the conference?**
Ask your facilitator about access to a development/test landscape, and watch for the recorded demo and configuration guide, which are in draft. Per SAP's Early Adopter Care terms, please do not share recordings, configuration guides, or this tutorial outside SAP until the product is generally available and marketing has confirmed it can be shared externally.

---

## <a id="dqa-9-wrap-up-and-key-takeaways"></a>9. Wrap-up and Key Takeaways

- The Deal Qualification Assistant orchestrates a small set of purpose-built agents — enrichment, qualification, and conversion today; routing and engagement to follow.
- Each agent hands off one clear result to the next: enriched profile → score & priority → engaged lead → owner assigned → opportunity created.
- The same underlying agents are available two ways: embedded in the lead record, and conversationally through Joule.
- Every AI action is logged transparently in the **AI Updates** section, so reps and admins can see exactly what changed and why.
- This is Early Adopter Care software — expect the UI and available agents to evolve before general availability.

---

*Questions? Flag a facilitator during the session, or bring them to the community session at the end of this track.*

---

## Case Management Assistant — Hands-on Tutorial

> Try the Case Preparation, Case Processing & Case Action Recommendation Agents on a preconfigured SAP system
>
> TechEd Landscape – Modelled after Early Adopter Care (EAC) Enablement

---

## <a id="cma-1-session-overview"></a>1. Session Overview

This is a ~60–75 minute self-paced hands-on lab running on a preconfigured SAP Service Cloud V2 tenant. You will work through the end-to-end lifecycle of a service case handled by the Case Management Assistant — from the moment an email arrives, through intelligent preparation and triage, guided resolution with Next Best Actions, to final customer acknowledgement.

### By the end of this session you will have

- Seen how the **Case Preparation Agent** automatically extracts and enriches an inbound email case
- Experienced the **Case Processing Agent** guiding you through resolution step-by-step with AI-recommended actions
- Drafted and sent a customer acknowledgement generated by the assistant
- Optionally, triggered the same flow conversationally through Joule

---

## <a id="cma-2-what-is-the-case-management-assistant"></a>2. What Is the Case Management Assistant?

The Case Management Assistant is part of the broader **Autonomous Service** stream in SAP Service Cloud V2.

*Figure 1 — Autonomous Assistants and Agents under Autonomous Service: Case Management Assistant is one of the assistants planned in SAP Service Cloud.*

The Case Management Assistant transforms how service teams handle cases by automating end-to-end case workflows. It coordinates autonomous AI agents to process cases and provide service teams with real-time insights and recommendations that enable them to triage, manage, and resolve cases faster — increasing operational efficiency and improving customer experiences.

### The 3 Agents

| Agent | What It Does |
|---|---|
| **Case Preparation Agent** | Extracts key information, identifies case type, generates issue summary, prioritises, categorises, and routes. Enriches with customer history, entitlements, and installed base from connected SAP systems. |
| **Case Processing Agent** | Guides the service rep through the resolution workflow step by step. Recommends Next Best Actions. Can execute autonomously — service orders, return authorisations, follow-up tasks, field service requests in S/4HANA. Drafts customer communications. |
| **Case Action Recommendation Agent** | Synthesises relevant knowledge articles, resolution guides, troubleshooting docs, and similar prior cases — delivering targeted, contextually ranked guidance. |

---

## <a id="cma-3-meet-sarah--why-this-matters"></a>3. Meet Sarah — Why This Matters

Before you click anything, it helps to know whose problem this assistant solves. Sarah is a Service Representative and the persona this assistant was designed around.

### Sarah's 3 problems

- **Inbox overload** — Dozens of cases are created every day, and Sarah spends significant time reading through the subject, description, and other information.
- **Context switching for pre-checks** — Each new case requires Sarah to look up the customer's details, entitlement status, and registered products across different screens.
- **Resolution and follow-up actions** — Service agents handle similar cases in different ways. There is no systematic guidance on what to do next, so resolution quality depends entirely on individual experience.

During the exercises, each agent triggered is designed to solve exactly one of these problems.

---

## <a id="cma-4-how-the-assistant-works-end-to-end"></a>4. How the Assistant Works, End to End

| Stage | Trigger | Agent | Result |
|---|---|---|---|
| Case Preparation | Rep clicks **Prepare Case** | Case Preparation Agent | Issue summary generated; key fields extracted; category and priority set |
| Smart Analysis | Rep clicks **Prepare Case** | Case Processing Agent + Case Action Recommendation Agent | Step-by-step resolution guidance; Next Best Actions proposed |
| Action Confirmation | Rep confirms recommended action | Case Processing Agent | Action executed; communication draft generated |
| Send Communication | Rep confirms draft | Case Processing Agent | Email sent |
| (Optional) Joule | Rep types prompt in Joule | Case Management Orchestrator | Same flow accessible conversationally via natural language |

> **Human-in-the-Loop (HITL) gates are mandatory.** The assistant proposes; the representative decides. No action is taken without explicit approval.

---

## <a id="cma-5-prerequisites-and-system-access"></a>5. Prerequisites and System Access

### What is pre-configured for you

- A SAP Service Cloud V2 tenant with Case Management Assistant activated
- A user account with service representative role and access to the **Cases** application
- A pre-loaded customer account (Individual customer Taylor Jones)
- Sample inbound email cases pre-staged in the system inbox
- Joule configured (for Exercise 7 only)

### What you do NOT need

- No separate agent or AI role — standard case access is sufficient
- No specific configuration — all setup is complete
- No prior experience with Joule — Exercise 7 has step-by-step prompts

---

## <a id="cma-6-hands-on-exercises"></a>6. Hands-on Exercises

Work through the exercises in order. Each builds on the previous one. **Estimated total time: 10–15 minutes.**

---

### <a id="cma-exercise-1--open-an-inbound-email-case-and-copy"></a>Exercise 1 — Open an Inbound Email Case and Copy

1. Log in to **SAP Service Cloud V2** with the credentials on your lab card.
2. Navigate to **Cases → All Cases**.
3. Find the case with a subject similar to *"Sample Case for TechEd Session"*. Copy it.
4. Update the subject and description to ensure a unique serial ID is given.
5. Observe the case header: note what is already populated and what is missing.
6. Open the **AI Mode (Assistant)** tab and wait for the AI Agent to provide an initial summary.

> **Expected result:** Initial summary is displayed. Key fields such as category, issue summary, and priority are not yet populated. AI Agent suggests Case Preparation.

> **Note:** If the AI Mode tab is not visible, check that the AI Mode tab is added on the Case Detail screen via Adaptation.

---

### <a id="cma-exercise-2--trigger-the-case-preparation"></a>Exercise 2 — Trigger the Case Preparation

1. Click the **"Prepare Case"** button.
2. Watch the updates populate in real time. The **Case Preparation Agent** will:
   - Extract the case category (example: *Product Services → Product Registration*)
   - Identify customer sentiment (example: *Neutral*)
   - Generate a concise issue summary
   - Surface relevant customer and product context
3. Review the enriched case header. Verify that category and priority fields are now populated and accurate.

> **Expected result:** Category field is filled. Priority field is set.

---

### <a id="cma-exercise-3--trigger-the-next-action"></a>Exercise 3 — Trigger the Next Action

1. After case preparation, the assistant automatically triggers the **Case Processing Agent**.
2. The AI Agent proposes the next action. Click on **"Smart Analysis"**.
3. The AI Agent validates the registration request and presents the **Product Registration Status**. Example: if the serial ID is unique then registration can proceed.

> **Expected result:** Product Registration Status is displayed.

---

### <a id="cma-exercise-5--trigger-registration-and-optional-verify"></a>Exercise 5 — Trigger Registration and (Optional) Verify

1. Click on **"Register Refrigerator"**.
2. The AI Agent registers the product and provides a **Registration Update**.
3. The AI Agent drafts an email and proposes the next action to review and send the email.
4. *(Optional)* Go to **Main Menu → Registered Products** and see the registered product with the relevant serial ID in the list, or search with the serial ID / customer.

> **Expected result:** Registration is successful.

---

### <a id="cma-exercise-6--send-confirmation-email"></a>Exercise 6 — Send Confirmation Email

1. On the Case detail screen – **AI Mode (Assistant)** tab, click on **"Review and send confirmation email"**.
2. The **Email** tab opens automatically with the draft email content filled in.
3. Edit the draft if you wish. Enter the **To** email address and send.
4. Refresh the case (Refresh icon on the top of the Case left header panel) and go to the **Timeline** tab. The email sent event is displayed.

> **Expected result:** Email is sent and Timeline is updated.

---

### <a id="cma-exercise-7--optional-explore-via-joule"></a>Exercise 7 — (Optional) Explore via Joule

> **Note:** This exercise requires SAP Managed Joule for Service. If Joule is not available in your lab tenant, you may skip this exercise.

1. Open the **Joule** work desktop.
2. Invoke `@case management assistant` — *"Show me a list of cases that I need to look into."*
3. Joule will surface relevant cases including the product registration case.
4. Type *"Show case \<ID\> details"* (choose a case with a registration request).
5. The Case Management Assistant will run the **Case Preparation Agent** and return the enriched case directly in the Joule panel. The next actions are also presented and can be followed.
6. Try additional prompts from [Section 7](#7-sample-prompts-for-joule) of this document.

> **Expected result:** Joule returns the same structured output as the embedded UI experience — issue summary, proposed case structure, recommended actions — in a conversational format.

---

## <a id="cma-7-sample-prompts-for-joule"></a>7. Sample Prompts for Joule

Use these as a starting point and try your own.

- *"Summarize the Case \<ID\>."*
- *"Get me a list of my open cases."*
- *"Get a list of open cases for customer \<Alpha Center\>."*
- *"Show me a list of cases reported on \<25th Oct 2026\>."*
- *"Prepare an email draft for case \<ID\> as per current status to send to the customer."*
- *"Show me cases with high priority."*

---

## <a id="cma-8-frequently-asked-questions"></a>8. Frequently Asked Questions

**Do I need Joule to use the Case Management Assistant?**
No. Exercises 1–6 use the assistant embedded directly in the case detail UI. Joule is only needed for Exercise 7.

**Does the assistant act automatically without my input?**
No. Every significant action — confirming case structure, approving Next Best Actions, sending customer communications — requires explicit human confirmation. The assistant proposes; you decide.

**Can the assistant handle cases from channels other than email?**
Yes — the Case Preparation Agent normalises case context from email, chat, web forms, and phone transcripts. This lab uses an email case, but the same agents apply across all channels.

**Is the Knowledge Content Creation Agent available today?**
Not in this lab. The Knowledge Content Creation Agent is on the roadmap.

**What is the confidentiality of this session?**
Internal / EAC use only until General Availability. Do not share tenant credentials, screenshots, or session materials externally.

---

## <a id="cma-9-wrap-up-and-key-takeaways"></a>9. Wrap-up and Key Takeaways

- The Case Management Assistant orchestrates a set of purpose-built agents working together end to end.
- The **Case Preparation Agent** prepares and enriches a case by adding a problem summary, categorisation, prioritisation, and entity extraction.
- The **Case Processing Agent** provided targeted, step-by-step Next Best Actions.
- **Human-in-the-Loop gates** ensured that the representative retained full control at every critical decision point — no action was taken without explicit approval.
- The assistant is available two ways: embedded in the case detail UI for guided, in-context interaction, and conversationally via Joule for natural language access.

---

*Questions? Flag a facilitator during the session or bring them to the SAP Booth / Ask the Expert pods.*

*Thank you for attending.*

---

> SAP TechEd Berlin · Case Management Assistant Hands-on Session · Internal / EAC use only


## License
Copyright (20xx-)20xx SAP SE or an SAP affiliate company and <your-project> contributors. Please see our [LICENSE](LICENSE) for copyright and license information. Detailed information including third-party components and their licensing/copyright information is available [via the REUSE tool](https://api.reuse.software/info/github.com/SAP/<your-project>).
