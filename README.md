# Phishing Website Detection

## 🧨 Business Problem

### 🏢 Company: SafeNet Web Security Solutions
SafeNet is a cybersecurity firm that provides a web safety plugin to browsers and corporate firewalls. Their goal is to identify and block phishing websites before users can click on them.

### 📌 Context:
Currently, SafeNet's detection system relies on:
- **Manually curated blacklists** (too slow to update).
- **Simple pattern-matching rules** (easily bypassed by smart attackers).

To improve their system, SafeNet wants to develop a machine learning-based phishing detection engine that:
1. Analyzes various characteristics of a URL (e.g., IP presence, '@' symbol, domain length, SSL status, etc.).
2. Classifies URLs in real-time as phishing or legitimate.
3. Integrates the engine into browsers, firewalls, or even email clients to pre-warn users.

### 🎯 Business Objective:
Automatically detect phishing websites based on their structural and technical attributes using a predictive machine learning model, with >95% accuracy and low false positives to minimize disruption for legitimate sites.

### 💼 Business Impact:
- Reduce user exposure to phishing attacks.
- Decrease helpdesk ticket volumes due to malware/ransomware.
- Improve customer trust and brand value.
- Potential monetization via API for other security platforms.

---

## 🧪 ML Problem Statement

**Goal:** Build a binary classification model to predict whether a website is phishing (-1) or legitimate (1), based on its technical attributes.

### 🧾 Success Metrics:
- **Accuracy / F1 Score**
- Low False Negatives (minimize missed phishing sites)
- Inference time (real-time readiness)

---

## 🧑‍💻 Data Understanding

The dataset consists of **5849 entries** and **31 features** related to website attributes, such as:

- **URL characteristics:** Length, subdomain presence, use of shortening services, SSL status, etc.
- **Traffic & Domain Info:** Web traffic, page rank, domain age, etc.
- **Miscellaneous:** Use of popups, iframes, redirects, and more.

### Dataset Columns:
1. `having_IP_Address`
2. `URL_Length`
3. `Shortining_Service`
4. `having_At_Symbol`
5. `double_slash_redirecting`
6. `Prefix_Suffix`
7. `having_Sub_Domain`
8. `SSLfinal_State`
9. `Domain_registeration_length`
10. `Favicon`
... (and 21 more columns)

### Sample Data (First 5 Rows):
| having_IP_Address | URL_Length | Shortining_Service | ... | Result |
|-------------------|------------|--------------------|-----|--------|
| -1                | 1          | 1                  | ... | -1     |
| 1                 | 1          | 1                  | ... | 1      |
| 1                 | 0          | 1                  | ... | -1     |
| 1                 | 0          | 1                  | ... | 1      |
| 1                 | 0          | -1                 | ... | 1      |

### Dataset Information:
- Total rows: 5849
- Total columns: 31
- Data types: Integer values (0, 1, -1)

---

## 🧠 Feature Engineering

- No missing data.
- Duplicate rows are removed.
- Skewed features handled via transformation techniques like PCA to retain 80% variance.

---

## 🚀 Model Development

- **Modeling Framework:** Binary classification
- **Evaluation Metrics:** Accuracy, F1 Score, Low False Negatives, Inference Time

---

## 🔧 Installation

Clone this repository and install dependencies:
```bash
git clone https://github.com/yourusername/phishing-detection
cd phishing-detection
pip install -r requirements.txt
