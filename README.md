<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0F2027,50:203A43,100:2C5364&height=190&section=header&text=Abhishek%20Tripathi&fontSize=40&fontColor=ffffff&animation=fadeIn&fontAlignY=34&desc=i%20write%20code%20%F0%9F%A6%9D&descSize=20&descAlignY=56" alt="Abhishek Tripathi - i write code" />

<a href="https://about---abhishek.vercel.app/"><img src="https://img.shields.io/badge/portfolio-000000?style=for-the-badge&logo=vercel&logoColor=white" alt="Portfolio" /></a>
<a href="https://www.linkedin.com/in/abhishek-tripathi-a714ab30b/"><img src="https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>
<a href="https://x.com/Abhishek706577"><img src="https://img.shields.io/badge/x-000000?style=for-the-badge&logo=x&logoColor=white" alt="X" /></a>
<a href="mailto:abhishektripathi317123@gmail.com"><img src="https://img.shields.io/badge/mail-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" /></a>
<img src="https://komarev.com/ghpvc/?username=Abhishekhack2909&style=for-the-badge&color=2C5364&label=VISITORS" alt="Profile visitor count" />

<br/><br/>

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=500&size=20&duration=3400&pause=1000&color=36BCF7&center=true&vCenter=true&width=720&lines=teaching+machines+to+admit+when+they+don't+know;retrieval+%3E+hallucination;if+it+isn't+traced%2C+it+isn't+shipped;i+dig+through+data+like+it's+a+dumpster+%F0%9F%A6%9D" alt="teaching machines to admit when they don't know; retrieval over hallucination; if it isn't traced it isn't shipped" />

</div>

---

<img align="right" width="320" src="https://media4.giphy.com/media/v1.Y2lkPTc5MGI3NjExM3E0aHB2ajRhd3RhcGw5bDBidWc3aWRwdWlrYnZmZnV5d20zcHcyNiZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/QXwtfadqo7wbfmT46H/giphy.gif" alt="pixel art animation" />

```console
$ whoami
Abhishek Tripathi — Kanpur, India. raccoon-adjacent.

$ cat ~/.obsessions
agents that know when they're wrong
retrieval that cites its sources
traces you can actually read at 3am

$ which languages
/usr/bin/python
/usr/bin/typescript
/usr/bin/c++

$ uptime
awake,mostly. shipping since 2024.

$ echo $PHILOSOPHY
an answer without a source is a rumour
guardrails are cheaper than apologies
```

<br clear="right"/>

---

## what happens when you ask my systems a question

```mermaid
flowchart LR
    Q(["🗣️ question"]) --> ROUTE{{"route"}}

    ROUTE --> RET["retrieve"]

    subgraph HYBRID ["hybrid search"]
        direction TB
        CH[("chromadb<br/>vectors")]
        BM[("bm25<br/>keywords")]
    end

    RET --> CH
    RET --> BM
    CH --> RR["rerank"]
    BM --> RR

    RR --> GEN["generate"]
    GEN --> CHK{"grounded?"}

    CHK -->|"no — go dig-again"| RET
    CHK -->|"yes"| OUT(["✅ answer + citations"])

    classDef q fill:#36BCF7,stroke:#0F2027,color:#0F2027,font-weight:bold
    classDef work fill:#203A43,stroke:#36BCF7,color:#ffffff
    classDef store fill:#2C5364,stroke:#36BCF7,color:#ffffff
    classDef gate fill:#6E44FF,stroke:#ffffff,color:#ffffff
    classDef good fill:#2C7A7B,stroke:#ffffff,color:#ffffff

    class Q q
    class RET,RR,GEN work
    class CH,BM store
    class ROUTE,CHK gate
    class OUT good
```

The interesting arrow is the one going backwards. A system that can't tell it failed to ground an
answer will happily invent one instead.

---

## and This is what it looks like from the inside

```
trace  a9f2c1   "why was my invoice charged twice?"            1,284 ms
│
├─ router.classify ................ ▇▇ 41 ms          → billing
├─ retrieve.hybrid ............... ▇▇▇▇▇▇ 210 ms
│  ├─ chroma.vector_search ....... ▇▇▇▇ 148 ms        k=12
│  └─ bm25.keyword ............... ▇ 34 ms            k=12
├─ rerank.cross_encoder .......... ▇▇▇ 96 ms          12 → 4 chunks
├─ llm.generate .................. ▇▇▇▇▇▇▇▇ 612 ms    groq · 284 tok
├─ guardrail.groundedness ........ ▇▇ 78 ms           ✓ 4/4 cited
└─ guardrail.pii_scrub ........... ▇ 22 ms            ✓ clean
                                                      ──────────────
                                                      0 retries · ok
```

If you can't produce this for an LLM feature, you don't have a feature. You have a slot machine.

---

## the stack

<details open>
<summary><b>🤖 &nbsp;the part that thinks</b></summary>
<br/>
<p>
<img src="https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square&logo=langchain&logoColor=white" alt="LangChain" />
<img src="https://img.shields.io/badge/LangGraph-1C3C3C?style=flat-square&logo=langchain&logoColor=white" alt="LangGraph" />
<img src="https://img.shields.io/badge/Agentic_AI-6E44FF?style=flat-square" alt="Agentic AI" />
<img src="https://img.shields.io/badge/RAG_Pipelines-4B8BBE?style=flat-square" alt="RAG Pipelines" />
<img src="https://img.shields.io/badge/Guardrails-2C7A7B?style=flat-square" alt="Guardrails" />
<img src="https://img.shields.io/badge/Prompt_Engineering-8E44AD?style=flat-square" alt="Prompt Engineering" />
</p>
<p>
<img src="https://img.shields.io/badge/OpenAI-412991?style=flat-square&logo=openai&logoColor=white" alt="OpenAI" />
<img src="https://img.shields.io/badge/Claude-D97757?style=flat-square&logo=anthropic&logoColor=white" alt="Claude" />
<img src="https://img.shields.io/badge/Gemini-8E75B2?style=flat-square&logo=googlegemini&logoColor=white" alt="Gemini" />
<img src="https://img.shields.io/badge/Groq_LPU-F55036?style=flat-square" alt="Groq LPU" />
<img src="https://img.shields.io/badge/HuggingFace-FFD21E?style=flat-square&logo=huggingface&logoColor=black" alt="Hugging Face" />
<img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white" alt="PyTorch" />
</p>
</details>

<details open>
<summary><b>🔍 &nbsp;the part that remembers</b></summary>
<br/>
<p>
<img src="https://img.shields.io/badge/ChromaDB-FF6F61?style=flat-square" alt="ChromaDB" />
<img src="https://img.shields.io/badge/FAISS-0467DF?style=flat-square&logo=meta&logoColor=white" alt="FAISS" />
<img src="https://img.shields.io/badge/BM25-5A67D8?style=flat-square" alt="BM25" />
<img src="https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white" alt="MongoDB" />
<img src="https://img.shields.io/badge/Postgres-4169E1?style=flat-square&logo=postgresql&logoColor=white" alt="PostgreSQL" />
<img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white" alt="Redis" />
<img src="https://img.shields.io/badge/Supabase-3ECF8E?style=flat-square&logo=supabase&logoColor=white" alt="Supabase" />
</p>
</details>

<details open>
<summary><b>📡 &nbsp;the part that watches</b></summary>
<br/>
<p>
<img src="https://img.shields.io/badge/Logfire-E52E7A?style=flat-square&logo=pydantic&logoColor=white" alt="Logfire" />
<img src="https://img.shields.io/badge/LangSmith-1C3C3C?style=flat-square&logo=langchain&logoColor=white" alt="LangSmith" />
<img src="https://img.shields.io/badge/OpenTelemetry-425CC7?style=flat-square&logo=opentelemetry&logoColor=white" alt="OpenTelemetry" />
</p>
</details>

<details>
<summary><b>🧱 &nbsp;the part users actually touch</b></summary>
<br/>
<p>
<img src="https://img.shields.io/badge/Python-3670A0?style=flat-square&logo=python&logoColor=white" alt="Python" />
<img src="https://img.shields.io/badge/TypeScript-007ACC?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript" />
<img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black" alt="JavaScript" />
<img src="https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white" alt="C++" />
<img src="https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white" alt="Java" />
</p>
<p>
<img src="https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB" alt="React" />
<img src="https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white" alt="Next.js" />
<img src="https://img.shields.io/badge/Tailwind-38B2AC?style=flat-square&logo=tailwindcss&logoColor=white" alt="Tailwind CSS" />
<img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white" alt="FastAPI" />
<img src="https://img.shields.io/badge/Node.js-6DA55F?style=flat-square&logo=nodedotjs&logoColor=white" alt="Node.js" />
<img src="https://img.shields.io/badge/Express-000000?style=flat-square&logo=express&logoColor=white" alt="Express" />
<img src="https://img.shields.io/badge/WebSockets-010101?style=flat-square&logo=socketdotio&logoColor=white" alt="WebSockets" />
<img src="https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white" alt="Streamlit" />
</p>
<p>
<img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" alt="Docker" />
<img src="https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white" alt="AWS" />
<img src="https://img.shields.io/badge/Vercel-000000?style=flat-square&logo=vercel&logoColor=white" alt="Vercel" />
<img src="https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white" alt="Git" />
</p>
</details>

---

## currently poking at

<table>
<tr>
<td width="33%" valign="top" align="center">
<h3>🎙️</h3>
<b>voice RAG in hindi</b>
<br/><br/>
<sub>speech in, grounded speech out. the hard part was never the audio — it's proving the claim before you say it out loud.</sub>
</td>
<td width="33%" valign="top" align="center">
<h3>🕸️</h3>
<b>multi-agent handoffs</b>
<br/><br/>
<sub>triage → specialist → escalation. every hop traced, because "the agent decided something" is not a debug log.</sub>
</td>
<td width="33%" valign="top" align="center">
<h3>⚡</h3>
<b>sub-second inference</b>
<br/><br/>
<sub>LLM calls sitting in the render path. if the user notices the model thinking, i've already lost.</sub>
</td>
</tr>
</table>

---

## things i'll argue about

> **"just fine-tune it"**
> usually no. most of the time your retrieval is bad, not your weights.

> **"the demo works"**
> a demo is one lucky path through a system with no error handling.

> **"we'll add logging later"**
> for anything non-deterministic, tracing *is* the feature. bolt it on afterwards and you're guessing.

> **"the model hallucinated"**
> the model did exactly what it was built to do. you shipped it without a verifier.

---

## the contribution dumpster 🦝

<div align="center">

<img src="https://github-readme-stats.vercel.app/api?username=Abhishekhack2909&show_icons=true&include_all_commits=true&count_private=true&hide_border=true&theme=tokyonight&hide_title=true&card_width=450" alt="Abhishek's GitHub statistics: commits, pull requests, issues and stars" />

<br/>

<img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Abhishekhack2909&layout=compact&langs_count=8&hide_border=true&theme=tokyonight" alt="Most used programming languages" />
<img height="165" src="https://github-profile-summary-cards.vercel.app/api/cards/most-commit-language?username=Abhishekhack2909&theme=tokyonight" alt="Languages ranked by commit count" />

<br/><br/>

<img src="https://streak-stats.demolab.com?user=Abhishekhack2909&hide_border=true&theme=tokyonight&date_format=j%20M%5B%20Y%5D" alt="Contribution streak: current and longest" />

<br/><br/>

<img src="https://github-readme-activity-graph.vercel.app/graph?username=Abhishekhack2909&theme=tokyo-night&hide_border=true&area=true&custom_title=where%20the%20commits%20go" alt="Daily contribution activity over the last month" />

<br/>

<img src="https://github-profile-trophy.vercel.app/?username=Abhishekhack2909&theme=tokyonight&no-frame=true&no-bg=true&column=7&margin-w=8&margin-h=8" alt="GitHub achievement trophies" />

</div>

---

<div align="center">

<em>my inbox is open. so is the dumpster.</em>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:2C5364,50:203A43,100:0F2027&height=110&section=footer" alt="" />

</div>
