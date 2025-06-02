
- **`data/`**  
  - Contains all of the CSV data splits and the serialized Random Forest model.  
  - **`train.csv`**: Historical weather features (temperature, humidity, wind speed, precipitation, etc.) and a binary label (`label`) indicating whether a wildfire occurred.  
  - **`test.csv`**: The held-out test set for evaluating classifier performance.  

- **`6models-wholedat.ipynb`**  
  - Reads `data/train.csv` and `data/test.csv`, preprocesses features, trains six different ML classifiers (Logistic Regression, Random Forest, XGBoost, SVM, etc.), computes performance metrics (accuracy, ROC-AUC, F1, recall), and plots ROC curves.  
  - Exports the best Random Forest model to `data/rf_model.joblib`.

- **`agent.ipynb`**  
  - Loads `data/rf_model.joblib` to perform real-time wildfire risk prediction.  
  - Demonstrates how the LLM agent wraps predictions in natural-language prompts.  
  - Requires a valid OpenAI API key or the endpoint of another GPT-compatible model.  
  - Shows sample email generation and deviation analysis.
  
- **`rf_model.joblib`**: Serialized Random Forest model exported from `6models-wholedat.ipynb`. You can load this directly (skipping retraining) in `agent.ipynb` or any custom Python script.
  
- **`poster.pptx`**  
  - Presentation-style poster that summarizes our approach, dataset, experimental results, and example agent outputs. Use this file to verify that your notebook outputs match the figures and text on the poster.

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
