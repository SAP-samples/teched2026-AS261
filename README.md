# Containing Files

1. The LICENSE file:
In most cases, the license for SAP sample projects is `Apache 2.0`.

2. The REUSE.toml file: 
The [Reuse Tool](https://reuse.software/) must be used for your samples project. You can find the REUSE.toml in the project initial. Please replace the parts inside the single angle quotation marks < > by the specific information for your repository.

3. The README.md file (this file):
Please edit this file as it is the primary description file for your project. You can find some placeholder titles for sections below.

## AS261 — Autonomous Agents for CX


### Sales Cloud - Deal Qualification Assistant — Hands-on Tutorial

> Try the Lead Enrichment, Qualification, and Conversion agents on a preconfigured SAP system

---

## Table of Contents

1. [Session Overview](#1-session-overview)
2. [What Is the Deal Qualification Assistant?](#2-what-is-the-deal-qualification-assistant)
3. [Meet Felicia — Why This Matters](#3-meet-felicia--why-this-matters)
4. [How the Assistant Works, End to End](#4-how-the-assistant-works-end-to-end)
5. [Prerequisites and System Access](#5-prerequisites-and-system-access)
6. [Hands-on Exercises](#6-hands-on-exercises)
   - [Exercise 1 — Create a Lead](#exercise-1--create-a-lead)
   - [Exercise 2 — Enrich the Lead (Lead Enrichment Agent)](#exercise-2--enrich-the-lead-lead-enrichment-agent)
   - [Exercise 3 — Qualify the Lead (Lead Qualification Agent)](#exercise-3--qualify-the-lead-lead-qualification-agent)
   - [Exercise 4 — Simulate Engagement](#exercise-4--simulate-engagement)
   - [Exercise 5 — Convert the Lead to Account and Contact](#exercise-5--convert-the-lead-to-account-and-contact)
   - [Exercise 6 — Convert the Lead to an Opportunity](#exercise-6--convert-the-lead-to-an-opportunity)
   - [Exercise 7 — Explore the Joule Conversational Interface (Optional)](#exercise-7--explore-the-joule-conversational-interface-optional)
7. [Sample Prompts to Try in Joule](#7-sample-prompts-to-try-in-joule)
8. [Frequently Asked Questions](#8-frequently-asked-questions)
9. [Wrap-up and Key Takeaways](#9-wrap-up-and-key-takeaways)

---

## 1. Session Overview

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

## 2. What Is the Deal Qualification Assistant?

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

## 3. Meet Felicia — Why This Matters

Before you click anything, it helps to know whose problem this assistant solves. Felicia is a Sales Development Manager and the persona this assistant was designed around.

*Figure 2 — Felicia's three problems: lead quality, focus on the right leads, and effective conversion.*

### Felicia's three problems

- **Lead quality** — *"My SDRs waste time researching leads that arrive with no context. I need every lead automatically enriched and scored before it reaches the team."*
- **Focus on the right leads** — *"High-value leads get buried in the same queue as low-fit ones. I need leads pre-qualified against our target profile and routed to the right specialist."*
- **Effective conversion** — *"Leads stall because follow-up is inconsistent and conversion is manual. I need my team to engage leads with relevant outreach and convert them without loss of context."*

As you work through the exercises, keep Felicia's problems in mind — each agent you trigger is designed to solve exactly one of them: higher lead quality, faster response times, and more conversions from the same pipeline.

---

## 4. How the Assistant Works, End to End

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

## 5. Prerequisites and System Access

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

## 6. Hands-on Exercises

### Exercise 1 — Create a Lead

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

### Exercise 2 — Enrich the Lead (Lead Enrichment Agent)

1. On the open lead, click **Initiate Deal Qualification Assistant**.
2. Wait for the assistant to run. Because the lead status is **Open**, the assistant invokes the **Lead Enrichment Agent**.
3. Review the **AI Updates** section — it should now list what the agent added, for example website and other firmographic/technographic details that belong to the lead data model.
4. Scroll to any **Notes** added by the agent — these capture details that aren't part of the formal data model but are useful talking points for the rep (e.g. recent company news, technographic signals).
5. Check the **Lead Status** — it should have moved from **Open** to **Enriched**.

> **Expected outcome:** → **ENRICHED PROFILE** is the agent's hand-off to the next stage, exactly as shown in Figure 3.

---

### Exercise 3 — Qualify the Lead (Lead Qualification Agent)

1. With the lead now **Enriched**, click **Initiate Deal Qualification Assistant** again.
2. This time the assistant invokes the **Lead Qualification Agent**, since the lead is already enriched.
3. Review the **AI Updates** — you should see a **Fitment Score** (for example, 70), calculated against your organization's Ideal Customer Profile (ICP).
4. Check the **Lead Status** — a fitment score high enough to pass your configured threshold moves the status from **Enriched** to **Accepted**.
5. Read the reasoning the agent provides for the score — this is what a rep would use to decide whether and how urgently to act.

> **Expected outcome:** → **SCORE & PRIORITY**. If your lead does not clear the threshold, the status may not change to Accepted — try enriching a second lead with different data to compare outcomes.

---

### Exercise 4 — Simulate Engagement

In production, the future Sales Engagement Agent would draft and send this outreach automatically. Since that agent is still on the roadmap, this step is manual so you can see how the Lead Qualification Agent reads engagement signals.

1. On your **Accepted** lead, log at least two interactions, for example:
   - An email sent to the contact
   - A follow-up call or an appointment
   - A free-text opportunity note summarizing what was discussed
2. **Optional but recommended:** complete the qualification survey (BANT or your organization's equivalent criteria) attached to the lead. Submitting it produces a survey score that also feeds the qualification agent.
3. Save your changes before moving to the next exercise.

---

### Exercise 5 — Convert the Lead to Account and Contact

1. Click **Initiate Deal Qualification Assistant** again.
2. The assistant now proposes converting the lead into a proper **Account and Contact** (rather than staying a prospect), and the qualification may change to **HOT**.
3. Read the reasoning shown — it should reference the fitment score and the interactions you just logged.
4. Accept the proposal.
5. Open the newly created Account and confirm that the context captured by the Lead Enrichment Agent (e.g. the notes) has carried over automatically.

> **Note:** Notice what did not happen: you did not have to navigate to a separate menu to manually create the Account and Contact records — the assistant did it for you and preserved context.

---

### Exercise 6 — Convert the Lead to an Opportunity

1. Back on the lead, click **Initiate Deal Qualification Assistant** one more time.
2. The assistant now proposes converting the lead into an **Opportunity**, again with reasons tied to the interactions and survey responses collected so far.
3. Accept the proposal.
4. Open the new Opportunity and locate the **AI-generated lead handover summary** — this briefing means an account executive does not have to review every individual lead activity to pick up the deal.
5. Return to the **AI Updates** history on the original lead and review the full trail of updates from Open through to conversion — this is the transparency record of everything AI touched, from a bare lead to a converted opportunity.

---

### Exercise 7 — Explore the Joule Conversational Interface (Optional)

If SAP Managed Joule for Sales and Service is enabled on your tenant, try the same capability conversationally instead of clicking through the lead record.

1. Open **Joule** and start a conversation.
2. Ask: *"What leads do I focus on today?"* — Joule invokes the relevant agent and returns a prioritized list with reasoning; selecting a lead populates its details.
3. Ask Joule to enrich a specific lead by name — if it is already enriched, Joule returns the enrichment details rather than re-running the agent.
4. Try a broader question, such as *"What are the leads that were recently updated?"*
5. Try a pointed question about a specific lead, such as *"Does [lead/company name] fit our ICP?"* — this invokes the Lead Qualification Agent for a direct answer.

*Figure 4 — Joule work: Conversations, Spaces, and Develop bring the same agents into a chat-first experience.*

---

## 7. Sample Prompts to Try in Joule

Use these as a starting point, then try your own. Facilitators recommend testing prompts against your own data set before rolling this out to business users.

- *"What leads do I focus on today?"*
- *"Enrich the lead for [Company Name]."*
- *"What leads were updated in the last 24 hours?"*
- *"Does [Company Name] fit our ideal customer profile?"*
- *"Summarize the AI updates for [Lead Name]."*
- *"Which of my leads are ready to convert to an opportunity?"*

---

## 8. Frequently Asked Questions

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

## 9. Wrap-up and Key Takeaways

- The Deal Qualification Assistant orchestrates a small set of purpose-built agents — enrichment, qualification, and conversion today; routing and engagement to follow.
- Each agent hands off one clear result to the next: enriched profile → score & priority → engaged lead → owner assigned → opportunity created.
- The same underlying agents are available two ways: embedded in the lead record, and conversationally through Joule.
- Every AI action is logged transparently in the **AI Updates** section, so reps and admins can see exactly what changed and why.
- This is Early Adopter Care software — expect the UI and available agents to evolve before general availability.

---

*Questions? Flag a facilitator during the session, or bring them to the community session at the end of this track.*

---

> SAP TechEd Berlin · Deal Qualification Assistant Hands-on Session · Kiran Karadi · Internal / EAC use only

**IMPORTANT**

Your repo must contain the .reuse and LICENSES folder and the License section below. DO NOT REMOVE the section or folders/files. Also, remove all unused template assets(images, folders, etc) from the exercises folder. 

## Contributing
Please read the [CONTRIBUTING.md](./CONTRIBUTING.md) to understand the contribution guidelines.

## Code of Conduct
Please read the [SAP Open Source Code of Conduct](https://github.com/SAP-samples/.github/blob/main/CODE_OF_CONDUCT.md).

## How to obtain support

Support for the content in this repository is available during the actual time of the online session for which this content has been designed. Otherwise, you may request support via the [Issues](../../issues) tab.

## License
Copyright (20xx-)20xx SAP SE or an SAP affiliate company and <your-project> contributors. Please see our [LICENSE](LICENSE) for copyright and license information. Detailed information including third-party components and their licensing/copyright information is available [via the REUSE tool](https://api.reuse.software/info/github.com/SAP/<your-project>).
