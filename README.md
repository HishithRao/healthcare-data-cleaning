# 🏥 Healthcare Data Cleaning Pipeline

A robust, multi-level data cleaning and validation pipeline built in Python using Pandas and NumPy. This project standardizes raw, messy healthcare tracking entries into an enterprise-grade dataset optimized for analytical processing and machine learning modeling.

---

## 🚀 Getting Started

You can run this pipeline instantly using Google Colab without any local system installation requirements:

1. Click the **Open in Colab** badge located at the top of the notebook.
2. Ensure you place your raw `healthcare_dataset.csv` file into your Google Drive home directory or upload it via the native file upload widget.
3. Run the notebook execution cells sequentially from Level 1 to Level 4.

---

## 🛠️ Pipeline Architecture & Methodology

The validation pipeline enforces cleaning criteria across four strict operational tiers:

### 🧩 Level 1 — Structural Integrity
* **Case Standardization**: Normalizes raw column definitions to lowercase `snake_case` notation to guarantee robust programmatic property lookups.
* **Temporal Type Conversions**: Casts unstructured textual dates into explicit `datetime64[ns]` timestamp tracking objects.
* **De-duplication**: Discovers and drops raw row-level records that represent redundant database logging entries.

### 🔠 Level 2 — Value-Level Cleaning
* **Text Normalization**: Standardizes messy, random casing variants in patient names and service fields into standard `Title Case`.
* **String Sanitization**: Trims out unexpected whitespace padding surrounding transactional text metrics.
* **Boundary Validation**: Validates categorical fields (such as `gender`, `blood_type`, and `test_results`) against strict sets of valid domain terms.

### ⚖️ Level 3 — Business Rule Verification
* **Financial Protection**: Intercepts rows displaying non-positive or negative `billing_amount` values, tagging them with an explicit `billing_flag` attribute instead of blindly deleting them.
* **Chronological Audits**: Verifies that no transaction states contain invalid medical dates where patient discharge records precede admission timestamps.
* **Feature Engineering**: Derives a new statistical variable tracking a patient's numerical `length_of_stay_days`.

### 💾 Level 4 — Export & Automated Documentation
* **Data Persistence**: Formats and exports the final valid memory matrix out to a portable spreadsheet structure called `healthcare_dataset_cleaned.csv`.
* **Reproducibility Log**: Programmatically writes a local summary report documenting precise raw row transformations for transparent project reporting.

---

## 📈 Performance & Results Metrics

The complete data transformation and metric records resulting from the pipeline run can be viewed directly in the generated [Data Cleaning Log](data_cleaning_log.md) file inside this repository.
