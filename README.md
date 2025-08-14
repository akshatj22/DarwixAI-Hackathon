# Digital Skeptic - Critical Thinking AI Tool (Groq Version)

## Overview
A Python tool that fetches a news article from a URL and uses Groq’s LLM to produce a **Markdown Critical Analysis Report**.  
The report covers: Core Claims, Language & Tone, Potential Red Flags, Verification Questions, Key Entities, and an Opposing Viewpoint.

## Requirements
- Python 3.8+
- Groq API key
- Internet connection

## Installation

`pip install python-dotenv newspaper3k lxml requests groq beautifulsoup4`


## Setup
Set your Groq API key:
export GROQ_API_KEY="your_key" # Linux/macOS
setx GROQ_API_KEY "your_key" # Windows

Or create a `.env` file:

GROQ_API_KEY=your_key

## Usage
Edit the `url` variable in `main()`:
url = "https://example.com/article"

Run:
`python digital_skeptic_groq.py`


The Markdown report will print in the console.

## Approach
- **Extract** article text via Newspaper3k, fallback to BeautifulSoup.
- **Analyze** using Groq’s `llama3-70b-8192` with a refined prompt for bias, tone, and verification questions.
- **Output** in Markdown format.

## API Key
- Required: `GROQ_API_KEY`
- Loaded from env or `.env` file.
- Keep it private.
