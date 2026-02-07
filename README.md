# Final Team Project: Machine Learning IoT Application Design and Implementation
# aai-smart-building-iot

Final Team Project for AAI-530-03 (Data Analytics and Internet of Things) University of San Diego.  
This repository contains the end-to-end notebook for data processing, two machine learning approaches, and Tableau-ready output for dashboarding.

## Team
Santosh Kumar  
Denis Mulabegovic  
Thomas Geraci  

## Project Overview
We use the Bristol Smart Building IoT dataset (temperature, humidity, light, RSSI) to build a preprocessing pipeline and two forecasting models:
- LSTM (Deep Learning) for one-step-ahead temperature prediction
- Random Forest Regressor for one-step-ahead humidity prediction

The notebook also exports a combined CSV that can be used directly in Tableau for actual vs predicted visuals and error monitoring.

## Repository Contents
- Main notebook: `Team_6_Final Team Project Machine Learning IoT Application Design and Implementation_...ipynb`
- `README.md`
- `.gitignore`

## Data (Bristol Dataset – Local Setup)
The Bristol dataset is **not included** in this repository due to its size. Each team member should download/extract it locally.

In the notebook, find the configuration cell where the local dataset directory is set and update it to your machine’s dataset location.

After setting the directory, run the notebook from top to bottom so the loader can find the CSV files.

### Do not upload to GitHub
Please do not commit:
- The raw dataset folder (thousands of CSVs)
- Any dataset ZIP files
- Large regenerated outputs that can be recreated by running the notebook

If needed, add your dataset folder name to `.gitignore`.

## How to Run
1. Open the notebook in JupyterLab / Jupyter Notebook.
2. Run the notebook from top to bottom (recommended: restart kernel, then run all).
3. Confirm preprocessing, model training, and evaluation complete without errors.

## Tableau Output (CSV)
When the notebook finishes, it saves a Tableau-ready CSV in the project’s processed output folder.

The exported table includes:
- `timestamp`
- temperature: actual, predicted, absolute error
- humidity: actual, predicted, absolute error

Use this CSV in Tableau to create:
- Actual vs predicted time-series lines
- Error over time lines
- KPI tiles (latest actual/prediction/error)

## Notes on AI Tool Disclosure
AI-assisted tools were used for debugging support, sanity-checking intermediate outputs, and validating that the Tableau export structure is correct. All code and results were reviewed, executed, and validated by the team.

## Dependencies
Typical environment:
- Python 3.9+
- numpy, pandas, matplotlib
- scikit-learn
- tensorflow / keras
- seaborn

Install (example):
```bash
pip install numpy pandas matplotlib scikit-learn tensorflow seaborn
