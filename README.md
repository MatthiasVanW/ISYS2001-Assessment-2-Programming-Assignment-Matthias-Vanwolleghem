# ISYS2001-Assessment-2-Programming-Assignment-Matthias-Vanwolleghem

**Course**: ISYS2001 Introduction to Business Programming  
**Author**: Matthias Vanwolleghem  
**Project**: Assessment 2: Programming Assignment

----------

## Project overview
The Personal Spending Analyser is an application that cleans CSV files, sums category totals, converts spending into a relatable beer converter ($10/beer) and delivers  budgeting advice via an AI Financial Coach powered by Google's Gemini.

<img width="1240" height="538" alt="image" src="https://github.com/user-attachments/assets/bae93455-b9ad-4527-9886-0d3db501ec87" />

----------

## Key features
- CSV data cleaning: strip currency symbols (`$`) and handle bad data using Pandas.
- Class-based design: use custom `Transaction`and `FinanceManager`classes to manage data.
- Beer converter tool: converts spending into equivalent beers (\$10 per beer).
- AI financial coach: provide advice using Gemini API
- Gradio interface: simple UI for uploads and chatting with financial coach

----------

## Repository structure
- `ISYS2001_Programming_Assignment_Matthias_Vanwolleghem.ipynb`: Main  notebook containing the six-step method, API setup and core code.
- `DEVELOPERS_DIARY.md`: Chronological log tracking daily progress, AI help and reasoning.
- `README.md`: Project overview, features and navigation guide.

----------

## Setup & Installation Instructions

1. **Open in Google Colab**:
   Open `ISYS2001_Programming_Assignment_Matthias_Vanwolleghem.ipynb` in Google Colab.

2. **Run the Colab**:
   Execute all code cells sequentially from top to bottom. The required packages, classes and dependencies will automatically install and initialize in sequence, leading smoothly to the launch of the interactive Gradio UI.

----------

## Testing

The application was subjected to critical edge-case tests to ensure accuracy:

**All corresponding screenshots and visual execution outputs for these tests are documented directly within the Notebook (`ISYS2001_Programming_Assignment_Matthias_Vanwolleghem.ipynb`) under Step 6.**

| Test # | Test Name | Scenario Description | Expected & Verified Result |
| :--- | :--- | :--- | :--- |
| **1** | **Data Formatting Consistency** | Testing date variations (e.g., `DD/MM/YYYY` vs `YYYY-MM-DD`). | Standardized into uniform datetime objects using `pd.to_datetime(..., dayfirst=True)`. |
| **2** | **Decimal & Separator Compatibility** | Ingesting European Excel CSVs using semicolons (`;`) and comma decimals (`$45,50`). | Delimiters autodetected via `sep=None` and commas cleaned to standard floats without throwing parsing errors. |
| **3** | **API Limit / Error Handling** | Simulating HTTP 429 Quota Exceeded and 503 Server Unavailable responses from Gemini API. | Intercepted, displaying offline fallback advice and UI notices without crashing. |
| **4** | **Missing Data** | CSV containing `NaN` or incomplete fields. | Incomplete rows filtered out dynamically without halting execution. |
| **5** | **Extra Columns** | CSV containing unexpected extra metadata headers. | Non-essential columns ignored; required target columns correctly processed. |
| **6** | **Scalability (1,000 Rows)** | Stress testing single-row vs. 1,000 duplicated rows. | Flawless calculation ($19,000 Rent sum verified with 0% data drift). |
| **7** | **Invalid File Type** | Uploading non-CSV files (ex. `.txt`). | Intercepted upfront with clear UI message: `Invalid file type. Only .csv allowed.` |
| **8** | **Beer Price Edge Cases** | Entering $0 or negative values (ex. `-5`). | $0 outputs `0 beers` safely; negative values apply `abs()` conversion without crashing. |

----------

## Security
The Gemini API key is securely retrieved via Google Colab Secrets (`userdata.get('GEMINI_API_KEY')`). No hardcoded API keys or sensitive credentials are present in the code or repository.

----------

## Execution status
- [x] step 1: problem definition and context
- [x] step 2: inputs and outputs
- [x] step 3: example by hand
- [x] step 4: pseudocode
- [x] step 5: python implementation
- [x] step 6: testing

