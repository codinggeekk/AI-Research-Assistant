![Uploading image.png…]()

 # AI-Research-Assistant
AI-Research-Assistant

AI-Research-Assistant is a Wikipedia-only multi-agent research tool available in two forms:

Python CLI version (main_wikipedia_only.py)

Interactive Browser GUI (gui.html) built entirely with HTML + CSS + JavaScript

Both versions use no machine learning models and no external APIs except Wikipedia's REST & Search endpoints.
The system generates research questions, fetches information from Wikipedia, and synthesizes a clean final report.

🌐 Live Technology Stack
Python CLI Version

Pure Python

Agents:

Planner Agent

Search Agent (Wikipedia summary + search fallback)

Synthesizer Agent

Libraries:

requests

re (text cleaning)

time

urllib.parse

Browser GUI Version (gui.html)

HTML5

CSS (glassmorphism + custom dark UI)

JavaScript ES6

Fetches Wikipedia directly using:

https://en.wikipedia.org/api/rest_v1/page/summary/...

https://en.wikipedia.org/w/api.php?action=query&list=search...

No backend is required — the GUI runs fully in the browser.

✨ Features
✔ Multi-Agent Pipeline

The system simulates a research-assistant workflow:

Planner Agent
Generates 3 automatic research questions:

Who is topic?

Important facts about topic?

Recent developments related to topic?

Search Agent
Uses:

Direct Wikipedia REST summaries

Search fallback using the MediaWiki API

Automatic sanitization of user input

Synthesizer Agent
Builds a clean, structured research report:

Introduction

Findings (summaries of each question)

Conclusion

📁 Project Structure
AI-Research-Assistant/
│
├── main_wikipedia_only.py       # Python CLI multi-agent assistant
├── gui.html                     # Fully functional HTML/CSS/JS GUI
├── README.md                    # This documentation
└── main.ipynb                   # Notebook version (optional)

🧠 Python Version (CLI)
Usage
python3 main_wikipedia_only.py


You will be prompted:

What topic would you like me to research today?


Then the system:

Generates research questions

Queries Wikipedia (summary → search fallback)

Produces a final compiled report

The terminal prints only the final report (no debug logs).

🌐 GUI Version (HTML/CSS/JS)
Opening the GUI

Just open:

gui.html


in any modern browser.
No installation needed.

GUI Features

✔ Search bar for topic
✔ Planner-generated questions
✔ Live log panel showing agent activity
✔ Synthesized final report
✔ Copy report to clipboard
✔ Download report as .txt
✔ Full dark-mode, glassy UI
✔ Responsive layout for desktops + mobile

🔧 Requirements
Python Version

Install dependencies:

pip install requests

Browser GUI

No dependencies. Works offline (except Wikipedia requests).

🏗 How It Works
1. Topic Sanitization

Removes padding text like:

“what is”

“tell me about”

“info on”

2. Planning

Creates 3 deterministic research questions.

3. Wikipedia Fetching

Attempts:

/page/summary/Topic_Name

Wikipedia Search API

Extracting summary or description

Includes a built-in 300ms politeness delay.

4. Report Synthesis

Cuts long answers to ~800 characters while respecting sentence boundaries.

🔒 Privacy

No data stored

No logging

No external services besides Wikipedia

All processing is local.

🚀 Future Improvements

Add multiple sources beyond Wikipedia

Add export to PDF/Markdown

Add agent customization (number of questions, domains)

Add local embeddings & offline mode

📝 License

You may include your preferred license here (MIT recommended).

