# IEEE Campus Energy Forecasting Challenge

Build an AI-powered energy forecasting system to predict campus electricity consumption and recommend energy reduction strategies.

---

## 🎯 Challenge Overview

**Duration**: 5 hours
**Team Size**: 2-4 students

**Your Mission**:
1. Build a forecasting model to predict the next 7 days of energy consumption
2. Create an interactive dashboard showing patterns and predictions
3. Provide 3 specific, data-driven recommendations for 10% energy reduction
4. Present your solution in 5 minutes

---

## 📊 Dataset

### Files Included

- `campus_energy_data.csv` - 18 months of hourly energy data (~218,000 rows)
- `building_metadata.csv` - Building information

### Data Dictionary

#### campus_energy_data.csv

| Column | Description | Type |
|--------|-------------|------|
| `datetime` | Hourly timestamp | DateTime |
| `facility_id` | Building identifier (Building_A to Building_G) | String |
| `consumption_mw` | Energy consumption | Float (Megawatts) |
| `grid_stability_factor` | Grid stability indicator | Float (0.85-0.99) |
| `renewable_mix_percent` | Renewable energy % | Float (5-25) |
| `peak_demand_indicator` | Peak hours flag | Int (0/1) |

#### building_metadata.csv

| Column | Description |
|--------|-------------|
| `facility_id` | Building identifier |
| `description` | Building purpose |
| `building_type` | Academic / Support / Residential |

**Dataset Stats**:
- 7 buildings (3 Academic, 2 Support, 2 Residential)
- ~18 months of hourly data
- ~218,000 total measurements

---

## 🏆 Judging Criteria (100 points)

| Category | Points | What's Evaluated |
|----------|--------|------------------|
| **Model Performance** | 30 | MAPE on hidden test data |
| **Insights & Recommendations** | 30 | Quality, specificity, feasibility |
| **Dashboard** | 20 | Usability, visualizations, interactivity |
| **Presentation** | 20 | Clarity, understanding |
| **Bonus** | +10 | Creativity, clean code |

### Model Scoring

| MAPE | Points | | MAPE | Points |
|------|--------|-|------|--------|
| < 5% | 30 | | 15-20% | 15 |
| 5-10% | 25 | | 20-30% | 10 |
| 10-15% | 20 | | > 30% | 5 |

**Note**: Insights matter as much as accuracy! (30 pts each)

---

## 📋 Submission Requirements

### 1. Code
Submit ONE of:
- Jupyter notebook (.ipynb)
- GitHub repository link
- Deployed app URL

### 2. Predictions CSV (Required)
```csv
datetime,facility_id,predicted_mw
2022-11-01 00:00:00,Building_A,0.0234
2022-11-01 01:00:00,Building_A,0.0221
...
```

### 3. Presentation (Optional)
- Max 3 slides OR demo directly from dashboard

---

## 🚀 Getting Started

### 1. Clone Repository

```bash
git clone [YOUR-REPO-URL]
cd ieee-energy-challenge
```

### 2. Set Up Environment

```bash
# Create virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Install packages
pip install -r requirements.txt
```

### 3. Load Data

```python
import pandas as pd

df = pd.read_csv('campus_energy_data.csv')
df['datetime'] = pd.to_datetime(df['datetime'])
buildings = pd.read_csv('building_metadata.csv')

print(f"Loaded {len(df):,} rows")
print(f"Date range: {df['datetime'].min()} to {df['datetime'].max()}")
```

---

## 💡 Tips for Success

### Focus on Insights Over Perfection

Example scores:
- 12% MAPE + amazing insights = **84 pts** ✅
- 4% MAPE + generic insights = **68 pts** ❌

### Use AI Tools!

**Encouraged**: ChatGPT, Claude, Copilot
**Required**: Understand your code for Q&A

### What Makes a Good Recommendation?

❌ **Bad**: "Use less energy"

✅ **Good**: "Building F shows 40% higher consumption 6-9 PM. Implement load-shifting for laundry after 10 PM. Expected savings: 720 kWh/month (₹5,760)."

### Explore Patterns

- Hour-of-day variations
- Weekday vs weekend
- Building type differences
- Unusual spikes

### Model Suggestions

**Easy**: Prophet, Moving Average
**Medium**: ARIMA, XGBoost
**Advanced**: LSTM, Ensemble

---

## ⚠️ Rules

1. **AI tools allowed** - ChatGPT, Claude, Copilot encouraged
2. **No pre-built solutions** - Don't copy I-BLEND notebooks
3. **Original work** - Code written during hackathon
4. **Team only** - No outside help
5. **No test data access** - Model tested on hidden data

---

## ❓ FAQ

**Q: Can we use external data?**
A: No - only provided dataset.

**Q: What if we don't finish?**
A: Submit what you have!

**Q: Dashboard required?**
A: Yes, but static plots acceptable if interactive fails.

**Q: Python version?**
A: 3.8+ (3.10 recommended)

---

## 📞 Support

- Ask mentors during event
- Open issues on GitHub
- Contact: [organizer-email]

---

**Good luck! 🚀**

*Organized by IEEE [Chapter] | Event: [Date] | Venue: [Location]*
