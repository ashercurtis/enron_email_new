# ACCTG 522 Enron email audit

Open `Enron_Email_Audit_Student.ipynb` for the runnable lab and `Enron_Email_Audit_Instructor.ipynb` for the same sequence with facilitation notes and actual outputs. Keep `Cybersecurity_case_studies_Enron.csv` beside the notebooks. The original CSV is unchanged.

## Setup

Python 3.10+ recommended. In a terminal, create a local environment with `python -m venv .venv`, then install with `.venv\Scripts\python -m pip install -r requirements.txt` on Windows (use `.venv/bin/python` on macOS/Linux). In VS Code install the Jupyter extension and select this environment as the notebook kernel. Run all cells in order.

In Google Colab, open a notebook and upload the CSV to the runtime when prompted, only if institutional data-use rules permit. pandas and matplotlib are normally preinstalled. Runtime files are temporary. Use local VS Code when uploading is not authorized. No API keys or paid services are needed.

## Classroom use

Module 1 (50 min): framing 5, single-email parsing 15, full-data validation 15, time summaries 15. Break 10 min. Module 2 (50 min): search/PII 12, credentials 10, competitor screening 10, independent investigation 18. Run worked defaults first, then change only patterns or keywords in Try it activities. Optional thread/encoding and language extensions can be assigned later.

Policies, PII categories, and competitor names are illustrative assumptions. Matches screen records for review; they establish neither disclosure nor policy violations. Preserve quoted text as the default search scope. The subject cannot reliably be separated from the body after flattening. Attachment references do not supply attachment contents.

Keep the dataset and executed notebook excerpts private; clear outputs before distributing notebooks outside the authorized classroom. Never commit the CSV, upload it to external analysis services, or send its contents to an LLM API. The instructor must review ambiguous examples, hypothetical policy scope, competitor names, and any excerpts before class. See the validation report below for measured results.

## Validation on the supplied CSV

Both notebooks executed end to end locally with Python 3.11, pandas 3.0.6, and matplotlib 3.11.2. The CSV has 26,751 data records and one original column. There are no empty records, unsuccessful header/body splits, outer metadata extraction failures, date failures, or duplicate MessageIDs. Exact header/body reconstruction passed. Synthetic tests verified quoted metadata boundaries, display-name senders with leading-dot addresses, mixed-offset local hours versus UTC, malformed dates, and record-versus-occurrence counts.

Recorded local date coverage: 2000-11-01 to 2002-06-25. UTC coverage: 2000-11-01 19:29:00+00:00 to 2002-06-25 14:51:14+00:00. Conservative address-format flags affect 5,711 sender records and 1,885 recipient records; supplied strings remain unchanged. These flags require contextual review rather than automatic repair.

The CSV SHA-256 remained `dfc6df879b44bad72a3320ad5c06c2ce58ad0e46fed3fc16d73423414400c58f` before and after execution. No data was committed or sent to an analysis service or LLM API. Colab compatibility is implemented through standard notebook code and a conditional upload fallback; execution was verified locally, not in a live Colab runtime.

The instructor notebook includes measured search counts and inspected ambiguous examples. Remaining instructor decisions are policy definitions, illustrative competitor names, permission for cloud use, and suitability/redaction of excerpts. Saved outputs contain dataset text and should be cleared before unauthorized distribution. `.build/` contains local authoring/validation tools only; neither notebook depends on it. `.venv/` is the local environment. For independent notebook execution validation, optionally install `nbclient` and `nbformat`; these are not required for classroom analysis.
