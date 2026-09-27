# AI Proposal Generation System

An AI-powered proposal generation and delivery workflow designed to automate proposal creation, client communication, proposal tracking and internal record management.

---

## 📌 Project Snapshot

| | |
|---|---|
| **Project Type** | AI Proposal Generation & Delivery Automation |
| **Role** | AI Automation Engineer / Workflow Designer |
| **Project Status** | Designed & Documented — Not Production Tested |
| **Workflow Platform** | n8n |
| **Core Technologies** | n8n, OpenAI, Google Sheets, Gmail, Notion |
| **Workflow Nodes** | 6 |
| **Primary Objective** | Automate proposal creation, delivery and record management |

---

## 🎯 Overview

Creating a professional proposal for every client or lead can involve collecting project information, structuring requirements, writing the proposal, formatting it, sending it to the client and maintaining an internal record.

I designed an **AI Proposal Generation System** to connect these activities into a single workflow.

The system accepts client/project information, cleans and structures the data, uses AI to generate a customized proposal, logs the proposal in Google Sheets, sends it through Gmail and stores a copy in Notion.

### Complete Flow

**Client Input → Data Formatting → AI Proposal Generation → Google Sheets Log → Gmail Delivery → Notion Storage**

The workflow was designed as a modular six-node n8n architecture.

📁 **[View Project Screenshots](assets/)**

---

## 💡 Business Problem

Proposal creation can become repetitive when a business handles multiple prospects or projects.

A typical process may require:

- Collecting client requirements
- Reviewing budget and timeline
- Writing a proposal
- Structuring the scope and deliverables
- Formatting the document
- Sending the proposal
- Recording proposal information
- Maintaining a history for future follow-ups

When these steps are performed manually, the process can become inconsistent and difficult to manage at scale.

The system was designed around one objective:

> **Convert structured client requirements into a professional proposal and automatically handle the delivery and record-keeping process.**

---

## ⚙️ Solution

The workflow connects the proposal lifecycle into a sequential automation:

**Client / Lead Input**

↓

**Clean & Structure Data**

↓

**AI Proposal Generation**

↓

**Log Proposal**

↓

**Send via Gmail**

↓

**Store in Notion**

The architecture can be divided into three functional layers:

**Input Layer → AI Layer → Delivery & Storage Layer**

📁 **[View Workflow Screenshots](assets/)**

---

## 1. 📝 Client Information Intake

The workflow begins with a webhook/form-based input.

The intended input contains information such as:

- Client name
- Email
- Required service
- Budget
- Deadline
- Additional requirements or notes

This creates a structured starting point for the rest of the workflow.

📁 **[View Intake Screenshot](assets/)**

---

## 2. 🧹 Data Cleaning & Formatting

Before sending the information to the AI model, the workflow passes it through a formatting stage.

The purpose is to convert raw form data into a cleaner internal structure.

For example:

**ClientName → client_name**

**Email → email**

**Service → service**

**Budget → budget**

**Deadline → deadline**

**Notes → notes**

The formatting layer also handles basic transformations such as trimming text, normalizing the email field and formatting budget/date information.

This creates cleaner and more predictable input for the AI generation stage.

---

## 3. 🤖 AI Proposal Generation

The cleaned client information is passed to an **OpenAI** node.

The AI is instructed to generate a customized business proposal based on:

- Client name
- Required service
- Budget
- Deadline
- Additional notes

The proposal structure is designed to include:

1. Professional introduction
2. Scope of work
3. Deliverables
4. Timeline and milestones
5. Pricing summary
6. Closing call-to-action

The purpose of this layer is to transform structured requirements into a proposal draft with a consistent business-oriented structure.

📁 **[View AI Generation Screenshot](assets/)**

---

## 4. 📊 Proposal Logging

After proposal generation, the workflow logs the proposal information in **Google Sheets**.

The proposed tracking structure includes fields such as:

- Date
- Client Name
- Service
- Budget
- Status

This provides a centralized record of proposals generated through the workflow.

The workflow uses a Google Sheets **Append** operation for this stage.

---

## 5. 📧 Automated Proposal Delivery

The next stage uses **Gmail** to send the generated proposal to the client's email address.

The intended email contains:

- Client name
- Service information
- Proposal content
- Professional closing/signature

The workflow uses HTML formatting for the email so that the generated proposal remains readable when delivered to the client.

This connects proposal generation directly with delivery instead of requiring the generated content to be manually copied into an email.

📁 **[View Gmail Delivery Screenshot](assets/)**

---

## 6. 🗂️ Notion Proposal Storage

The final stage stores the proposal information in a **Notion database**.

The proposed record can contain:

- Client name
- Service
- Budget
- Date
- Proposal text
- Status

This creates a searchable internal record that can be used for proposal tracking and future follow-up.

The n8n workflow contains a Notion database-page creation node for this stage.

📁 **[View Notion Screenshot](assets/)**

---

# 🔄 End-to-End Architecture

The complete system can be represented as:

**Client / Lead Input**

↓

**Data Cleaning & Formatting**

↓

**AI Proposal Generation**

↓

**Google Sheets Proposal Log**

↓

**Gmail Proposal Delivery**

↓

**Notion Proposal Record**

The six nodes are connected sequentially so that information flows from the initial client input through generation, tracking, delivery and storage.

📁 **[View Full n8n Workflow](assets/)**

---

# 🛠️ Tools & Technologies

| **Technology** | **Purpose** |
|---|---|
| **n8n** | Workflow orchestration |
| **OpenAI** | Proposal generation |
| **Google Sheets** | Proposal logging |
| **Gmail** | Proposal delivery |
| **Notion** | Proposal storage and tracking |
| **Webhook / Form** | Client information intake |

The architecture uses each tool for a specific stage of the business process rather than treating AI as the entire automation.

---

# 🧩 Implementation Approach

The workflow was designed around a simple sequential architecture:

**Capture → Clean → Generate → Log → Deliver → Store**

Each stage receives structured information from the previous stage.

This modular approach makes it possible to modify individual components without redesigning the entire workflow.

For example:

- The input source can be changed from a webhook to a CRM.
- Different proposal types can use different AI prompts.
- A PDF generation layer can be added before email delivery.
- CRM integration can be added after proposal generation.
- Follow-up automation can be added after delivery.

These expansion paths are identified as potential extensions of the workflow.

---

# 🧪 Current Status & Testing

This is a **designed portfolio automation architecture** and was not connected to production credentials or tested with real client data.

Therefore, this case study does **not** claim:

- Production deployment
- Real proposals delivered
- Real client responses
- Measured proposal conversion
- Measured time savings
- Revenue generated
- Production performance metrics

### Current Status

> **Designed and documented as a realistic AI proposal automation workflow; production validation was not performed.**

The testing instructions describe how the workflow could be validated using sample client data, but those instructions are not presented as evidence of successful production testing.

---

# 📈 Expected Operational Impact

Because no production metrics were collected, the following are **expected capabilities rather than measured results**.

### ⚡ Automated Proposal Preparation

Client information can be transformed into structured proposal content through the AI generation layer.

### 📄 Consistent Proposal Structure

The AI prompt establishes a repeatable structure covering scope, deliverables, timeline, pricing and closing information.

### 📧 Faster Delivery Workflow

Once configured with production credentials, the generated proposal can move directly into the delivery stage.

### 🗂️ Centralized Proposal Records

Google Sheets and Notion provide structured locations for proposal tracking and storage.

### 🔁 Reduced Repetitive Administrative Work

The workflow connects proposal creation, logging, delivery and storage instead of requiring each step to be handled separately.

> These are **designed capabilities**, not measured production outcomes.

---

# 🧠 Key Engineering Learnings

### 1. AI generation needs structured inputs

The AI layer becomes more reliable when client information is cleaned and standardized before generation.

### 2. AI should be surrounded by deterministic workflow logic

The AI generates the proposal content, while n8n controls data flow, logging, delivery and storage.

### 3. Proposal automation is more than content generation

Generating text is only one part of the process.

A practical proposal system also needs:

**Input → Generation → Tracking → Delivery → Storage**

### 4. Record-keeping should be part of the workflow

Automatically storing proposal information creates a useful history for future follow-ups and reporting.

### 5. Modular workflows are easier to expand

The current six-node architecture can later be extended with PDF generation, CRM synchronization, approval steps, Slack notifications or follow-up automation.

---

# 🚀 Future Improvements

Potential production extensions include:

- HTML → PDF proposal generation
- Proposal approval before sending
- Multiple proposal templates
- Service-specific AI prompts
- AI tone selection
- CRM integration
- Google Drive proposal storage
- Slack notifications
- Automated proposal follow-ups
- Proposal status dashboard
- AI-generated executive summary
- Proposal version tracking

These extensions can transform the basic proposal workflow into a more complete proposal-management system.

---

# ♻️ Reusable Components

The workflow contains several reusable components that can be adapted to other business automation systems:

- Form/webhook data intake
- Data cleaning and normalization
- AI content generation
- Structured prompt design
- Google Sheets logging
- Automated Gmail delivery
- Notion database storage
- Sequential workflow orchestration

These components can be reused for:

- Proposals
- Quotations
- Statements of work
- Client reports
- Other document-generation workflows

---

# 📸 Project Evidence

All available workflow screenshots and project evidence are stored inside the repository's `assets` folder.

📁 **[Open Assets Folder](assets/)**

The folder contains the available screenshots and workflow evidence for this project.

---

# 📌 Final Takeaway

The **AI Proposal Generation System** demonstrates how AI can be integrated into a complete business workflow rather than being used only as a text-generation tool.

The system connects:

**Client Input → Data Preparation → AI Proposal Generation → Logging → Email Delivery → Internal Storage**

The architecture was designed to make proposal creation and administration more structured, while keeping the workflow modular enough for future CRM, PDF, approval and follow-up integrations.

This project is presented as a **designed and documented automation architecture**, not as a production deployment or a system with measured business results.

---

# 📊 Project Evidence Summary

| | |
|---|---|
| **Project** | AI Proposal Generation System |
| **Workflow Platform** | n8n |
| **AI Layer** | OpenAI |
| **Integrations** | Google Sheets, Gmail, Notion |
| **Architecture** | 6-node sequential workflow |
| **Testing Status** | Not production tested |
| **Primary Focus** | Proposal generation, delivery and record management |
| **Documentation** | n8n workflow + implementation guide |
| **Project Status** | **Designed & Documented — Production Validation Pending** |

---

## 🌐 Portfolio

**[View My Portfolio](https://priyansh-roy.github.io/priyansh-portfolio/)**

---

## 🛠️ Tech Stack

`n8n` · `OpenAI` · `Google Sheets` · `Gmail` · `Notion` · `Webhooks`
