# Startup_Pub


**Title: Mapping Innovation in Energy Startups: A Data Fusion Journey with OpenCorporates and Semantic Scholar**  

**Subtitle: How we linked company data with academic research to uncover hidden innovation patterns**  

**Author: Connor MacLean**  

---

### Introduction  

In today’s fast-evolving energy sector, keeping track of innovative startups is both a challenge and an opportunity. With thousands of new companies emerging each year, how can investors, policymakers, and researchers quickly identify the most promising ventures—especially those with deep scientific expertise?  

During my PhD research at INSA Strasbourg, I set out to tackle this problem by building a scalable data pipeline that fuses two powerful data sources: **OpenCorporates** for company information, and **Semantic Scholar** for academic publications. The goal was simple but ambitious: link energy startups to the research output of their founders and officers, and use that linkage to assess their innovative potential. Importantly, this methodology can be applied to any domain, provided filtering is done for domain-specific research. 

In this post, I’ll walk through the methodology, share some key findings, and explain how this approach opens new doors for data-driven innovation analysis.  

---

### Why This Matters  

The transition to renewable energy depends not just on capital, but on knowledge. Many startups are founded by researchers and engineers whose academic work directly informs their commercial ventures. Yet until now, there’s been no systematic way to connect company data with scientific publication records at scale.  

By bridging this gap, we can:  
- Identify startups with strong research foundations  
- Track emerging trends in energy technology  
- Help investors and accelerators spot scientifically-grounded innovation early  

---

### Building the Dataset: A Step-by-Step Process  

#### Step 1: Sourcing Company Data with OpenCorporates  

We started by querying the **OpenCorporates API** for all companies registered under industry codes related to energy generation, storage, and distribution. We focused on five key regions: the EU, Norway, the UK, Switzerland, and the US, and limited our search to companies founded between 2020 and 2025 to capture recent innovation activity. We requested bulk data in this step, which limits the amount of data on individual companies.

**Filters applied:**  
- Industry codes: `351` (Electricity Generation) and equivalents across national classification systems  
- Active status only  
- No dissolved companies  

This initial pull gave us a basic dataset of over **27,000 startups**, including company names, locations, and incorporation dates.  

#### Step 2: Extracting Officer Information  

A second call to the OpenCorporates API allowed us to access more fine-grained data for these startups. Not all company listings contain the names of their members, so the dataset was limited to those containing officer lists. These names (as well as their affiliations) became the critical link between the corporate and academic worlds.  

#### Step 3: Linking to Academic Publications via Semantic Scholar  

Using the **Semantic Scholar API**, we searched for academic articles authored by individuals matching the officer names. To improve accuracy, we used available affiliation data where possible.  

**Result:** We successfully linked over **15,000 startups** to one or more scientific publications - creating a novel, research-enriched company dataset.  

#### Step 4: Filtering for Relevance  

Not every publication is relevant to energy innovation. We filtered articles based on their research fields, keeping only those aligned with energy-related domains such as:  
- Applied Sciences (Engineering, Materials Science)  
- Natural Sciences (Physics, Chemistry, Environmental Science)  
- Formal Sciences (Mathematics, Computer Science)  

This step reduced the corpus by roughly 50%, leaving us with a focused set of **~175,000 articles** tied directly to energy startups.  

---

### Key Findings  

#### 1. Research Diversity Varies Widely  
While most startup-linked articles were single-discipline (e.g., purely engineering or physics), a meaningful subset showed strong interdisciplinary engagement—a signal of higher innovation potential.  

#### 2. High-Interdisciplinary Work Is Rare but Promising  
About **4%** of articles combined fields from distinct domains (e.g., Physics + Computer Science, or Chemistry + Medicine). These cross-domain papers often represent novel approaches that could lead to breakthroughs in energy tech.  

#### 3. Novel Data Fusion  
By merging OpenCorporates’ structured company data with Semantic Scholar’s publication records, we created a **first-of-its-kind dataset** that maps the scientific footprint of energy startups. This fusion enables new kinds of trend analysis, portfolio evaluation, and innovation forecasting.  

---

### Methodological Notes  

#### Handling Ambiguity  
Matching names between company officers and academic authors is inherently noisy. We used filtering by field and manual validation where possible to reduce false positives. Future iterations could incorporate disambiguation algorithms or ORCID integration.  

#### Scalability  
The entire pipeline is automated and can be rerun as new data becomes available. This makes it suitable for ongoing monitoring of the startup landscape.  

#### Open Source Access  
The code for this project is publicly available on [GitHub](https://github.com/MacLean-C/Startup_Pub/tree/main), allowing others to replicate, extend, or adapt the methodology for other sectors.  

---

### Why OpenCorporates Was Essential  

OpenCorporates provided the reliable, structured, and legally grounded company data needed to build this pipeline. The API’s consistency across jurisdictions and its rich officer metadata were critical to establishing robust links between companies and researchers.  

This project demonstrates how open company data can be used not just for compliance or due diligence, but also for **innovation mapping** and **research attribution**—a novel application with real-world impact.  

---

### Looking Ahead  

This work is part of my PhD thesis in Computer Science, and the methodology continues to evolve. We’re now exploring:  
- Enhanced name disambiguation techniques  
- Integration of patent data for a fuller innovation picture  
- Real-time monitoring of startup research output  

We believe this approach can be extended beyond energy to other sectors and that the methodology can be generalized.  

---

### Acknowledgments  

This research was conducted at the ICube Laboratory, INSA Strasbourg, with support from the EDF Discovery Group. Special thanks to the OpenCorporates team for their support and for maintaining such a valuable public resource.  

---

 


