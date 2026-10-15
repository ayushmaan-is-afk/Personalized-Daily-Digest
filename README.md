# Personalized-Daily-Digest

An automated research and content-curation agent built with **Activepieces** that discovers your newsletter subscriptions, analyzes their content, learns your interests, and delivers a personalized intelligence digest every day at **7:00 AM**.

## Overview

Staying updated on fields like artificial intelligence, cybersecurity, software engineering, and emerging technologies often means dealing with dozens of newsletters and multiple information sources. Most newsletters contain a mixture of relevant and irrelevant content, making it difficult to find the information that actually matters.

The Personalized Daily Intelligence Digest Agent solves this by identifying the newsletters you receive, analyzing their content and associated websites, and using your preferences to curate a focused daily digest.

During initialization, the agent discovers your existing information sources, proposes interests based on their content, and asks you to confirm or refine those interests through Slack. Once initialized, it searches additional sources such as Hacker News and other configured technology publications to deliver a personalized digest every morning.

## Key Features

- **Manual Initialization:** Starts with a manual trigger to configure the agent and connect the user's Gmail account.
- **Newsletter Discovery:** Identifies newsletters arriving in the user's Gmail inbox.
- **Website and Content Indexing:** Analyzes newsletter content and associated websites to identify recurring topics, categories, and relevant information.
- **Automatic Interest Discovery:** Infers potential interests from the newsletters the user already receives.
- **Slack-Based Confirmation:** Sends a confirmation message summarizing the inferred preferences and requests user approval.
- **Preference Management:** Allows users to edit existing interests and add new topics.
- **Fallback Notifications:** Sends a Slack notification when the agent cannot identify relevant interests or find suitable content during initialization.
- **Multi-Source Research:** Retrieves relevant content from sources such as Hacker News, alongside other configured websites and publications.
- **Personalized Daily Digest:** Filters and organizes relevant findings into a digest delivered daily at 7:00 AM.
- **Adaptive Configuration:** Uses the user's confirmed preferences to guide subsequent content discovery and filtering.

## How It Works

### 1. Manual Initialization

The workflow begins when the user manually triggers initialization.

The user provides their Gmail account details and authorizes the necessary access. The agent then begins discovering the newsletters and information sources available through that account.

### 2. Newsletter Discovery

The agent examines incoming email content to identify newsletters and recurring publications.

It extracts available information such as:

- Newsletter and publication names
- Article titles and links
- Topics and keywords
- Associated websites
- Content summaries and relevant text

The extracted information provides the foundation for discovering the user's interests.

### 3. Website and Content Analysis

The agent analyzes newsletter content and indexes relevant website information to identify the subjects covered by the user's subscriptions.

For example, if several newsletters regularly discuss large language models, AI agents, vulnerability research, and threat intelligence, the agent may infer that the user is interested in AI and cybersecurity.

These inferred interests are suggestions rather than permanent assumptions.

### 4. Slack Confirmation

After analyzing the available information, the agent sends a confirmation message through Slack.

The message presents the interests it has inferred and asks the user to confirm or modify them.

If the agent cannot identify meaningful interests or find sufficient information, it sends a separate notification explaining that it needs additional input.

### 5. Preference Configuration

The user can refine the proposed interests by editing existing preferences or adding new ones.

Example preferences:

- Artificial intelligence and LLMs
- AI agents and automation
- Cybersecurity and vulnerability research
- Open-source projects
- Developer tools and software engineering
- Startup funding and emerging technologies

The confirmed preferences determine which topics the agent prioritizes during future content discovery.

### 6. Multi-Source Content Discovery

The agent searches configured websites and publications for material relevant to the user's preferences.

Sources can include:

- [Hacker News](https://news.ycombinator.com/)
- [TechCrunch](https://techcrunch.com/)
- [The Verge](https://www.theverge.com/)
- Relevant newsletters and their associated websites
- Additional configured publications and research sources

The source list can be expanded as the workflow evolves.

### 7. Relevance Filtering and Digest Generation

The agent evaluates discovered content against the user's confirmed interests, filters out less relevant material, and organizes the remaining findings into a readable digest.

A digest entry can include:

- Article or story title
- Source publication
- Short summary
- Original article link
- Relevant topic or category

The objective is to provide useful information without requiring the user to manually browse every newsletter and publication.

### 8. Daily Delivery at 7:00 AM

Once initialized, the workflow runs on a daily schedule and delivers the personalized digest at **7:00 AM**, using the configured timezone.

The user receives a consolidated briefing of relevant developments from their selected topics and configured sources.

## Technology Stack

| Component | Purpose |
|---|---|
| Activepieces | Workflow orchestration, triggers, and scheduling |
| Gmail | Newsletter discovery and email-content retrieval |
| Website scraping / browsing tools | Retrieve relevant website and article content |
| AI / LLM integration | Content analysis, interest inference, relevance filtering, and summarization |
| Slack | Preference confirmation, updates, and fallback notifications |
| Scheduled trigger | Daily digest delivery at 7:00 AM |

## Example Use Case

A developer subscribes to multiple newsletters covering AI, cybersecurity, and developer tooling.

During initialization, the agent discovers these subscriptions and proposes AI and cybersecurity as primary interests. The user confirms these topics and adds AI agents as another preference.

Each morning, the agent searches its configured sources, identifies relevant stories, filters out unrelated content, and delivers a consolidated briefing at 7:00 AM.

Instead of opening multiple newsletters and websites, the user gets a single, preference-driven starting point for the day.

## Expected Benefits

- **Reduced information overload:** Consolidates relevant information from multiple sources.
- **Personalized research:** Tailors content discovery to individual interests.
- **Automated onboarding:** Infers initial preferences from existing newsletter subscriptions.
- **Flexible configuration:** Allows interests to evolve as the user's needs change.
- **Broader coverage:** Supplements existing newsletters with stories from other configured sources.
- **Consistent delivery:** Provides a daily briefing at a predictable time.

## Design Philosophy

The agent follows a simple principle: **discover what the user cares about, confirm it with the user, and continuously find useful information around those interests.**

Rather than delivering the same generic news roundup to everyone, it combines newsletter discovery, preference-based research, and automated summarization into a personalized daily intelligence workflow.

## REQUIREMENTS - 
1. Activepieces
2. OpenRouter API KEY
3. SLACK

## ARCHITECTURE

<img width="1328" height="5612" alt="Initilization" src="https://github.com/user-attachments/assets/46680edb-ba1a-4a7a-bd71-1fc6c13921d3" />
Initialization

<img width="1328" height="4172" alt="Daily Flow" src="https://github.com/user-attachments/assets/7c1f0904-9a78-4874-886c-30d588063954" />
Daily Flow
