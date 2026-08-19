# LinkGPT — AI-Powered Remote Job Search Agent

> An AI-powered job search automation system that turns a user's job requirements into targeted searches, filters relevant remote opportunities, identifies recruiters and hiring managers, organizes qualified leads, and generates personalized email drafts for human review.

---

## 🚀 Overview

**LinkGPT** is an AI-powered job search agent built to automate the repetitive parts of searching and applying for remote jobs.

Instead of manually searching for jobs, checking whether they are actually remote, finding relevant recruiters, organizing opportunities, and writing outreach emails, the user can simply send a message describing what they are looking for.

LinkGPT processes that request and takes it through an automated workflow.

### Example

The user can send:

> "Find remote AI Automation Engineer jobs that I can apply for from Pakistan. Focus on junior roles involving n8n, AI agents, APIs, and JavaScript."

LinkGPT then:

**Understands the request → Generates search queries → Searches for opportunities → Filters results → Finds relevant contacts → Organizes qualified opportunities → Generates personalized email drafts**

The emails are saved as **drafts rather than being sent automatically**, allowing the user to review and edit them before sending.

---

## 🎯 Problem

Searching for remote jobs can involve a lot of repetitive manual work:

* Searching multiple platforms
* Creating different search queries
* Checking job requirements
* Verifying remote eligibility
* Filtering location restrictions
* Finding recruiters or hiring managers
* Collecting job information
* Maintaining spreadsheets
* Writing personalized outreach emails

LinkGPT aims to automate this workflow while keeping a **human-in-the-loop** before outreach.

---

## 💡 Solution

LinkGPT combines **AI agents, workflow automation, APIs, and structured data processing** to create an end-to-end job-search pipeline.

### Workflow

```text
User Message
     ↓
Understand Requirements
     ↓
Generate Targeted Search Query
     ↓
Search for Opportunities
     ↓
Extract & Structure Results
     ↓
Filter & Qualify Jobs
     ↓
Find Recruiters / Hiring Managers
     ↓
Store Qualified Opportunities
     ↓
Generate Personalized Email
     ↓
Save Email as Draft
     ↓
Human Review
```

---

## 🏗️ System Architecture

![LinkGPT Architecture](architecture/system-architecture.png)

The system is designed as a modular workflow where each stage has a specific responsibility.

### 1. User Input

The user provides natural-language requirements such as:

* Target role
* Skills
* Experience level
* Remote preference
* Location
* Job type
* Other requirements

The AI agent converts these requirements into structured information that can be used throughout the workflow.

---

### 2. Search Query Generation

The AI generates targeted search queries based on the user's requirements.

For example:

```text
(recruiter OR "Talent Acquisition Manager" OR "Hiring Manager")
AND
("AI Automation Engineer" OR "AI Automation Specialist")
AND
(remote)
AND
(Pakistan)
```

The goal is to make the search more targeted than a simple keyword search.

---

### 3. Job Discovery

LinkGPT uses search/API-based workflows to discover relevant opportunities.

The workflow can collect information such as:

* Job title
* Company
* Location
* Remote status
* Job URL
* Relevant keywords
* Recruiter / hiring manager information

---

### 4. Job Filtering

Not every remote job is actually accessible to every candidate.

LinkGPT applies filtering logic to identify relevant opportunities and remove location-restricted roles where appropriate.

For example, the system can identify restrictions such as:

```text
US Only
UK Only
EU Only
Citizenship Required
Residency Required
Location Restricted
```

The goal is to prioritize opportunities that can realistically be performed remotely from Pakistan.

---

### 5. Recruiter & Hiring Manager Research

For qualified opportunities, LinkGPT can search for relevant people such as:

* Recruiters
* Talent Acquisition Managers
* Hiring Managers
* Founders
* Relevant department leads

This creates a path from:

```text
Job Opportunity
      ↓
Relevant Contact
      ↓
Personalized Outreach
```

---

### 6. Structured Storage

Qualified opportunities are organized and stored in **Google Sheets**.

Example structure:

| Job Title              | Company   | Location  | Remote | Contact        | Job URL | Status    |
| ---------------------- | --------- | --------- | ------ | -------------- | ------- | --------- |
| AI Automation Engineer | Company A | Worldwide | Yes    | Recruiter      | URL     | Qualified |
| Automation Engineer    | Company B | Remote    | Yes    | Hiring Manager | URL     | Qualified |

This makes the results easier to review and manage.

---

### 7. Personalized Email Generation

Instead of sending generic messages, LinkGPT uses the available job and contact information to generate a personalized outreach email.

Example:

```text
Subject: AI Automation Engineer Opportunity

Hi [Recruiter Name],

I came across the AI Automation Engineer opportunity at [Company]
and noticed the role focuses on automation, AI agents, and workflow
optimization.

My experience with n8n, AI agents, APIs, and workflow automation
aligns closely with the requirements of the role.

I'd be happy to share more about my experience and discuss how
I could contribute to the team.

Best,
Ayesha
```

---

### 8. Human-in-the-Loop

One of the important design decisions in LinkGPT is **not automatically sending outreach emails**.

Instead:

```text
AI Generates Email
        ↓
Save as Draft
        ↓
Human Reviews
        ↓
Human Edits if Necessary
        ↓
Human Sends
```

This provides a final review step before external communication.

---

# 🖥️ Screenshots

## Project Overview

![LinkGPT Overview](screenshots/linkgpt-overview.png)

---

## n8n Workflow

![n8n Workflow](screenshots/n8n-workflow.png)

The workflow connects the different stages of the LinkGPT pipeline and orchestrates the automation.

---

## User Input

![User Input](screenshots/user-input.png)

The user can provide their job-search requirements through a natural-language message.

---

## AI Search Query Generation

![Search Query Generation](screenshots/search-query-generation.png)

The AI converts the user's requirements into targeted search queries and structured parameters.

---

## Qualified Job Results

![Job Results](screenshots/job-results.png)

Qualified opportunities are organized and stored for further review.

---

## Recruiter / Hiring Manager Search

![Recruiter Search](screenshots/recruiter-search.png)

The workflow searches for relevant recruiters and hiring managers associated with target opportunities.

---

## Personalized Email Draft

![Email Draft](screenshots/email-draft.png)

LinkGPT generates personalized outreach and saves it as a **draft**, allowing the user to review it before sending.

---

# 🛠️ Tech Stack

| Technology        | Purpose                                                                     |
| ----------------- | --------------------------------------------------------------------------- |
| **n8n**           | Workflow orchestration and automation                                       |
| **LLMs**          | Requirement understanding, query generation, filtering and email generation |
| **JavaScript**    | Data transformation and workflow logic                                      |
| **REST APIs**     | Connecting external services                                                |
| **Webhooks**      | Receiving user requests and triggering workflows                            |
| **SERP API**      | Search and information discovery                                            |
| **Google Sheets** | Structured storage of job opportunities                                     |
| **Gmail**         | Creating personalized email drafts                                          |

---

# 🔑 Key Features

### Natural Language Input

Users can describe what they are looking for instead of manually configuring search parameters.

### AI-Powered Search

LLMs generate targeted search queries based on the user's requirements.

### Remote Job Filtering

The system prioritizes remote opportunities and filters location-restricted roles.

### Recruiter Discovery

Relevant recruiters and hiring managers can be identified for qualified opportunities.

### Structured Data

Job information is automatically organized into a structured format.

### Personalized Outreach

AI generates personalized email drafts based on the opportunity and available contact information.

### Human Review

Emails are saved as drafts instead of being automatically sent.

---

# 📂 Repository Structure

```text
LinkGPT/
│
├── README.md
│
├── architecture/
│   └── system-architecture.png
│
├── screenshots/
│   ├── linkgpt-overview.png
│   ├── n8n-workflow.png
│   ├── user-input.png
│   ├── search-query-generation.png
│   ├── job-results.png
│   ├── recruiter-search.png
│   └── email-draft.png
│
├── n8n/
│   └── linkgpt-workflow.json
│
├── prompts/
│   ├── search-agent.md
│   ├── job-filtering.md
│   └── email-generation.md
│
├── docs/
│   ├── architecture.md
│   ├── setup.md
│   └── evaluation.md
│
└── LICENSE
```

---

# ⚙️ How It Works

At a high level, the workflow follows this process:

```text
1. User sends job requirements
              ↓
2. AI analyzes the request
              ↓
3. Search parameters are generated
              ↓
4. Search APIs discover opportunities
              ↓
5. Results are processed
              ↓
6. Jobs are filtered and qualified
              ↓
7. Relevant contacts are researched
              ↓
8. Qualified opportunities are stored
              ↓
9. AI generates personalized outreach
              ↓
10. Email is saved as a draft
              ↓
11. Human reviews and sends
```

---

# 🔧 Setup

## Prerequisites

Before running the workflow, you will need:

* n8n
* An LLM/API provider
* SERP API access
* Google account
* Google Sheets
* Gmail API access

---

## Import the n8n Workflow

1. Open your n8n instance.
2. Import the workflow from:

```text
n8n/linkgpt-workflow.json
```

3. Configure the required credentials.
4. Add your API credentials.
5. Configure Google Sheets.
6. Configure Gmail.
7. Test the workflow with a sample request.

> **Important:** Never commit API keys, OAuth credentials, tokens, passwords, or other secrets to this repository.

---

# 🔐 Environment & Credentials

The workflow requires external credentials.

For security reasons, credentials are **not included in this repository**.

Configure your own credentials inside n8n for:

```text
LLM Provider
SERP API
Google Sheets
Gmail
```

---

# 📊 Example Use Case

### User Request

```text
Find junior remote AI Automation Engineer roles
that I can work from Pakistan.

Focus on:
- n8n
- AI agents
- APIs
- JavaScript

Also find recruiters or hiring managers
and prepare an email draft for relevant opportunities.
```

### LinkGPT Output

```text
Search Requirements
        ↓
Targeted Search
        ↓
Relevant Jobs
        ↓
Location Filtering
        ↓
Recruiter Discovery
        ↓
Google Sheets
        ↓
Personalized Email Draft
```

The user can then review the generated opportunities and email drafts before taking action.

---

# 🚧 Current Limitations

LinkGPT is an evolving project and currently has limitations.

Some job listings may contain incomplete or outdated information.

Search engines and external APIs may return duplicate, incomplete, or inconsistent results.

AI-generated classifications and email content should be reviewed before being used.

The workflow currently focuses on automation and organization rather than fully autonomous job applications.

---

# 🔮 Future Improvements

Potential improvements include:

* Automated job deduplication
* Better job relevance scoring
* More robust location verification
* Job description parsing
* Resume-to-job matching
* Automated application tracking
* Agent evaluation and testing
* Better failure handling and retries
* Production deployment
* Monitoring and logging
* Multi-platform job discovery
* Improved recruiter matching
* Follow-up email workflows

---

# 📚 What I Learned

Building LinkGPT gave me hands-on experience with:

* AI agent workflows
* LLM-based decision making
* n8n workflow automation
* REST APIs
* Webhooks
* JavaScript data processing
* Search API integration
* Structured data pipelines
* Human-in-the-loop automation
* AI-generated personalized outreach
* Building multi-step automation systems

The project also helped me understand that building an AI agent is more than simply connecting an LLM to a workflow.

The surrounding system — **input handling, data processing, filtering, validation, storage, and human review** — is equally important.

---

# 📌 Project Status

**Status: 🚧 Active Development**

LinkGPT is continuously being improved as I experiment with better search strategies, filtering logic, AI workflows, and production-ready automation.

---

# 👩‍💻 Author

**Ayesha Jalil**

AI Automation Engineer | n8n | AI Agents | LLMs | Workflow Automation

---

## ⭐ If you found this project interesting

Feel free to explore the workflow, architecture, and implementation details.

If you're interested in AI automation, agentic workflows, or n8n, feel free to connect.
