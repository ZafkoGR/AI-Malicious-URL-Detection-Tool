# 🛡️ AI-Based Malicious URL Detection System

This project presents a machine learning–powered tool designed to classify URLs as either **malicious** or **benign** based on their structural and lexical characteristics. It supports real-time input prediction, dynamic whitelisting, and an automated feedback loop to improve accuracy over time.

---

## 📘 Project Background

This malicious URL detection system was developed alongside the work presented in **Chapter 5: Practical AI in Cybersecurity** of my Master's thesis titled *Practical AI in Cyberwarfare and Cybersecurity*.

The project was implemented by **Konstantinos Zafeiropoulos** (Student ID: 20390293) at the  
**University of West Attica**  
**Faculty of Engineering, Department of Informatics and Computer Engineering**

> ⚠️ Although fully developed, this tool was **not included in the final thesis submission** due to time and scope constraints, as well as the decision to focus on tools with higher experimental impact and deeper integration with the thesis narrative.

---

## 1️⃣ Why AI is Needed

Malicious URLs today are:
- Obfuscated (e.g., `bit.ly`, `goo.gl`)
- IP-based or dynamically generated
- Designed to mimic trusted domains (e.g., fake bank login pages)

Traditional methods fail to adapt.  
✅ AI enables:
- Real-time detection of suspicious, never-before-seen URLs  
- Learning from patterns in phishing, malware, and defacement data  
- Adaptive protection against evolving cyber threats

---

## 2️⃣ Can This Be Done Without AI?

Yes, but with **major limitations**:

- Rule-based systems (e.g., blacklists, keyword filters) are:
  - Rigid and easy to bypass
  - Unable to generalize to new attack variants
- Manual updates and static filters increase human workload  
- No pattern recognition or self-learning capacity

---

## 3️⃣ AI Algorithm Used

✅ **ExtraTreesClassifier**  
(A randomized tree-based ensemble classifier)

- Builds multiple randomized decision trees and averages results  
- Highly suitable for:
  - Non-linear feature relationships  
  - High-dimensional tabular data  
  - Fast predictions with strong generalization  
- Great for computing **feature importance** and understanding model behavior

---

## 4️⃣ Tool & AI Architecture

### 🔄 Tool Flow

- **Input**: Raw URL string  
- **Feature Extraction**:
  - URL length  
  - Special character count  
  - Suspicious keyword frequency  
  - IP address presence  
  - HTTPS usage  
  - Shortener detection  
  - Whitelist check (domain-based)
- **Prediction Output**:  
  - Class: `malicious` or `benign`

### ♻️ Feedback Loop

- Tracks **false positives**
- Updates the whitelist dynamically
- Triggers **automated retraining** to reduce future errors

### 🧠 AI Model

- **Type**: Supervised Machine Learning  
- **Model**: ExtraTreesClassifier  
- **Task**: Binary Classification  
- **Training Set**: Combined real-world datasets, balanced 2:1 (benign : malicious)  
- **Retraining**: Ongoing, based on feedback and false-positive rate

---

## 5️⃣ AI Subcategory

✅ **Supervised Machine Learning**  
✅ **Binary Classification**

- No deep learning or NLP
- Uses structured features and decision tree ensembles  
- Interpretable and efficient for production use

---

## 6️⃣ Purpose & Social Impact

This project aims to:

- Build a **lightweight, explainable, real-time** detection tool  
- Protect users and organizations from:
  - Phishing attacks  
  - Malware infections  
  - Website defacements  
- Reduce **human error** in recognizing harmful links  
- Strengthen front-line cyber defenses for both experts and non-experts

---

## 7️⃣ Dataset Overview

The model is trained on a consolidated dataset derived from real-world sources:

| Dataset Name         | Source Type         | Description                             |
|----------------------|---------------------|-----------------------------------------|
| `malicious_phish.csv`| Phishing/Malware    | Labeled URLs including phishing, malware, and defacement links. Converted to binary labels: `malicious` or `benign` |

---
## 👤 Author

**Konstantinos Zafeiropoulos**  
Master's Thesis: *Practical AI in Cyberwarfare and Cybersecurity*  
University of West Attica – Department of Informatics and Computer Engineering
