# CIA Country Analysis and Clustering

## Overview

This project performs exploratory data analysis and unsupervised clustering on country-level data sourced from the CIA World Factbook. The goal is to identify patterns and group countries based on shared socioeconomic and geographic characteristics, then visualize the resulting clusters on an interactive world map.

## Dataset

The dataset contains information on countries across the following features:

- **Country** and **Region**
- **Population** and **Area (sq. mi.)**
- **Population Density** (per sq. mi.)
- **Coastline** (coast/area ratio)
- **Net Migration**
- **Infant Mortality** (per 1000 births)
- **GDP** ($ per capita)
- **Literacy** (%)
- **Phones** (per 1000)
- **Arable, Crops, and Other** land percentages
- **Climate**
- **Birthrate** and **Deathrate**
- **Agriculture, Industry, and Service** sector shares

A secondary file (`country_iso_codes.csv`) is used to map country names to ISO codes for choropleth map rendering.

## Project Structure

```
CIA-Country-Analysis-And-Clustering/
|-- CIA Country Analysis And Clustering.ipynb   # Main analysis notebook
|-- DATA/
    |-- CIA_Country_Facts.csv                   # Primary dataset
    |-- country_iso_codes.csv                   # Country ISO code mapping
```

## Methodology

### 1. Exploratory Data Analysis

- Inspected dataset shape, types, and summary statistics
- Identified and visualized missing values
- Plotted population distributions, GDP by region, and GDP vs. literacy scatter plots
- Generated a correlation heatmap across all numeric features

### 2. Data Preprocessing

- Filled missing agriculture values with zero where applicable
- Imputed missing climate and literacy values using regional group means
- Dropped remaining rows with missing data
- Encoded categorical variables using one-hot encoding
- Scaled all features using StandardScaler

### 3. Clustering

- Applied K-Means clustering across a range of cluster counts (k = 2 to 30)
- Used the elbow method (sum of squared distances) to identify a suitable number of clusters
- Selected k = 3 as the primary model for interpretability
- Analyzed feature correlations with cluster labels to understand what drives group separation

### 4. Visualization

- Rendered cluster assignments on an interactive choropleth world map using Plotly Express
- Countries are colored by cluster, with hover information showing country names

## Requirements

- Python 3.x
- pandas
- matplotlib
- seaborn
- scikit-learn
- plotly

Install dependencies with:

```bash
pip install pandas matplotlib seaborn scikit-learn plotly
```

## Usage

Open the notebook in Jupyter and run all cells in order:

```bash
jupyter notebook "CIA Country Analysis And Clustering.ipynb"
```

## Results

Countries are grouped into three clusters that broadly correspond to levels of economic development and geographic characteristics. The choropleth map provides a clear visual summary of how clusters are distributed across regions of the world.
