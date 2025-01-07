# Lake View Township Broadway Corridor Analysis

This repository contains an analysis of potential property tax revenue impacts from rezoning the Broadway corridor in Lake View Township, Chicago.

## Setup

1. Install R and required packages:
```R
install.packages(c("tidyverse", "knitr", "scales", "ggplot2", "DBI", "RSQLite"))
```

2. Download the Cook County Property Tax Database (PTAXSIM):

The PTAXSIM database is a comprehensive SQLite database containing Cook County property tax data. To get the database:

```R
# In R, run:
download.file(
  "https://ptaxsim.s3.amazonaws.com/ptaxsim.db", 
  "ptaxsim.db",
  mode = "wb"  # Binary mode for Windows compatibility
)
```

The download is approximately **8.8GB** in size. The database file will be saved as `ptaxsim.db` in your project directory.

If you encounter any issues with the direct download, you can:
1. Visit https://ptaxsim.s3.amazonaws.com/ptaxsim.db in your browser
2. Save the file as `ptaxsim.db` in your project directory

For more information about PTAXSIM, visit the [Cook County Assessor's Office GitHub repository](https://github.com/ccao-data/ptaxsim).

## Running the Analysis

Open `lakeview_corridor_analysis.Rmd` in RStudio and click "Knit" to generate the analysis report. The analysis will:

1. Connect to the property tax database
2. Analyze current property values in Lake View Township
3. Calculate potential tax revenue under different development scenarios
4. Generate visualizations of the results

## Data Source

The analysis uses the Cook County Property Tax Simulator database (PTAXSIM), which is hosted on AWS S3. The database is not included in this repository due to its size (**~8.8GB**), but can be downloaded using the R command in the Setup section above. PTAXSIM contains historical Cook County property tax data including assessed values, exemptions, tax rates, and final tax bills for all parcels in Cook County.
