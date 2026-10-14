# ISYS2001-Assessment-2-Programming-Assignment-Matthias-Vanwolleghem

**Course**: ISYS2001 Introduction to Business Programming  
**Author**: Matthias Vanwolleghem  
**Project**: Assessment 2: Programming Assignment

----------

## Project vverview
The Personal Spending Analyser is an application that cleans CSV files, sums category totals, converts spending into a relatable beer converter ($10/beer) and delivers  budgeting advice via an AI Financial Coach powered by Google's Gemini.

----------

## Planned features
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

## Security
The Gemini API key is stored using Google Colab Secrets (`GEMINI_API_KEY`)

----------

## Execution status
[x] step 1: problem definition and context
[x] step 2: inputs and outputs
[x] step 3: example by hand
[x] step 4: pseudocode
[o] step 5: python implementation
[o] step 6: testing

