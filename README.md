### 📺 Full Video Walkthrough & Setup Guide
**Watch the full demo and setup guide on YouTube:** **[Youtube Video](https://www.youtube.com/watch?v=r9WMbzfY-mg&t=)**
Chat interface example: https://articollov2.vercel.app

This repository contains the complete workflow for **Keywordo-kun**, an AI agent specialized in competitor analysis, keyword research, and automated SEO content creation.
![Keywordo-kun Hero Image](Keywordo-kun%20image.png)
It's built for marketers, agencies, and SEO professionals who want to automate their research and writing process. The agent uses a powerful stack to analyze competitors, identify keyword opportunities, and generate high-quality, long-form blog posts.

## 🤖 How It Works: The Tool Stack

This project is built on **n8n** and **v0.dev**, connecting several key AI and data services:

* **n8n:** The central automation platform that runs the entire backend logic and agent "brain."
* **v0.dev:** Provides the sleek, conversational chat interface for the frontend.
* **Google Gemini (2.5 Pro & Flash):** Powers the agent's core reasoning, analysis, and content generation.
* **DataForSEO:** Provides the critical, real-time SERP data, keyword ideas, and competitor metrics.
* **Firecrawl:** Used to scrape and crawl websites for content analysis.

## 📂 What's Included in This Repository

This repository gives you all the components you need to deploy Keywordo-kun:

1.  **`Keywordo-kun (Articollo Agent).json`**: The main n8n workflow. This is the "brain" of the agent that handles the user chat, processes requests, and calls the necessary tools.
2.  **`Keywordo-kun (Tools).json`**: The secondary n8n workflow. This file contains all the individual tools (e.g., "Get Keyword Ideas," "Analyze SERP") that the main agent calls upon.
3.  **`Keywordo-kun Chat Interface (v0.dev).zip`**: The complete frontend UI. You can import this zip file directly into v0.dev to deploy the chat interface.
4.  **`Keywordo-kun image.png`**: The project's hero image.

## 🚀 How to Set Up (Prerequisites)

To get this workflow running, you will need accounts and API keys for the following services:

* An **n8n** account (Cloud or self-hosted).
* A **v0.dev** account to host the chat interface.
* A **Google AI Studio** API key for **Gemini**.
* A **DataForSEO** account and API credentials.
* A **Firecrawl** API key.

### 🏁 Quick Setup Guide

1.  **Deploy n8n Workflows:**
    * Create a new, empty workflow in n8n and import the `Keywordo-kun (Tools).json` file.
    * Create a second workflow and import the `Keywordo-kun (Articollo Agent).json` file.
2.  **Configure Tools Workflow:**
    * Open the "Tools" workflow and configure each HTTP Request node with your **DataForSEO** API credentials, as shown in the [video guide]([https://www.youtube.com/watch?v=r9WMbzfY-mg&t]).
    * Configure the Firecrawl node with your **Firecrawl** API key.
    * Save and activate this workflow.
3.  **Configure Agent Workflow:**
    * Open the "Agent" workflow.
    * Connect the **Gemini** nodes with your Google AI Studio API key.
    * In the "Agent" node, connect the tools to the "Tools" workflow you just deployed (by copying its production URL).
4.  **Deploy Frontend:**
    * Go to v0.dev and import the `Keywordo-kun Chat Interface (v0.dev).zip` file.
    * Get the **production webhook URL** from your "Agent" n8n workflow.
    * In the v0.dev chat prompt, ask it to replace the old webhook URL with your new one, as shown in the [video guide]([https://www.youtube.com/watch?v=r9WMbzfY-mg&t]).
5.  **Activate & Test:**
    * Activate your "Agent" n8n workflow.
    * Start chatting with your agent in the v0.dev interface!
