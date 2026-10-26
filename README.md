# Exploratory Data Analysis & Visualization (EDAV) Course-End Project

An end-to-end data analysis and visualization pipeline analyzing building energy consumption, weather patterns, and meter readings. This project demonstrates core data manipulation, time-series transformation, wrangling, and multi-faceted visualization using Python, NumPy, Pandas, Matplotlib, and Seaborn.

---

## Repository Structure & Datasets

### Datasets
* `building_info.csv`: Metadata regarding building properties, primary use types, square footage, and structural characteristics.
* `weather_info.csv`: Environmental conditions including outdoor temperatures, humidity, wind speed, and precipitation.
* `meters_info.csv`: High-frequency meter telemetry recording energy consumption metrics across building sites.

---

##  Unit-by-Unit Functionality Breakdown

### Unit 1: NumPy Basics (`UNIT1_numpybasics.py`)
* **Core Functionalities**:
  * Multi-dimensional array structures (`np.ndarray`), matrix operations, and vectorized math.
  * Array broadcasting, boolean masking, slicing, and index filtering.
  * Statistical summaries (`np.mean`, `np.median`, `np.std`, `np.percentile`) and mathematical normalizations.
* **Dataset Application**:
  * Extracted raw energy usage and weather readings into vector arrays to evaluate low-level numerical properties, basic array-level transforms, and baseline statistics without DataFrame overhead.

### Unit 2: Pandas Foundations (`UNIT2_pandas_foundations.py`)
* **Core Functionalities**:
  * Schema ingestion via `pd.read_csv`, structural diagnostics (`.info()`, `.describe()`, `.shape`, `.dtypes`).
  * Explicit row/column access via `.loc[]`, `.iloc[]`, conditional filtering, and column projections.
  * Sorting, indexing, and basic descriptive summaries on structured tabular data.
* **Dataset Application**:
  * Loaded `building_info.csv`, `meters_info.csv`, and `weather_info.csv`.
  * Profiled building square footage distributions, identified unique primary use categories, and inspected initial meter data ranges.

### Unit 3: Cleaning & Data Wrangling (`UNIT3_cleaning_and_wrangling.py`)
* **Core Functionalities**:
  * Null-value handling (`.isna()`, `.fillna()`, `.dropna()`) and duplicate deduplication (`.drop_duplicates()`).
  * Data type casting, categorical standardization, and string cleaning.
  * Relational table operations via `pd.merge()` (inner/left joins across shared keys) and data reshapes (`.melt()`, `.pivot()`).
* **Dataset Application**:
  * Handled missing meteorological data (e.g., forward-filling weather gaps).
  * Merged meter readings with corresponding building properties (`building_id`) and timestamped weather records (`timestamp`) to produce a consolidated analysis dataset.

### Unit 4: Aggregation & Time Series (`UNIT4_aggregation_and_timeseries.py`)
* **Core Functionalities**:
  * Datetime parsing (`pd.to_datetime`), index-based time slicing, and component extraction (hour, day of week, month).
  * Resampling and frequency conversion (`.resample('D')`, `.resample('M')`) and rolling window transforms (`.rolling().mean()`).
  * Multi-level groupings using `.groupby()` paired with aggregate functions (`.agg()`).
* **Dataset Application**:
  * Resampled high-frequency meter telemetry into hourly, daily, and monthly aggregate consumption baselines.
  * Evaluated diurnal load profiles (weekday vs. weekend consumption cycles) across distinct building use types (e.g., Education, Office, Commercial).

### Unit 5: Data Visualization (`UNIT5_visualization.py`)
* **Core Functionalities**:
  * Distribution analysis: Histograms, Kernel Density Estimation (KDE), and Box plots (`sns.boxplot`).
  * Relational & categorical inspection: Scatter plots (`sns.scatterplot`), line charts (`plt.plot`), and bar charts.
  * Correlation & multi-variable analysis: Heatmaps (`sns.heatmap`) for correlation matrices and multi-panel FacetGrids.
* **Dataset Application**:
  * Plotted correlation heatmaps between outside temperature and aggregate electrical load.
  * Visualized hourly peak load profiles by building category and identified usage anomalies across seasonal transitions.

---

##  User Instructions

### 1. Prerequisites
Ensure you have Python 3.8+ installed on your system.

### 2. Clone the Repository
```bash
git clone [https://github.com/suprita-sahu/EDAV_CourseEndProject.git](https://github.com/suprita-sahu/EDAV_CourseEndProject.git)
cd EDAV_CourseEndProject
```

### 3. Set Up Environment & Install Dependencies

```bash
# Create virtual environment
python -m venv venv

# Activate on Windows (Command Prompt / PowerShell)
venv\Scripts\activate
# Or on Linux / macOS:
# source venv/bin/activate

# Install dependencies
pip install numpy pandas matplotlib seaborn
```

### 4. Running the Units

```bash
python UNIT1_numpybasics.py
python UNIT2_pandas_foundations.py
python UNIT3_cleaning_and_wrangling.py
python UNIT4_aggregation_and_timeseries.py
python UNIT5_visualization.py
```
