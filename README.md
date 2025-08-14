# 🕵 Digital Skeptic – Critical Thinking AI Tool

A Python-based tool that fetches an online news article and uses **Groq's LLM API** to produce a **rich, nuanced critical analysis report** in Markdown.  
The analysis highlights potential bias, identifies missing context, and generates sharp verification questions — helping readers think more critically.

---

## 📌 Features
- **Automated Article Extraction**  
  Uses [Newspaper3k](https://github.com/codelucas/newspaper) for robust parsing, with a fallback to **BeautifulSoup** if extraction fails.
- **Nuanced AI Analysis**  
  Powered by **Groq's LLaMA 3 70B** model for deep, structured critique.
- **Bias & Red Flag Detection**  
  Identifies tone, loaded language, missing counterpoints, and possible logical fallacies.
- **Verification Roadmap**  
  Suggests questions and key entities for further research.
- **Opposing Viewpoint Simulation**  
  Presents a counter-perspective to challenge the article’s stance.

---

## 🚀 How to Test the Application (Google Colab or Local)

### **1. Clone the Repository**
```bash
git clone https://github.com/yourusername/digital-skeptic.git
cd digital-skeptic
```

### **2. Install Dependencies**
Make sure Python 3.8+ is installed. Then install:
```bash
pip install -r requirements.txt
```

**Example `requirements.txt`:**
```
requests
beautifulsoup4
python-dotenv
newspaper3k
groq
```

### **3. Set Up Your API Key**
The application requires a **Groq API key**.

- Sign up for Groq Cloud: [https://groq.com](https://groq.com)
- Get your API key from your Groq dashboard.
- Create a `.env` file in the project root:
```
GROQ_API_KEY=your_api_key_here
```

### **4. Run the Script**
In **Google Colab**:
```python
!pip install requests beautifulsoup4 python-dotenv newspaper3k groq
!python digital_skeptic.py
```

Locally:
```bash
python digital_skeptic.py
```

---

## 🧠 Approach
1. **Article Retrieval & Cleaning**
   - First attempts with **Newspaper3k** for structured extraction (title, clean text).
   - If that fails, falls back to **BeautifulSoup** parsing of `<p>` tags.

2. **Critical Thinking Prompt**
   - Sends the cleaned article text along with a **custom structured prompt** to Groq’s LLaMA 3 model.
   - The prompt enforces a **6-section Markdown analysis**:
     1. Core Claims  
     2. Language & Tone Analysis  
     3. Potential Red Flags  
     4. Verification Questions  
     5. Key Entities for Research  
     6. Simulated Opposing Viewpoint  

3. **Low Temperature (0.2)**
   - Ensures reproducibility and reduces creative hallucinations.

4. **Markdown Output**
   - Outputs neatly structured text for easy reading and sharing.

---

## 🔑 API Key Details
- **Service**: [Groq API](https://groq.com) – for running the LLaMA 3 70B model.
- **Environment Variable**: `GROQ_API_KEY`
- **Storage**: Never hardcode the API key in your script. Store it in a `.env` file or set it as a secure environment variable.
- **Rate Limits**: Check Groq’s pricing & rate-limit policies before running bulk analyses.

---

## 📄 Example Output
Once run, you’ll receive a **Critical Analysis Report** like:

```
# Critical Analysis Report for: Example Article Title

## 1. Core Claims
- Claim 1...
- Claim 2...
...

## 2. Language & Tone Analysis
- Tone is moderately persuasive...
...

## 3. Potential Red Flags
- Relies solely on anonymous sources...
...

## 4. Verification Questions
- What independent evidence supports...?
...

## 5. Key Entities for Further Research
- Organization X – research funding sources
...

## 6. Simulated Opposing Viewpoint
- An alternative perspective could argue...
```

