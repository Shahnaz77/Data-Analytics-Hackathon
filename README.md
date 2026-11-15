# VoltRelay Energy: hackathon submission

Gradient Learnings Data Analytics Hackathon, 15 Nov 2025.

The question: VoltRelay's swaps and revenue grew a lot in 2024-25, but failures, rider churn and margins got worse. Why, and where should the next budget go?

Short answer: old Gen1 chargers in hot cities, a bad batch of Kyron batteries, and an unprofitable ZipDrop contract.

## Files
- `VoltRelay_Analysis.ipynb`: the main notebook (cleaning, Q1-Q6, deep dives). Runs top to bottom in about 30-40 seconds.
- `VoltRelay_Analysis_Report.docx` / `.pdf`: the written report
- `VoltRelay_Presentation.pptx`: slides used for the video (speaker notes have the script)
- `VoltRelay_Dashboard.html`: interactive dashboard, open in a browser
- `VIDEO_SCRIPT.md`: the video script
- `outputs/`: charts, result tables, `key_numbers.json`, and the data-cleaning log

## How to run
```bash
python3 -m venv .venv && .venv/bin/pip install pandas pyarrow duckdb matplotlib statsmodels plotly jupyter jupytext python-docx
.venv/bin/jupyter nbconvert --to notebook --execute --inplace VoltRelay_Analysis.ipynb
.venv/bin/python analysis/build_dashboard.py
.venv/bin/python analysis/build_report.py
cd deck && npm install && NODE_PATH=$PWD/node_modules node build_deck.js
```
Put the CSVs in `HackathonData/Hackathon Data Set _ Gradient/` (or just leave `HackathonData.zip` next to the notebook). For Google Colab, see `COLAB_SETUP.md`.

The notebook is generated from `analysis/voltrelay_analysis.py` (jupytext). The `analysis/x_*.py` files are rough exploration scripts from earlier on.

## AI use
I used Gemini as a coding assistant for parts of the code and for help drafting the report and slides. The analysis choices and conclusions were reviewed by me, and every number comes from the notebook.
