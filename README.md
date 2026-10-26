# Hanuai Assignment

Submitted by **Sundeep Kumar Amara**.

This repository contains my work for both tasks of the assignment. Each task has its own folder with a README that explains the files and how to run them.

## Repository structure

```
Hanuai_Assignment/
├── README.md
├── .gitignore
├── task1/    Web scraping and sentiment analysis
└── task2/    Advanced EDA and text mining
```

## Task 1: Web scraping and sentiment analysis

Scrapes customer reviews, classifies their sentiment, and summarises what drives satisfaction and dissatisfaction.

| Deliverable | What it is |
|---|---|
| Python notebook (`.ipynb`) | Annotated scraper and sentiment analysis code |
| Dataset (`.csv` / `.xlsx`) | All scraped fields plus sentiment tags |
| Written report (`.pdf` / `.docx`) | Anti-scraping challenges and solutions, satisfaction drivers, pain points, and business recommendations |

See `task1/README.md` for details.

## Task 2: Advanced EDA and text mining

Analysis of 1,000 vehicle infotainment warranty events: data cleaning, text mining of the free-text narratives, issue categorisation, clustering and root-cause insights.

| Deliverable | File |
|---|---|
| Annotated notebook | `task2/Hanuai_Task2_EDA_TextMining.ipynb` |
| Tagged dataset | `task2/Hanuai_task2_tagged.xlsx` and `.csv` |
| Stakeholder report | `task2/Hanuai_Task2_Report.docx` and `.pdf` |

Headline findings:
- 89% of events end in a radio replacement.
- Component failure (38%) and communication/network faults (37%) are the two largest issue categories.
- 20% of claims occur within 90 days of in-service.
- Plant, make and model show only weak association with issue category.

See `task2/README.md` for details.

## How to review

1. Open the README in each task folder.
2. Read the notebook (GitHub shows the outputs and charts).
3. Read the report for the summary, recommendations and learnings.
4. The Excel files can't be previewed on GitHub, so download them to view the colour-coded tags.

## Running the code

Each task folder lists its own steps and a `requirements.txt`. In short:

```
python -m venv .venv
# Windows:  .venv\Scripts\activate
# Mac/Linux: source .venv/bin/activate
pip install -r requirements.txt
```

Then open the notebook in VS Code or Jupyter and run all cells.
