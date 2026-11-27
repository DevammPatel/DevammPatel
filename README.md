<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0F172A,100:0EA5E9&height=180&section=header&text=Devamm&fontSize=60&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=Turning%20raw%20data%20into%20decisions&descAlignY=58&descSize=18" width="100%"/>

<a href="https://git.io/typing-svg"><img src="https://readme-typing-svg.demolab.com/?font=Fira+Code&size=20&pause=1000&color=0EA5E9&center=true&vCenter=true&width=600&lines=MSc+AI+%40+University+of+Leeds;Microsoft+Certified+Fabric+Data+Engineer;Open+Source+Contributor+%40+Apache+Airflow%2C+dbt-duckdb+%26+OpenInference;Published+IEEE+Researcher;Building+Multi-Agent+AI+Systems;Data+Engineer+%7C+RAG+%7C+Azure+AI+Foundry" alt="Typing SVG" /></a>

</div>

---

### 📖 The Short Version

Most teams have data everywhere and insight nowhere: pipelines run, signals get buried, and nobody trusts the number on the dashboard. I build the systems that fix that, from real-time streaming pipelines and ETL that clean and structure raw data to multi-agent AI systems that reason over it.

I'm an **MSc Advanced Computer Science (Artificial Intelligence)** student at the **University of Leeds** and a B.Tech (ICT) graduate of DA-IICT. I have a published IEEE paper on federated learning, the **Microsoft Certified: Fabric Data Engineer Associate (DP-700)** certification, merged contributions to **[Apache Airflow](https://github.com/apache/airflow)**, **[dbt-duckdb](https://github.com/duckdb/dbt-duckdb)** and **[Arize OpenInference](https://github.com/Arize-ai/openinference)**, and hands-on work across streaming data platforms, RAG and agentic AI on Azure AI Foundry. Based in Leeds, UK, and open to Data Engineering, Data Analyst and Data Science / AI roles.

<br/>

### 🌍 Open Source

<table>
<tr>
<td width="140" align="center" valign="middle">

<a href="https://github.com/apache/airflow"><img src="https://github.com/apache.png" width="64" alt="Apache"/></a><br/>
<sub><b>apache/airflow</b></sub><br/>
<img src="https://img.shields.io/github/stars/apache/airflow?style=social" alt="stars"/>

</td>
<td valign="top">

**[Use the Trino connection schema for OpenLineage table names](https://github.com/apache/airflow/pull/77345)** &nbsp;![Merged](https://img.shields.io/badge/merged-Nov_2026-8957e5?style=flat-square&logo=github)

In the Airflow Trino provider, `TrinoHook` connects with the connection's schema as the session schema, but the schema it reported to OpenLineage was always `None`. So lineage for a query on an unqualified table, like `SELECT name FROM customer`, could list the same table from every schema in the catalog, including ones the query never read. If the metadata lookup failed, datasets were named `<catalog>.None.<table>`. I made the OpenLineage default schema follow the connection's schema, and added regression tests that fail without the fix. I found the bug by reading the provider code.

</td>
</tr>
<tr>
<td width="140" align="center" valign="middle">

<a href="https://github.com/duckdb/dbt-duckdb"><img src="https://github.com/duckdb.png" width="64" alt="DuckDB"/></a><br/>
<sub><b>duckdb/dbt-duckdb</b></sub><br/>
<img src="https://img.shields.io/github/stars/duckdb/dbt-duckdb?style=social" alt="stars"/>

</td>
<td valign="top">

**[Read Delta sources at as_of_version 0 instead of the latest version](https://github.com/duckdb/dbt-duckdb/pull/915)** &nbsp;![Merged](https://img.shields.io/badge/merged-Nov_2026-8957e5?style=flat-square&logo=github)

dbt-duckdb's Delta Lake plugin ignored `as_of_version: 0`: it checked the version with `if as_of_version:`, and since `0` is falsy, a source pinned to the table's first commit silently read the latest version instead. I changed the check to `is not None`, and brought back the repo's Delta time-travel test assertions, which had been commented out and were hiding the bug. The test now fails on `main` and passes with the fix.

</td>
</tr>
<tr>
<td width="140" align="center" valign="middle">

<a href="https://github.com/Arize-ai/openinference"><img src="https://github.com/Arize-ai.png" width="64" alt="Arize AI"/></a><br/>
<sub><b>Arize-ai/openinference</b></sub><br/>
<img src="https://img.shields.io/github/stars/Arize-ai/openinference?style=social" alt="stars"/>

</td>
<td valign="top">

**[fix(openai-agents): emit zero token counts on the chat completions path](https://github.com/Arize-ai/openinference/pull/4410)** &nbsp;![Merged](https://img.shields.io/badge/merged-Nov_2026-8957e5?style=flat-square&logo=github)

OpenInference is OpenTelemetry instrumentation for AI observability. In the OpenAI Agents SDK instrumentor, spans from the Chat Completions path (used for Gemini, Groq, OpenRouter, vLLM and LiteLLM) dropped every token count that was `0`. Spans from the Responses path kept them, so filtering on `cache_read = 0` in Phoenix missed all Chat Completions spans. I made the two paths behave the same way, kept the SDK's placeholder `Usage()` from writing made-up zeros (which would skew cost numbers), and added regression tests. Before/after traces were checked in Phoenix. Closes [#4185](https://github.com/Arize-ai/openinference/issues/4185).

</td>
</tr>
</table>

<br/>

### 🧭 Where I've Been Building

<table>
<tr>
<td width="50%" valign="top">

**🔐 IEEE Publication**
Secure Data Aggregation for Oilfield Transport & Inspection Vehicles using Onion-Routed Federated Learning. Presented at the 2026 IEEE TPEC in Texas, USA, and reached 99.88% global precision on the LR-HR DDoS 2024 dataset · [IEEE Xplore](https://ieeexplore.ieee.org/document/11513191)

</td>
<td width="50%" valign="top">

**🤖 [SkillForge AI](https://github.com/DevammPatel/skillforge-ai)**
A 5-agent enterprise certification readiness platform on Azure AI Foundry (Agents, AI Search, Azure OpenAI), built for Microsoft's Agents League Hackathon. Now building an MCP server to expose a SkillForge AI capability · [Live demo](https://skillforge-ai-egcwzshcnjb9uv2wvyspkh.streamlit.app/)

</td>
</tr>
<tr>
<td width="50%" valign="top">

**🔎 [Sentinel-RAG](https://github.com/DevammPatel/Sentinel-RAG)**
Cited answers over 37 official SEBI and RBI regulatory documents (1,606 passages). Hybrid BM25 + dense retrieval with cross-encoder reranking reaches **Hit@1 0.90 / Hit@5 1.00** on a 50-question golden set. Includes an agent loop that retries or refuses, guardrails, and OpenTelemetry tracing in Phoenix

</td>
<td width="50%" valign="top">

**📈 [CryptoStream](https://github.com/DevammPatel/CryptoStream)**
Binance WebSockets → Redpanda (Kafka) → Spark → Parquet lake → dbt + DuckDB → LightGBM price-direction model tracked in MLflow behind a promotion gate → FastAPI + live Streamlit dashboard. Orchestrated by Dagster, fully Dockerized, with CI

</td>
</tr>
<tr>
<td width="50%" valign="top">

**🌊 [Pulse: Real-Time Streaming Lakehouse](https://github.com/DevammPatel/Pulse)**
NSE/BSE market ticks → Kafka → Spark Structured Streaming → Delta Lake medallion (bronze/silver/gold) on S3-compatible storage at 10K+ events/sec. Airflow runs a Great Expectations quality gate and dbt marts on Trino, with Grafana/Superset dashboards on top

</td>
<td width="50%" valign="top">

**🏛️ [National Digital Economy Intelligence Warehouse](https://github.com/DevammPatel/Project-DigiDist)**
PostgreSQL star schema over 722 districts, with Python ETL (alias + fuzzy district matching) and a District Prosperity Index computed with SQL window functions · [Live dashboard](https://devammpatel.github.io/Project-DigiDist/)

</td>
</tr>
</table>

<br/>

### 🏅 Certifications

- **Microsoft Certified: Fabric Data Engineer Associate (DP-700)**, October 2026
- **Google Gen AI Academy**: completed the ADK Challenge Lab (structured-output agents and sequential multi-agent pipelines)

<br/>

### 💼 Experience

- **Data Scientist Intern, Sridix Technology** (Jan – May 2026): automated Python preprocessing over 50,000+ records (18% fewer missing/inconsistent entries), built 10+ stakeholder dashboards (15% less reporting time) and delivered a 22% accuracy gain over baseline in predictive models
- **Data Analyst Intern, Lambdafy Data Solutions** (May – Jul 2025): analyzed 30,000+ rows of logistics data to uncover delivery delay patterns, supporting a 12% cut in average fulfillment time, and built 8 Python/Excel KPI dashboards
- **Deputy Convener, Synapse** (Gujarat's largest techno-cultural fest): led the largest mega-show in its history (12,000+ attendees) with an INR 14M budget and INR 5M in sponsorships

<br/>

### ⚡ Stack I Reach For

<div align="center">

**Languages**<br/>
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=for-the-badge)
![C](https://img.shields.io/badge/C-00599C?style=for-the-badge&logo=c&logoColor=white)
![C++](https://img.shields.io/badge/C%2B%2B-00599C?style=for-the-badge&logo=cplusplus&logoColor=white)

**Data Engineering**<br/>
![Apache Kafka](https://img.shields.io/badge/Apache_Kafka-231F20?style=for-the-badge&logo=apachekafka&logoColor=white)
![Apache Spark](https://img.shields.io/badge/Apache_Spark-E25A1C?style=for-the-badge&logo=apachespark&logoColor=white)
![Apache Airflow](https://img.shields.io/badge/Airflow-017CEE?style=for-the-badge&logo=apacheairflow&logoColor=white)
![Dagster](https://img.shields.io/badge/Dagster-4F43DD?style=for-the-badge)
![dbt](https://img.shields.io/badge/dbt-FF694B?style=for-the-badge)
![Delta Lake](https://img.shields.io/badge/Delta_Lake-00ADD4?style=for-the-badge)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)

**Cloud & Platforms**<br/>
![Azure](https://img.shields.io/badge/Azure_AI_Foundry-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white)
![Microsoft Fabric](https://img.shields.io/badge/Microsoft_Fabric-117865?style=for-the-badge)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)

**Databases**<br/>
![PostgreSQL](https://img.shields.io/badge/Postgres-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![DuckDB](https://img.shields.io/badge/DuckDB-FFF000?style=for-the-badge&logo=duckdb&logoColor=black)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-07405E?style=for-the-badge&logo=sqlite&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3FCF8E?style=for-the-badge&logo=supabase&logoColor=white)

**AI / ML**<br/>
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)
![Keras](https://img.shields.io/badge/Keras-D00000?style=for-the-badge&logo=keras&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)
![SciPy](https://img.shields.io/badge/SciPy-8CAAE6?style=for-the-badge&logo=scipy&logoColor=white)
![MLflow](https://img.shields.io/badge/MLflow-0194E2?style=for-the-badge&logo=mlflow&logoColor=white)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=for-the-badge&logo=langchain&logoColor=white)
![OpenTelemetry](https://img.shields.io/badge/OpenTelemetry-000000?style=for-the-badge&logo=opentelemetry&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)

**Apps, Analytics & Viz**<br/>
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)
![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white)
![Plotly](https://img.shields.io/badge/Plotly-3F4F75?style=for-the-badge&logo=plotly&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)

</div>

<br/>

<div align="center">

`Data Engineering` &nbsp;•&nbsp; `Streaming Pipelines` &nbsp;•&nbsp; `Lakehouse Architecture` &nbsp;•&nbsp; `RAG` &nbsp;•&nbsp; `Multi-Agent Systems` &nbsp;•&nbsp; `AI Observability` &nbsp;•&nbsp; `Federated Learning` &nbsp;•&nbsp; `Knowledge Graphs` &nbsp;•&nbsp; `Open Source`

</div>

<br/>

### 📊 GitHub Stats

<div align="center">

<img src="https://github-readme-stats.vercel.app/api?username=DevammPatel&show_icons=true&theme=tokyonight&hide_border=true&count_private=true" height="165"/>
<img src="https://streak-stats.demolab.com/?user=DevammPatel&theme=tokyonight&hide_border=true" height="165"/>

</div>

<br/>

### 🌐 Find Me

<div align="center">

<a href="https://devammpatel.github.io/"><img src="https://img.shields.io/badge/Portfolio-0EA5E9?style=flat-square&logo=googlechrome&logoColor=white"/></a>
<a href="https://www.linkedin.com/in/Devamm"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=flat-square&logo=linkedin&logoColor=white"/></a>
<a href="https://github.com/DevammPatel"><img src="https://img.shields.io/badge/GitHub-100000?style=flat-square&logo=github&logoColor=white"/></a>
<a href="mailto:pateldevamm.12@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?style=flat-square&logo=gmail&logoColor=white"/></a>

</div>

<br/>

<div align="center">
<i>Building the infrastructure layer between raw data and good decisions.</i>
</div>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0EA5E9,100:0F172A&height=100&section=footer" width="100%"/>
