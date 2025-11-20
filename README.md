# 🧑‍🎓 Actionable Student Feedback Analysis: Identifying Course Risk Factors

[![Python](https://img.shields.io/badge/Python-3.x-blue)](https://www.python.org/)
[![Libraries](https://img.shields.io/badge/Libraries-scikit--learn%2C%20nrclex%2C%20nltk-orange)](https://pypi.org/)

This repository details a project focused on transforming raw, qualitative **student feedback** into a quantitative risk assessment and a strategic **Action Plan** for academic administration.

The analysis in the `mid sem Q3.ipynb` notebook leverages **Natural Language Processing (NLP)**, specifically **Topic Modeling** and **Lexicon-Based Emotion Analysis** (`nrclex`), to move beyond simple sentiment scores. The goal is to isolate the most pressing concerns (the **"Fear Topic"**) and the strongest features of the course/platform (the **"Trusted Topic"**) to guide data-driven strategic improvements.

---

## 🎯 Project Goals and Objectives

The primary aims of this analysis were:

1.  **Topic Modeling & Clustering:** Use unsupervised learning to categorize thousands of unstructured student comments into a few core, actionable **themes** (e.g., course difficulty, instructor support, platform usability).
2.  **Emotional and Sentiment Analysis:** Apply the **`nrclex`** library to detect underlying human emotions (e.g., **Fear**, **Trust**, **Anger**, **Joy**) in the feedback, providing a deeper layer of insight than traditional polarity scoring.
3.  **Risk Assessment:** Quantify the percentage of students who fall into the **"At Risk"** category based on the presence of critical negative topics and dominant negative emotions.
4.  **Strategic Reporting:** Automatically generate a concise **`Executive_Summary.txt`** with clear, actionable recommendations for course directors and administrators.

---

## 📈 Key Methodology & Insights

The notebook executes a pipeline culminating in a high-level summary:

| Step | Technique | Business Insight |
| :--- | :--- | :--- |
| **Data Cleaning** | Stop-word removal, tokenization, lemmatization. | Prepares text for accurate feature extraction. |
| **Modeling** | Topic Modeling (e.g., LDA/NMF) | Isolates core themes (e.g., **"Assignment Load"** or **"Technical Bugs"**). |
| **Emotion Tagging** | **`nrclex`** (Lexicon-based) | Identifies the dominant *feeling* driving the feedback (e.g., comments related to 'exams' carry high **Fear**). |
| **Risk Scoring** | Combining Topic & Emotion Scores | Classifies **{at\_risk\_count}** students (**{at\_risk\_pct:.1f}%**) as needing urgent follow-up. |
| **Reporting** | Automated Summary Generation | Extracts and presents the most critical negative topic (**Fear Topic {fearful\_topic\_idx}**) and the most positive topic (**Trusted Topic {trusted\_topic\_idx}**). |

### Final Output Snippet

The analysis directly generates the most critical phrases for administrative review:
* **Primary Pain Point:** **Topic {fearful\_topic\_idx}** (Keywords: {topic\_dict[fearful\_topic\_idx]}).
* **Platform Strength:** **Topic {trusted\_topic\_idx}** (Keywords: {topic\_dict[trusted\_topic\_idx]}).
* **Actionable Quotes:** {phrase\_1}, {phrase\_2} (Extracted from the high-risk group).

---

## 📂 Project Structure

| File | Description |
| :--- | :--- |
| `mid sem Q3.ipynb` | The main Jupyter Notebook containing the full code, data preprocessing, Topic Modeling, emotion analysis, and final report generation. |
| `[Feedback Data Filename]` | **(REQUIRED)** The raw dataset containing student comments and metadata (e.g., course ID, term). *Not included in this repo.* |
| `Executive_Summary.txt` | **Final Output.** A concise, automated report summarizing the key risk topics and strengths for administration. |
| `README.md` | This overview file. |

---

## 🛠️ Requirements and Setup

### Prerequisites

Ensure you have **Python 3** installed.

### Dependencies

Install all necessary libraries using the command below:

```bash
pip install pandas numpy scikit-learn matplotlib seaborn nltk nrclex
