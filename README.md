# ECE228_LLM-Based-Agent-System-for-Automated-Weather-Disaster-Management-
LLM-Based Agent System for Automated Weather Disaster Management 

- **`data/`**  
  - Optional folder for any additional raw or intermediary data files. If you have any scripts that convert raw data into `train.csv`/`test.csv`, place them here.

- **`train.csv` & `test.csv`**  
  - Contain historical weather features (temperature, humidity, wind speed, precipitation, etc.) and a binary label (`label`) indicating whether a wildfire occurred.  
  - These CSVs are the splits used in `6models-wholedat.ipynb` to train and validate classifiers.

- **`6models-wholedat.ipynb`**  
  - Reads `train.csv`/`test.csv`, preprocesses features, trains six different ML classifiers (Logistic Regression, Random Forest, XGBoost, SVM, etc.), computes performance metrics (accuracy, ROC-AUC, F1, recall), and plots ROC curves.  
  - Exports the best Random Forest model to `rf_model.joblib`.

- **`agent.ipynb`**  
  - Loads `rf_model.joblib` to perform real-time wildfire risk prediction.  
  - Demonstrates how the LLM agent wraps predictions in natural-language prompts.  
  - Requires a valid OpenAI API key or the endpoint of another GPT-compatible model.  
  - Shows sample email generation and deviation analysis.

- **`rf_model.joblib`**  
  - Serialized Random Forest model. You can load this directly (skipping retraining) in `agent.ipynb` or any custom Python script.

---

## 🛠️ Requirements & Installation

1. **Operating System**  
   - Tested on Windows 10 (Python 3.8+), macOS 12+, and Ubuntu 20.04+.  

2. **Python Version**  
   - Python 3.8 or later (we recommend 3.9).

3. **Clone the Repository**  
   ```bash
   git clone https://github.com/<your-username>/<repo-name>.git
   cd <repo-name>
