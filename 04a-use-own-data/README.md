\# Generative AI App Using Tools



\## Overview

This exercise builds a Python generative AI application using Microsoft Foundry and GPT-5.2.



The application can use two tools:

\- \*\*Web Search\*\* – searches the web for current travel information.

\- \*\*File Search\*\* – searches travel brochure PDFs stored in a vector store.



\## What I Built

\- Created a Microsoft Foundry project.

\- Deployed the GPT-5.2 model.

\- Connected the Python application to Microsoft Foundry.

\- Created a vector store.

\- Uploaded 6 travel brochure PDFs.

\- Used File Search to retrieve information from the brochures.

\- Used Web Search to retrieve current information from the internet.

\- Used `previous\_response\_id` to maintain conversation context.



\## RAG Flow



User Question  

↓  

GPT-5.2  

↓  

File Search / Web Search  

↓  

Vector Store / Internet  

↓  

Relevant Information  

↓  

Generated Answer



\## Testing



The application successfully answered questions such as:



\- "What's happening in San Francisco next month?"

\- "What hotels does Margie's Travel offer there?"



The first question demonstrated web search, while the follow-up demonstrated file search and conversation context.



\## Security

Environment variables are stored in a `.env` file. The `.env` file is excluded from Git using `.gitignore` so that configuration information is not pushed to GitHub.

