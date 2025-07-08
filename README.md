# Incident Response Agent 🔐⚠️

A security-first LLM agent that triages logs and alerts to assist in incident response. It analyzes logs for anomalies, summarizes incidents, and recommends next steps for mitigation.

---

## 🚨 Features

- 📥 Accepts logs (JSON, plain text, or CSV)
- 🧠 Detects patterns or known attack signatures
- 🛡️ Categorizes incidents (e.g., auth failure, RCE, DoS)
- ✍️ Suggests mitigation actions
- 📤 Generates incident summaries

---

## 🛠️ Tech Stack

- Python 3.10+
- LangChain or OpenAI
- FastAPI or Streamlit
- Sample ELK/Graylog logs or simulated data
- SQLite or file-based incident storage

---

## 🚀 Usage

```bash
git clone https://github.com/HiraWaheed/Incident_Responder.git
cd Incident_Responder
python -m venv venv && source venv/bin/activate
pip install -r requirements.txt
````

Run:

```bash
streamlit run app.py
```

---

## 📂 Log Input Example

```log
[2024-07-05 13:45:12] Failed login attempt from 192.168.1.10 (username: admin)
[2024-07-05 13:45:13] Multiple 500 errors detected on /api/auth
```

---

## 🧠 Agent Flow

1. Preprocesses logs for timestamp, IP, message
2. LLM classifies severity & incident type
3. Suggests next steps (e.g., block IP, restart service)
4. Stores in local log store or DB

---

## 📝 Output Example

```json
{
  "incident_type": "Brute Force Login",
  "severity": "High",
  "recommended_action": "Temporarily block IP 192.168.1.10, notify admin",
  "summary": "Multiple failed login attempts detected within 2 minutes."
}
```

---

## 🚀 Future Work

* Real-time log ingestion
* Slack/Webhook alerts
* Integration with SIEMs or PagerDuty
