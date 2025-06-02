
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
  - Requires a valid Gemini API key or the endpoint of another GPT-compatible model.  
  - Shows sample email generation and deviation analysis.
  
- **`rf_model.joblib`**: Serialized Random Forest model exported from `6models-wholedat.ipynb`. You can load this directly (skipping retraining) in `agent.ipynb` or any custom Python script.
  
- **`poster.pptx`**  
  - Presentation-style poster that summarizes our approach, dataset, experimental results, and example agent outputs. Use this file to verify that your notebook outputs match the figures and text on the poster.

---

## Environment & Dependencies

Below is a concise summary of the environment and prerequisites needed to run the two Jupyter notebooks in this repository.

---

### 1. Common Requirements

- **Python Version**  
  - Python 3.8 or later (3.9+ recommended).

- **Virtual Environment (recommended)**  
  ```bash
  python3 -m venv venv
  source venv/bin/activate        # macOS/Linux
  venv\Scripts\activate           # Windows
  pip install --upgrade pip
  pip install pandas numpy scikit-learn matplotlib seaborn joblib jupyterlab ipykernel

- **API KEY**
  - Remember to export your own api key. Set as environment variable before launching Jupyter:
    ```bash
    export OPENAI_API_KEY="your_api_key_here"      # macOS/Linux
    setx OPENAI_API_KEY "your_api_key_here"        # Windows (PowerShell)
### 1. Common Requirements
After setting the requirements below, you can run the `6models-wholedat.ipynb` and `agent.ipynb` to reproduce the result!

