# Final Team Project: Machine Learning IoT Application Design and Implementation
## aai-smart-building-iot

Final Team Project for **AAI-530-03 (Data Analytics and Internet of Things)** University of San Diego.  
This repository contains an end-to-end notebook for data processing, two machine learning approaches, and Tableau-ready output for dashboarding.

---

## Team
- Santosh Kumar  
- Denis Mulabegovic  
- Thomas Geraci  

---

## Project Overview
We use the **Bristol Smart Building IoT dataset** (temperature, humidity, light, RSSI) to build a preprocessing pipeline and two forecasting models:

- **LSTM (Deep Learning)** for **one-step-ahead temperature prediction**
- **Random Forest Regressor** for **one-step-ahead humidity prediction**

The notebook also exports a combined CSV that can be used directly in Tableau for actual vs predicted visuals and error monitoring.

---

## Repository Contents
- Main notebook: `Final Team Project Machine Learning IoT Application Design and Implementation.ipynb`
- `README.md`
- `.gitignore`

---

## Dataset (Bristol Smart Building IoT — Local Setup Required)
The Bristol dataset is **not included** in this repository due to its size (~2.2 GiB).  
To reproduce results, the instructor (or any user) must **download and extract the dataset locally**, then update the dataset path in the notebook.

**Official dataset source (University of Bristol data repository / DOI):**  
- https://doi.org/10.5523/bris.fwlmb11wni392kodtyljkw4n2

### Setup Steps (Required)
1. Open the DOI link above and download the full dataset ZIP (~2.2 GiB).
2. Extract the ZIP locally (it contains many CSV files organized in folders).
3. Open the notebook and locate the configuration cell that defines:
   - `LOCAL_DATA_DIR = ...`
4. Set `LOCAL_DATA_DIR` to the folder containing the extracted Bristol dataset CSV files (or the top-level folder that contains the CSV subfolders).
   - Example (Windows):
     - `LOCAL_DATA_DIR = r"C:\Users\<you>\Downloads\bristol_dataset\"`
   - Example (macOS/Linux):
     - `LOCAL_DATA_DIR = "/Users/<you>/Downloads/bristol_dataset/"`
5. Run the notebook **top-to-bottom** (recommended: **Restart Kernel → Run All**).

> The notebook searches within `LOCAL_DATA_DIR` for `.csv` files (including inside subfolders).  
> If no CSVs are detected, adjust `LOCAL_DATA_DIR` to the correct extracted folder level.

### Do Not Upload to GitHub
Please do not commit:
- The raw dataset folder (thousands of CSVs)
- Any dataset ZIP files (e.g., ~2.2 GiB download)
- Large regenerated outputs that can be recreated by running the notebook

If needed, ensure your local dataset folder is excluded in `.gitignore` (recommended: ignore `data/` and any extracted dataset directories).

---

## How to Run
1. Open the notebook in **JupyterLab** / **Jupyter Notebook**.
2. Update `LOCAL_DATA_DIR` (see Dataset section above).
3. Run the notebook from top to bottom (recommended: **Restart Kernel → Run All**).
4. Confirm preprocessing, model training, and evaluation complete without errors.

---

## Tableau Output (CSV)
When the notebook finishes, it saves a Tableau-ready CSV to:

- `data/processed/tableau_predictions.csv`

The exported table includes:
- `timestamp`
- temperature: `actual_temperature`, `pred_temperature`, `temp_abs_error`
- humidity: `actual_humidity`, `pred_humidity`, `humidity_abs_error`

Use this CSV in Tableau to create:
- Actual vs predicted time-series lines
- Error over time lines
- KPI tiles (latest actual/prediction/error)

---

## Notes on AI Tool Disclosure
AI-assisted tools were used for debugging support, sanity-checking intermediate outputs, and validating that the Tableau export structure is correct. All code and results were reviewed, executed, and validated by the team.

---

## Dependencies
Typical environment:
- Python 3.9+
- numpy, pandas, matplotlib
- scikit-learn
- tensorflow / keras

Install (example):
```bash
pip install numpy pandas matplotlib scikit-learn tensorflow
