# Clément Longeac

**AI engineering · Clinical NLP · Self-supervised representation learning**

Final-year engineering student at **ESIEE Paris** (Data Science & AI, *Tremplin Recherche* research track), based in Paris.
I build NLP systems for French clinical text and I am working towards a PhD in AI for biomedical research.

📍 Paris, France  ·  🗣️ French · English · Japanese · Spanish
🔗 [LinkedIn](https://www.linkedin.com/in/clément-longeac)  · [Kaggle](https://www.kaggle.com/clmentlongeac/code) · [GitLab (Debian Salsa)](https://salsa.debian.org/Clement_LONGEAC) · ✉️ [clement.longeac@edu.esiee.fr]

*Seeking a six-month research or applied ML internship starting March 2027*

---

## Research focus

| Topic | Status |
|---|---|
| **Clinical named-entity recognition in French oncology** (rules → Transformer → LLM) | Active, see [DEMNE](https://github.com/longeacc/DEMNE-Determination-of-Extraction-Methode-for-Named-Entity) |
| **Latent-space prediction (JEPA-style) applied to clinical text** | Early exploration |
| **Reproducible ML pipelines** (CI/CD, containers, experiment tracking) | Ongoing |
---

## Featured project

### [DEMNE](https://github.com/longeacc/DEMNE-Determination-of-Extraction-Methode-for-Named-Entity): hybrid NLP pipeline for French oncology
 
**Adaptive selection of the named-entity extraction method for frugal clinical NLP in oncology.** Not every entity in a French clinical report needs a transformer or an LLM. DEMNE computes five corpus metrics per entity type and routes it to the least costly tier predicted to be good enough (**rules, transformer-based model, or LLM**), addressing the performance, explainability and frugality trilemma.
 
|  **99.5 %**  |  **0.941 vs 0.358**  |  **0.866**  |  **59 · 92**  |
|:---:|:---:|:---:|:---:|
| of mentions routed to rules on an unseen AP-HP cohort (411/413) | mean F1, rules vs fine-tuned DrBERT, same entities | routing concordance on an unseen corpus (leave-one-corpus-out) | oncology entity types · entity-corpus pairs in the reference standard |
 
**How it works.** Rules are chosen only on positive evidence (a stable surface pattern with a homogeneous vocabulary, or a discriminative keyword set, and a safe negation context). Otherwise the entity escalates to a supervised transformer when the corpus holds enough labelled examples, and to an LLM as a last resort. The 17 parameters are calibrated with Optuna (NSGA-II) on concordance and an asymmetric cost that penalizes under-escalation twice as much as over-escalation.
 
- **In-domain (59 oncology entities):** concordance 0.954, cost-score 0.947, pooled accuracy 0.915 (54/59), no over-escalation; fixed-tier baselines reach at most 0.729
- **External validation:** 300 AP-HP CT-scan reports (colorectal and head-and-neck cancers), 7 tumour-response entities, frozen configuration with no retuning; 6 routed to rules (F1 0.892 to 0.972), 1 to the LLM tier
- **Domain transfer:** concordance drops to 0.45 to 0.73 across domains, so the method is recalibrated for a new domain or language
- Open-source metric pipeline with a Streamlit dashboard

<img width="371" height="303" alt="decision_graph" src="https://github.com/user-attachments/assets/ce820f8d-2f83-4e7c-8798-d144e0e4660f" />

Manuscript in preparation. Stack: Python, PyTorch, Hugging Face Transformers, DrBERT, Optuna, EDS-NLP, Streamlit


---

## Other selected work

| Project | What it is |
|---|---|
| [Air-quality data science project](https://github.com/longeacc/DATA_Science_PROJECT_AirQuality_France) | Analysis of reconstructed background air-pollution concentrations over France (2000–2015) |
| [Face recognition with deep learning](https://github.com/longeacc/IA-and-Deep-Learning---Modern-face-recognition-with-deep-learning-project-) | Course project on modern deep-learning face recognition |
| [DevOps on AWS](https://github.com/wilfried-lafaye/dashboard-devops-aws) | Team project: Flask dashboard, Quartz docs, automated deployment (EKS, Cloudflare Pages) |
| [Data engineering project](https://github.com/william-zee/Projet_Data_Engineering) | Team project in Python |
| [Face recognition](https://github.com/longeacc/IA-and-Deep-Learning---Modern-face-recognition-with-deep-learning-project-) | Course project on modern deep-learning face recognition |
| [Debian ROCm CI](https://salsa.debian.org/Clement_LONGEAC) | autopkgtest scripts validating scientific software on AMD GPUs |
| [Kaggle](https://www.kaggle.com/clmentlongeac/code) | Notebooks |

---

## Tools

![Python](https://img.shields.io/badge/Python-24292e?style=flat-square&logo=python&logoColor=white)
![C](https://img.shields.io/badge/C-24292e?style=flat-square&logo=c&logoColor=white)
![C++](https://img.shields.io/badge/C++-24292e?style=flat-square&logo=cplusplus&logoColor=white)
![Bash](https://img.shields.io/badge/Bash-24292e?style=flat-square&logo=gnubash&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-24292e?style=flat-square&logo=pytorch&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-24292e?style=flat-square&logo=tensorflow&logoColor=white)
![Hugging Face](https://img.shields.io/badge/Hugging%20Face-24292e?style=flat-square&logo=huggingface&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-24292e?style=flat-square&logo=scikitlearn&logoColor=white)
![spaCy](https://img.shields.io/badge/spaCy-24292e?style=flat-square&logo=spacy&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-24292e?style=flat-square&logo=pandas&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-24292e?style=flat-square&logo=streamlit&logoColor=white)
![Linux](https://img.shields.io/badge/Debian-24292e?style=flat-square&logo=debian&logoColor=white)
![Git](https://img.shields.io/badge/Git-24292e?style=flat-square&logo=git&logoColor=white)
![GitLab CI](https://img.shields.io/badge/GitLab%20CI-24292e?style=flat-square&logo=gitlab&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-24292e?style=flat-square)
---

**Language models** DrBERT, BioMistral, fine-tuning, few-shot prompting, GPT-4 and Claude APIs
**Clinical NLP** EDS-NLP, BRAT, CoNLL, python-crfsuite, eco2ai
**Methods** grid search, asymmetric ordinal loss, corpus analysis, frugal and explainable AI
**GPU** AMD ROCm, OpenCL · **Regulation** EU AI Act (Art. 12, 14), GDPR, HDS

## Experience
 
| | |
|---|---|
| **Nov 2025 – Jun 2026** | **Research Fellow, Tremplin Recherche**: ESIEE Paris, LBA (Aix-Marseille Université) and AP-HP Health Data Warehouse. Designed DEMNE and its corpus metrics. |
| **May – Aug 2025** | **Intern, Synchrotron SOLEIL**: OpenCL autopkgtest scripts on the Debian ROCm CI, mapping scientific-software compatibility across AMD GPUs; automated install tests on clean virtual machines. |

## Currently

- Reading the I-JEPA and V-JEPA papers closely, and thinking about what prediction in latent space means for discrete text
- Writing up DEMNE as a technical report
- Looking for a **6-month research or applied-ML internship starting March 2027** (Paris and all over the world)
---

*Open to discussing clinical NLP, self-supervised learning and world models. Feel free to reach out.*
