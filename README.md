# For Every Child, Evidence: Child Nutrition Analysis in The Gambia

*A data-driven contribution to understanding and addressing child malnutrition, aligned with SDG 2 
(Zero Hunger) and SDG 3 (Good Health and Well-being), using UNICEF's MICS6 household survey data.*

## 📌 Overview

Malnutrition remains one of the most persistent barriers to child survival, growth, and development 
worldwide — and The Gambia is no exception. Leaving no child behind requires more than national averages; 
it requires understanding **where** and **for whom** malnutrition is most severe, so that resources and 
programming can reach those furthest behind first.

This project analyzes the **Multiple Indicator Cluster Survey 6 (MICS6)** under-5 children's dataset — 
a nationally representative survey conducted by The Gambia Bureau of Statistics (GBoS) in partnership 
with UNICEF — to surface actionable disparities in child nutrition outcomes, supported by an AI-assisted 
layer for rapid, plain-language insight generation.

## 🎯 Key Findings

| Indicator | National Prevalence (weighted) |
|---|---|
| Stunting (chronic malnutrition) | 18.9% |
| Underweight | 13.8% |
| Wasting (acute malnutrition) | 6.2% |

- **Geographic inequity:** Stunting nearly doubles between the best- and worst-performing regions — 
  from 14.5% in Kanifing to 26.5% in Kuntaur — underscoring the need for geographically targeted responses.
- **Wealth inequity:** Children in the poorest households are stunted at nearly **twice the rate** of 
  children in the richest households (24.0% vs 13.0%), reflecting how poverty and undernutrition remain deeply linked.
- **Gender dimension:** Boys show higher stunting prevalence than girls (21.5% vs 16.3%), a pattern 
  consistent with global evidence and worth further investigation at the country level.

These findings echo UNICEF's core message: **national averages can mask the inequities that matter most**, 
and disaggregated data is essential to reach the most vulnerable children first.

## 🌍 Alignment with the Sustainable Development Goals

- **SDG 2 (Zero Hunger):** Directly informs Target 2.2 — ending all forms of malnutrition, including 
  achieving internationally agreed targets on stunting and wasting in children under 5.
- **SDG 3 (Good Health and Well-being):** Supports early identification of health risk factors linked 
  to childhood nutrition and survival.
- **SDG 10 (Reduced Inequalities):** Highlights disparities by wealth, region, and sex — central to 
  UNICEF's equity-focused approach to programming.

## 🛠️ Methodology

1. Loaded the official MICS6 SPSS (`.sav`) dataset using `pyreadstat`, preserving GBoS/UNICEF's original 
   variable and value labels for full traceability
2. Cleaned survey-specific missing-value codes and excluded biologically implausible anthropometric 
   z-scores, in line with WHO Child Growth Standards guidance
3. Derived WHO-standard malnutrition indicators from height-for-age, weight-for-age, and weight-for-height z-scores
4. Applied MICS6 sample weights throughout, ensuring all estimates are representative of the national 
   child population — not just the surveyed sample
5. Disaggregated findings by region (LGA), household wealth quintile, and sex, to surface equity gaps
6. Used the **Groq API (Llama 3.3 70B)** to generate a concise, plain-language programme brief from the 
   verified statistics — demonstrating how AI can accelerate evidence translation for decision-makers, 
   without compromising data integrity

## 🤖 Responsible & Ethical Use of AI

In line with UNICEF's commitment to the ethical and responsible use of emerging technologies for children, 
the AI component in this project was designed with clear boundaries:

- The model is used **only to summarize pre-verified statistics** already computed from the official dataset
- It does **not** generate, infer, or alter any underlying figures
- No personally identifiable respondent information is used at any stage — the MICS6 microdata is 
  anonymized at source, consistent with UNICEF's data protection and respondent privacy standards

This reflects a broader principle: **AI should support, not replace, rigorous and transparent data 
analysis**, especially when the evidence concerns the lives and wellbeing of children.

## 📂 Data Source & Acknowledgement

Data provided by **The Gambia Bureau of Statistics (GBoS)** and **UNICEF**, through the **Multiple 
Indicator Cluster Survey 6 (MICS6)**, 2018. Survey documentation available at 
[mics.unicef.org/surveys](http://mics.unicef.org/surveys).

> This analysis is conducted independently for research, learning, and portfolio purposes. In line with 
> MICS data access conditions, GBoS and UNICEF Gambia are acknowledged as the source of this data, and 
> any resulting publications will be shared with them accordingly.

## 🧰 Tools & Libraries

- Python, pandas, matplotlib
- `pyreadstat` for SPSS (.sav) metadata-preserving data access
- Groq API (Llama 3.3 70B) for AI-assisted insight summarization
- Google Colab

## 🚀 Running This Notebook

1. Open `Child_Nutrition_Gambia_MICS6.ipynb` in Google Colab
2. Upload `ch.sav` to the Colab session
3. Add a `GROQ_API_KEY` secret in Colab (🔑 icon → Add new secret) — get a free key at [console.groq.com](https://console.groq.com)
4. Run all cells sequentially, from data loading through to the AI-generated summary

## 📄 Disclaimer

This is an independent project prepared for demonstration and learning purposes. It is **not** an 
official UNICEF or GBoS publication, and does not represent the official position of either organization. 
All figures are derived from publicly available MICS6 microdata using standard, transparent methodology.

---

*"For every child, data. For every child, evidence. For every child, a fair chance."*
