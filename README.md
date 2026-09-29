# Student Performance Analysis

## Project Overview

This project performs **student performance analysis using Python, Pandas, NumPy, Matplotlib, and Seaborn**. The notebook loads student performance data, cleans categorical features, calculates statistical measures, creates overall performance metrics, categorises students into performance bands, and identifies extreme performance outliers.

The project is designed as a practical data-analysis workflow for understanding students' marks in **Mathematics, Reading, and Writing**.

## Objectives

- Load and inspect the student performance dataset.
- Understand the structure and basic statistics of the data.
- Check for missing values and duplicate records.
- Clean and standardise categorical features.
- Calculate mean, median, standard deviation, quartiles, and IQR.
- Calculate each student's total score and percentage.
- Assign a performance band based on percentage.
- Detect unusual or extreme scores using IQR and Z-score methods.
- Visualise score distributions using box plots.

## Technologies Used

- **Python**
- **Pandas** – data loading, cleaning, transformation, and analysis
- **NumPy** – numerical operations
- **Matplotlib** – data visualisation
- **Seaborn** – statistical visualisation
- **Jupyter Notebook** – development and analysis environment

## Project Files

| File | Description |
|---|---|
| `week_7 (1).ipynb` | Jupyter Notebook containing the complete analysis |
| `Studentperformance_preprocessed.csv` | Preprocessed student performance dataset |
| `README.md` | Project documentation |

## Dataset

The uploaded CSV contains **1,000 student records and 16 columns**.

### Main Dataset Features

| Column | Description |
|---|---|
| `gender` | Student gender |
| `race/ethnicity` | Student's race/ethnicity group |
| `parental level of education` | Parent's education level |
| `lunch` | Lunch programme/category |
| `test preparation course` | Test preparation status |
| `math score` | Mathematics score |
| `reading score` | Reading score |
| `writing score` | Writing score |
| `Total Score` | Sum of the three subject scores |
| `Percentage` | Overall percentage calculated from total score |
| `Performance Band` | Performance category based on percentage |
| `math score outlier` | Mathematics outlier status |
| `reading score outlier` | Reading outlier status |
| `writing score outlier` | Writing outlier status |
| `Total Score outlier` | Total-score outlier status |
| `Outlier Subjects` | Number of subjects in which the student is flagged as an outlier |

## Analysis Workflow

### 1. Data Loading and Inspection

The notebook imports the required Python libraries and loads the student dataset using Pandas.

Initial inspection includes:

- First records using `head()`
- Last records using `tail()`
- Dataset information using `info()`
- Descriptive statistics using `describe()`
- Dataset dimensions using `shape`
- Missing-value checking using `isnull().sum()`
- Column-name inspection

### 2. Categorical Data Cleaning

The categorical columns are standardised by:

- Removing unnecessary spaces.
- Collapsing repeated spaces.
- Converting text to a consistent case.
- Standardising known category variations.
- Checking duplicate records.
- Removing duplicate rows.
- Converting categorical columns to Pandas `category` data type.

The cleaned categorical fields are:

- Gender
- Race/Ethnicity
- Parental Level of Education
- Lunch
- Test Preparation Course

### 3. Statistical Analysis

The notebook analyses the three subject-score columns:

- Mathematics
- Reading
- Writing

The following statistical measures are calculated:

- Mean
- Median
- Standard deviation
- First quartile (Q1)
- Second quartile (Q2)
- Third quartile (Q3)
- Interquartile Range (IQR)

These measures help describe the distribution and variation of student scores.

### 4. Total Score and Percentage

A student's total score is calculated as:

```text
Total Score = Math Score + Reading Score + Writing Score
```

Since each subject has a maximum score of 100:

```text
Percentage = (Total Score / 300) × 100
```

A `Performance Band` is also created using the percentage.

| Percentage Range | Performance Band |
|---|---|
| Below 40% | Fail |
| 40%–60% | Average |
| 60%–75% | Good |
| 75%–90% | Very Good |
| 90% and above | Excellent |

### 5. Outlier Detection

The project uses two approaches to identify unusual performance:

#### IQR Method

The standard IQR rule uses:

```text
Lower Bound = Q1 - 1.5 × IQR
Upper Bound = Q3 + 1.5 × IQR
```

Scores outside these limits are flagged as outliers.

The notebook also checks an extreme outlier threshold using:

```text
Q1 - 3 × IQR
Q3 + 3 × IQR
```

#### Z-Score Method

The notebook also identifies observations where:

```text
|Z-score| > 3
```

Outlier analysis is performed for:

- Math score
- Reading score
- Writing score
- Total Score

Students can also be identified as outliers in two or more subjects.

### 6. Data Visualisation

Box plots are used to visualise:

- Distribution of Mathematics, Reading, and Writing scores.
- Distribution of overall percentage.
- Potential IQR-based outliers.

These visualisations make unusual values and score distributions easier to understand.

## Key Outputs

The notebook creates the following important analysis objects:

| Object | Purpose |
|---|---|
| `summary_stats` | Statistical summary of subject scores |
| `outlier_summary` | Outlier counts and IQR/Z-score limits |
| `outliers` | Students flagged as outliers in at least one area |
| `multi` | Students flagged as outliers in two or more subjects |
| `Performance Band` | Overall performance category |
| `Total Score` | Combined score across three subjects |
| `Percentage` | Overall percentage |

## How to Run the Project

### 1. Install Python

Install Python 3.x from the official Python website or use Anaconda.

### 2. Install Required Libraries

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### 3. Open Jupyter Notebook

```bash
jupyter notebook
```

### 4. Open the Notebook

Open:

```text
week_7 (1).ipynb
```

### 5. Dataset Path

The notebook's original data-loading cell uses a Google Drive path. If you run the project locally, update the CSV path to the location of:

```text
Studentperformance_preprocessed.csv
```

For example:

```python
df = pd.read_csv("Studentperformance_preprocessed.csv")
```

Then run the notebook cells from top to bottom.

## Project Outcome

The project produces a structured analysis of student academic performance. It combines data cleaning, descriptive statistics, derived performance measures, categorical performance bands, outlier detection, and visualisation in a single Python workflow.

## Conclusion

This project demonstrates how Python-based data analysis can be used to examine student performance systematically. The analysis provides statistical summaries, overall performance measures, performance categories, and outlier information that can help users understand patterns in student scores.

## Author

**Mukesh Krishna**
