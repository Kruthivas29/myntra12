# 🛍️ StyleKart — Customer Intelligence Platform

> **SBR Session 5 | Customer Segmentation for Organisation Growth | 20 Marks**

A Streamlit-powered dashboard solving three interconnected e-commerce problems using data-driven models applied to ~175K retail transactions.

[![Open in Streamlit](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://your-app-name.streamlit.app)

---

## Three Problems Solved

| # | Problem | Method | Key Output |
|---|---------|--------|------------|
| 1 | **Customer Segmentation** | RFM Analysis (Recency, Frequency, Monetary) | 7 named segments with campaign recommendations |
| 2 | **Customer Lifetime Value** | BG/NBD + Gamma-Gamma (`lifetimes` library) | 6-month CLV prediction + tier classification |
| 3 | **Churn Prediction** | Logistic Regression + Random Forest | Churn probability + risk bands + business impact |

**Key Differentiator:** The Integrated Intelligence tab connects all three models into a single Master Customer Table.

---

## Project Structure

```
stylekart-customer-intelligence/
├── app.py                    # Main Streamlit app (5 tabs)
├── requirements.txt          # Pinned Python dependencies
├── packages.txt              # System-level packages (Streamlit Cloud)
├── .gitignore
├── data/
│   └── online_retail_II.csv  # ~15MB dataset (~175K records)
├── utils/
│   ├── __init__.py
│   ├── data_cleaning.py
│   ├── rfm.py
│   ├── clv.py
│   └── churn.py
└── .streamlit/
    └── config.toml           # Dark theme configuration
```

---

## 🚀 Deploy on Streamlit Cloud

### Step 1 — Push to GitHub

```bash
git init
git add .
git commit -m "Initial commit — StyleKart Customer Intelligence"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/stylekart-customer-intelligence.git
git push -u origin main
```

### Step 2 — Deploy

1. Go to [share.streamlit.io](https://share.streamlit.io) and sign in with GitHub
2. Click **"New app"**
3. Select your repo, branch (`main`), main file: `app.py`
4. Click **"Deploy"**

> ⚠️ First load takes 2–3 minutes as ML models train. Subsequent loads use `@st.cache_data`.

---

## 🖥️ Run Locally

```bash
git clone https://github.com/YOUR_USERNAME/stylekart-customer-intelligence.git
cd stylekart-customer-intelligence

python -m venv venv
source venv/bin/activate   # Windows: venv\Scripts\activate

pip install -r requirements.txt
streamlit run app.py
```

App opens at `http://localhost:8501`

---

## Tech Stack

| Layer | Library |
|-------|---------|
| Dashboard | `streamlit >= 1.32` |
| Data Processing | `pandas >= 2.0`, `numpy < 2.0` |
| Visualisation | `plotly >= 5.18` |
| ML Models | `scikit-learn >= 1.3` |
| CLV Modelling | `lifetimes >= 0.11.3` (BG/NBD + Gamma-Gamma) |

---

## Dataset

**Online Retail II** (UCI ML Repository) — proxy for StyleKart transaction data

- ~175K records, ~4,300 UK customers, Jan 2010 – Dec 2011
- Currency in GBP (≈ ₹105 per GBP)
- Behavioural segmentation only (no demographic data)

---

## References

Based on the *"Data-Driven Growth with Python"* series — Towards Data Science (9-part).
