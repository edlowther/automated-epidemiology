# Why Can’t Epidemiology Be Automated (Yet)?

This repository accompanies the manuscript:

> **Bann D, Lowther E, Wright L, Kovalchuk J**  
> *Why can’t epidemiology be automated (yet)?* (Arxriv, 2025)
>
> [https://www.arxiv.org/abs/2507.15617](https://www.arxiv.org/abs/2507.15617)

---

## Abstract (Draft)

Recent advances in artificial intelligence (AI)—particularly generative AI—present new opportunities to accelerate, or even automate, epidemiological research. Unlike disciplines based on physical experimentation, a sizable fraction of Epidemiology relies on secondary data analysis and thus is well-suited for such augmentation. Yet, it remains unclear which specific tasks can benefit from AI interventions or where roadblocks exist. 

Awareness of current AI capabilities is also mixed. Here, we map the landscape of epidemiological tasks using existing datasets—from literature review to data access, analysis, writing up, and dissemination—and identify where existing AI tools offer efficiency gains. While AI can increase productivity in some areas such as coding and administrative tasks, its utility is constrained by limitations of existing AI models (e.g. hallucinations in literature reviews) and human systems (e.g. barriers to accessing datasets). 

Through examples of AI-generated epidemiological outputs, including fully AI-generated papers, we demonstrate that recently developed agentic systems can now design and execute epidemiological analysis, albeit to varied quality (see https://github.com/edlowther/automated-epidemiology). Epidemiologists have new opportunities to empirically test and benchmark AI systems; realising the potential of AI will require two-way engagement between epidemiologists and engineers. 

## Contents overview

In this repository, we provide examples of what some of these systems are capable of doing now. 

### 1. [Data Analysis Crow](https://github.com/Future-House/data-analysis-crow) 

This is an open-source tool from [FutureHouse](https://www.futurehouse.org/), a not-for-profit organisation based in the US. From their repository:

> Data Analysis Crow is an AI agent framework designed to perform complex scientific data analysis tasks by iteratively working through Jupyter notebooks. This agent takes in datasets and prompts, then systematically explores, analyzes, and interprets the data to provide comprehensive answers and insights.

It is capable of delegating tasks to various language models via API calls: we experimented with OpenAI's GPT 4.1 and Anthropic's Claude Sonnet 4. 

We used the data-generation process documented in [`inputs/generate-synthetic-data.ipynb`](/inputs/generate-synthetic-data.ipynb), which produces some significant relationships between variables and also various realistic problems such missing values, some outliers (e.g. very large salaries) and even some impossible values (e.g. negative heights). 

We prompted the system to carry out some simple linear regression tasks using the data; the results are available at [`outputs/data-analysis-crow_notebooks`](outputs/data-analysis-crow_notebooks). 

### 2. [AI Scientist-v2](https://github.com/SakanaAI/AI-Scientist-v2)

Building on similar themes as contained in the analysis outlined above, we also investigated this tool by [SakanaAI](https://sakana.ai/), which is billed as an end-to-end system, i.e. capable of contributing to every stage of the research project workflow, from ideation to producing written reports of findings. 

The AI Scientist-v2 defaults to using OpenAI models on the backend; we stuck with this approach and used the [ideation](https://github.com/SakanaAI/AI-Scientist-v2/blob/main/ai_scientist/perform_ideation_temp_free.py) feature to generate the outputs available at [`outputs/ai-scientist-v2_ideas`](outputs/ai-scientist-v2_ideas). 

### 3. Deep Research tools and [`data-to-paper`](https://github.com/Technion-Kishony-lab/data-to-paper)

We also prompted three closed-source tools - Claude 4 Opus from Anthropic, GPT o3 from OpenAI, and Gemini 2.5 pro from Google - and the open-source `data-to-paper` tool from the [Kishony Lab](https://kishony.technion.ac.il/) at the Technion-Israel Institute of Technology to produce full papers based on the synthetic data. The results are at [`outputs/full-papers`](outputs/full-papers). 

### 4. [NotebookLM](https://notebooklm.google/) 

This is a closed-source tool from Google that is capable of summarising information in various ways. We used it to convert our draft paper into a podcast, available at [`outputs/notebook-LM_podcasts`](outputs/notebook-LM_podcasts). 

*Questions or issues?* Open an issue in the repo or contact the authors.
