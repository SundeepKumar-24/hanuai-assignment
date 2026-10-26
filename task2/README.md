Task 2: Advanced EDA and Text Mining

Analysis of 1,000 vehicle infotainment warranty events (Hanuai_task2_assignment.csv): data cleaning, text mining of the three free-text narratives, issue categorisation, clustering and root-cause insights.

Project files
File	Description
Hanuai_Task2_EDA_TextMining.ipynb	Annotated notebook (already executed, outputs and charts included)
Hanuai_task2_assignment.csv	Input data (must sit next to the notebook to re-run it)
Hanuai_task2_tagged.xlsx	Tagged dataset. Grey headers = original data, green = extracted tags, blue = classifications. Yellow rows = the 5 provided example rows. Extra sheets: Tag_Dictionary, Tag_Frequency, Category_Summary, Cluster_Profile, Topic_Profile, Gold_Validation
Hanuai_task2_tagged.csv	Same tagged data as CSV (UTF-8 with BOM, opens correctly in Excel)
Hanuai_Task2_Report.docx / .pdf	Stakeholder report: data synthesis, actionable points with business impact, learnings and next steps
figures/	The 11 charts used in the notebook and report (PNG)
requirements.txt	Python packages needed to run the notebook
How to run the notebook
Install Python 3.10 or newer.
Put the notebook and Hanuai_task2_assignment.csv in the same folder and open that folder in VS Code or Jupyter.
Create and activate a virtual environment, then install the packages:
   python -m venv .venv

   # Windows
   .venv\Scripts\activate
   # Mac / Linux
   source .venv/bin/activate

   pip install -r requirements.txt
Open the notebook, select the .venv Python kernel and run all cells (about one minute).
Results are written to an outputs/ folder next to the notebook (tagged CSV and Excel, plus figures/).

Tested with pandas 3.x and scikit-learn 1.8. No internet access or model downloads are needed.

Notebook structure
EDA: data assessment, cleaning, critical columns, statistics and distributions
Text mining: free-text identification, normalisation (including Spanish/French terms), entity tagging, validation against the 5 example rows, issue categorisation
Insights: pareto of failures, trends, plant/make/model effects, K-Means and LDA, root-cause synthesis
Export: tagged CSV and Excel
Conclusions: key findings, hypotheses, limitations, next steps
Output columns (tagged dataset)
Original six tag columns (Trigger, Failure Component, Failure Condition, Additional Context, Fix Component, Fix Condition), now filled for all rows in the same list format as the examples
Symptoms (mined), Diagnosis (mined), Process Flags, DTC status: extra tags
Issue category: component failure, communication/network, software/calibration, electrical/wiring, assembly/build quality, no fault found
Symptom area: customer-facing function (camera, XM, phone, display and so on)
Complaint cluster / Root-cause topic: K-Means and LDA groupings
Days in service, Language, Data quality flags
Key assumptions and limitations
The six tag columns were empty except for 5 rows, so those rows were used as the schema and a small validation set (n = 5, directional only).
76 events have a claim opened before the in-service date. They are flagged and their days-in-service is left blank, not imputed.
Tagging uses a transparent keyword and regex dictionary, not a trained model. See the report for planned improvements.
There are no production volumes or cost data, so findings are shares of claims, not failure rates.
Sharing

Do not share the .venv/ folder. It is excluded by .gitignore, and anyone can recreate it with the steps above.