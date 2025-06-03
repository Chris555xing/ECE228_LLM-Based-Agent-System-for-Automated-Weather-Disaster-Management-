### 1. Files Description
- **`data/`**  
  - Contains all of the CSV data splits and the serialized Random Forest model.  
  - **`train.csv`**: Historical weather features (temperature, humidity, wind speed, precipitation, etc.) and a binary label (`label`) indicating whether a wildfire occurred.  
  - **`test.csv`**: The held-out test set for evaluating classifier performance.  

- **`7models_comparison.ipynb`**  
  - Reads `data/train.csv` and `data/test.csv`, preprocesses features, trains six different ML classifiers (Logistic Regression, Random Forest, ,MLP, CNN1D, etc.), computes performance metrics (accuracy, ROC-AUC, F1, recall), and plots ROC curves.  
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

### 2. Common Requirements

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
## 3. Results

After installing all requirements, you can run both `6models-wholedata.ipynb` and `agent.ipynb` to reproduce the following tables and images. Simply place your figures (exported from the poster and Jupyter notebooks) under an `images/` folder (or any path you prefer), then reference them with standard Markdown syntax.

---

### 3.1 ML Model Performance (Poster Tables)

Below is an example of how to include the main performance table from your poster. Copy your actual numbers into this Markdown table.

| Model               | Accuracy | Precision | Recall | F1-score | ROC-AUC |
|---------------------|----------|-----------|--------|----------|---------|
| Logistic Regression | 0.82     | 0.80      | 0.78   | 0.79     | 0.87    |
| Random Forest       | 0.89     | 0.87      | 0.84   | 0.85     | 0.92    |
| XGBoost             | 0.88     | 0.86      | 0.83   | 0.84     | 0.90    |
| SVM                 | 0.85     | 0.83      | 0.80   | 0.81     | 0.88    |
| KNN                 | 0.81     | 0.79      | 0.77   | 0.78     | 0.85    |
| Neural Network      | 0.86     | 0.84      | 0.82   | 0.83     | 0.89    |

> **Note:** Replace the above placeholder numbers with the exact values from your poster.

---

### 3.2 ROC Curves and Poster Figures

![ROC Curve Comparison](result/ROC_curves.png)
*Figure 1: ROC curves for six classifiers on the test set.*

### 3.3 Example email response

![Email Response](result/Example_email_response.png)
*Figure 2: Excerpt from project poster summarizing data sources and methodology.*


