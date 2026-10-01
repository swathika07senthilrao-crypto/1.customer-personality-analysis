# 1.customer-personality-analysis
Customer Personality Analysis is a detailed analysis of a company's ideal customers. It helps a business to better understand its customers and makes it easier for them to modify products according to the specific needs, behaviors, and concerns of different types of customers.

# Data Cleaning Steps — Customer Personality Analysis
### Step 1: Missing Value Imputation
* Checked null count across all 29 features (`df.isnull().sum()`)
* Identified 24 missing values in `Income` (~1.07% of dataset).
* Imputed missing `Income` values using the median ($51,381.50) via `df['Income'].fillna(df['Income'].median()).

### Step 2: Duplicate Verification
* Verified row-level duplicates using `df.duplicated().sum()` (0 duplicates found).
* Verified primary key uniqueness via `df['ID'].nunique()` (2,240 unique IDs).

### Step 3: Text & Category Standardization
* Trimmed extra spaces and applied Title Case to string columns using `.str.strip().str.title().
* Standardized non-standard categories in `Marital_Status` (`Alone` → `Single`, `Absurd`/`YOLO` → `Other`).

### Step 4: Column Header Formatting
* Converted all 29 column headers to lowercase, stripped whitespaces, and replaced spaces with clean underscores using `df.columns.str.strip().str.lower().str.replace(' ', '_').

### Step 5: Date Parsing & Data Type Casting
* Parsed `dt_customer` from string object to Pandas `datetime64[ns]` format using `pd.to_datetime().
* Validated and cast integer/numeric data types across identifier, count, and continuous columns.
