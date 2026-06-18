🐕 Autonomous D2C Market Intelligence & Visual Hook Parser
self-hosted, event-driven data operations pipeline built to autonomously extract, normalize, and audit competitor marketing hooks and consumer personas from Premium D2C brand handles.

This repository hosts the interactive, live presentation deck showcasing the system architecture, token economics, and target data harvest schemas.

👉 Live Interactive Showcase Link (Replace with your actual GitHub Pages URL)

🛠️ System Architecture

The pipeline runs completely serverless, decoupled, and anti-fragile, hosted on Railway Cloud utilizing n8n.

[Trigger] ➔ [Google Sheet Config] ➔ [Apify Proxy Scraper] ➔ [JavaScript Normalization]
                                                                        │
[Google Sheet Database] 🗄️ 🅤🅟🅓🅐🅣🅔 🗂️ [Structured Output Parser] 🖎 [LLM Reasoning Layer]


Key Components

Orchestration Engine: Self-hosted n8n instance running on independent cloud infrastructure (Railway).

Decentralized Extraction: Apify Instagram Scraper routing requests through rotating residential proxies to safely bypass CDN session checkpoints without exposing brand accounts.

Data Transformation (Custom JS): Custom ES6+ JavaScript code blocks managing schema mapping, timezone normalization, and format balancing.

Cognitive Analysis: gpt-4o-mini analyzing dynamic image CDN links and corresponding captions in parallel.

Schema Governance: Strict JSON schema validation enforcing standardized output constraints (Persona Type, Hook Category, Quantitative Score, Qualitative Reasoning) for direct relational database ingestion.

⚡ Core Engineering Solutions

1. Bypassing Media Formatting Biases

Standard engagement-sorting formulas naturally favor video formats over static imagery due to raw view velocities. To eliminate this, a custom, weighted popularity index is run inside a decoupled JavaScript node to split, rank, and merge static carousel/sidecar ads with videos:

$$\text{Engagement Popularity Score} = \text{Views} + (\text{Likes} \times 5) + (\text{Comments} \times 20)$$

This balances the final audit portfolio 50/50, ensuring image ads get equal analytical attention.

2. High-Friction API Cost Controls

To avoid feeding raw, unfiltered scraped datasets directly to multi-modal vision models, an inline pre-filtering JavaScript layer narrows down $92$ raw ingested assets to the $19$ highest-signal competitive anomalies. This resulted in a $79\%$ reduction in OpenAI API token spend.

📁 Repository Structure

index.html — The interactive slide deck application representing the case study.

16c190a3-42ec-4ad3-9556-76c9c2a8e5a7.png — The verified production n8n execution canvas.

README.md — Project documentation.

🚀 Local Setup & Deployment

Clone this repository:

git clone https://github.com/biswanathkar-oss/competitor-intelligence-deck.git


Place your cropped n8n execution canvas screenshot in the root folder as 16c190a3-42ec-4ad3-9556-76c9c2a8e5a7.png.

Enable GitHub Pages under Settings > Pages in your repository to host the interactive showcase instantly for free!
