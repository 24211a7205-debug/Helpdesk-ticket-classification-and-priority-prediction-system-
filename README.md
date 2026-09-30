
Help Desk Ticket Classification & Priority Prediction

Classifies incoming IT support tickets by category (Network, Hardware, Software, Access, Email, Security) and predicts priority (Low → Critical), with a live Streamlit dashboard.

Features
TF-IDF (1–2 grams) + Logistic Regression for both tasks

Live monitor: simulated ticket stream classified in real time (toggle in sidebar)

"Try a ticket" tab for ad-hoc predictions with confidence

Model performance tab: accuracy, macro-F1, confusion matrices
Quick start

pip install -r requirements.txt
python -m src.train        # generates data, trains, saves models/
streamlit run app.py
Structure

app.py               Streamlit dashboard
src/generate_data.py Synthetic ticket generator
src/train.py         Training + evaluation
models/              Saved models + metrics.json

Using your own data
Replace generate() in src/train.py with a CSV loader that returns columns text, category, priority. The synthetic data is rule-generated, so scores are optimistic; expect lower numbers on real tickets.
Ideas
Sentence-embedding models, SLA breach prediction, feedback loop for agent corrections, Docker + CI.