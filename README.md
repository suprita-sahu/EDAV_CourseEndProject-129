# Exploratory Data Analysis & Visualization (EDAV) - Course-End Project

An exploratory data analysis and visualization pipeline analyzing building energy consumption, weather conditions, and structural metadata using **NumPy**, **Pandas**, **Matplotlib**, and **Seaborn**.

---

## Datasets Overview

The project utilizes three datasets scaled to **100 rows** each:

1. **`building_info.csv`** (100 rows)
   - `building_id`: Unique identifier for each building (1 to 100)
   - `primary_use`: Building sector type (`Education`, `Office`, `Commercial`)
   - `square_feet`: Total gross floor area
   - `year_built`: Construction year
   - `floor_count`: Number of floors

2. **`weather_info.csv`** (100 rows)
   - `timestamp`: Chronological hourly timestamps
   - `air_temperature`: Outdoor air temperature (°C)
   - `dew_temperature`: Dew point temperature (°C)
   - `wind_speed`: Wind speed (m/s)
   - `precip_depth_1_hr`: 1-hour liquid precipitation accumulation (mm)

3. **`meters_info.csv`** (100 rows)
   - `building_id`: Foreign key referencing `building_info.csv`
   - `meter`: Type of meter (`0` = electricity)
   - `timestamp`: Measurement timestamp
   - `meter_reading`: Energy consumption reading in kWh

---

## Units Covered

### Unit 1: NumPy Basics
- Loading raw telemetry into NumPy arrays
- Calculating statistical summaries: `mean`, `median`, `std`, and percentiles
- Boolean masking and conditional filtering (`meter_reading > 200`)
- Vectorized Min-Max normalization on environmental metrics

### Unit 2: Pandas Foundations
- Ingesting CSV files into DataFrames (`pd.read_csv`)
- Structural diagnostics using `.info()`, `.describe()`, and `.shape`
- Data subsetting using `.loc` and `.iloc`
- Multi-condition filtering and column projection

### Unit 3: Cleaning & Data Wrangling
- Identifying missing values (`.isna().sum()`)
- Sequential forward-fill (`.ffill()`) and duplicate dropping (`.drop_duplicates()`)
- Datetime type casting using `pd.to_datetime()`
- Relational database merges: joining meter data with building specs and weather conditions

### Unit 4: Aggregation & Time Series Analysis
- Feature extraction from datetime (`hour`, `day_name`, `is_weekend`)
- Multi-level group aggregations (`.groupby('primary_use').agg(...)`)
- Downsampling and time-frequency resampling (`.resample('h')`)
- Rolling window calculations (3-hour moving averages)

### Unit 5: Data Visualization
- **Boxplot**: Energy distribution across building use types (`sns.boxplot`)
- **Line Plot**: Diurnal 24-hour mean hourly energy consumption profile (`sns.lineplot`)
- **Correlation Heatmap**: Pearson correlation between consumption and environmental factors (`sns.heatmap`)

---

## Setup & Execution

1. Clone the repository:
   ```bash
   git clone [https://github.com/suprita-sahu/EDAV_CourseEndProject.git](https://github.com/suprita-sahu/EDAV_CourseEndProject.git)
   cd EDAV_CourseEndProject
   ```
2. Install dependencies:
   pip install numpy pandas matplotlib seaborn
   
3.Run the pipeline:
python edav_pipeline.py
