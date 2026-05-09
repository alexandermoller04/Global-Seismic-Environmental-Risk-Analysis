# 🌍 Global Seismic & Environmental Risk Analysis

* **Project**: Data Science Capstone Project
* **Authors**: Alexander Moller, Kerven Zephir, Racquel Christie, & Britney Antoine
* **Institution**: Florida Atlantic University
* **Dataset Regions**: North America | South America | Asia | Oceania

---

## Table of Contents
* [About the Project](#about-the-project)
* [Objective](#objective)
* [Datasets](#datasets)
* [Methods & Models](#methods--models)
* [Key Findings](#key-findings)
* [Challenges](#challenges)
* [Improvements](#improvements)

---

## About the Project

The Global Seismic & Environmental Risk Analysis is an unsupervised machine learning project that explores the relationship between seismic activity and environmental factors (CO2 emissions, fossil fuel production, and population density). 
By integrating multiple datasets, the project uncovers geographic and environmental patterns that profiles similarities between seismic events as a means for risk management in the Ring of Fire.

---

## Objective

The objective of this project is to identify and visualize hidden patterns between seismic events and environmental variables across the globe. By applying clustering, similarity, and density estimation techniques, the project aims to:

- Group countries by their seismic and environmental risk profiles
- Detect correlations between natural hazards (earthquakes, tsunamis, volcanoes) and human-driven environmental factors
- Surface seasonal and geographic trends in seismic event occurrences across multiple world regions

---

## Datasets

* **Earthquake Dataset**: Global seismic event records including magnitude, depth, alert level, date/time, and country
* **Environmental Dataset**: Country-level CO2 emission rates, gas/coal/oil production, population density, volcanic coordinates, and elevation

### Dataset Split by Region:
* 🌎 **South America**
* 🌎 **North America**
* 🌏 **Asia**
* 🌏 **Oceania**

---

## Methods & Models

### 🔹 Exploratory Data Analysis
* Grouped earthquake counts and average magnitudes by country to identify spatially frequent seismic zones
* Parsed `date_time` into seasonal categories (Spring, Summer, Fall, Winter) to detect seasonal seismic trends
* Mapped alert levels (Green, Yellow, Orange) by country using stacked bar charts

### 🔹 Cosine Similarity
* Engineered a country-level feature matrix combining quake count, average magnitude, and alert level distributions
* Applied **Cosine Similarity** to identify countries with statistically analogous seismic risk profiles
* Visualized results as a heatmap matrix across all countries

### 🔹 K-Means Clustering
* Applied **K-Means (k=3)** on population density and CO2 emission rates to segment countries into distinct environmental risk clusters
* Used the **Elbow Method** (SSE vs. K) to determine the optimal number of clusters
* Applied **MinMaxScaler** to normalize features prior to clustering

### 🔹 Hierarchical Clustering
* Performed **Ward Linkage** hierarchical clustering on 13 combined geographic and environmental features
* Visualized cluster relationships through a **Dendrogram** to interpret feature groupings and distances

### 🔹 Kernel Density Estimation (KDE)
* Fit a **Cosine Kernel Density model** on country code and magnitude to estimate probability distribution of seismic activity
* Overlaid KDE plots with scatter points for interpretability

### 🔹 Correlation Analysis
* Produced a **Correlation Heatmap** across 13 environmental and seismic variables
* Identified key feature relationships to guide further modeling

---

## Key Findings

* **Tsunami & Magnitude**: Strong positive correlation
* **Elevation & Volcanic Coordinates**: Medium correlation
* **Earthquake Latitude & Depth**: Medium correlation
* **Seasonal Patterns**: Seismic event frequency was relatively consistent across seasons
* **Clustering**: K-Means identified three distinct country profiles — low-density/low-emission, high-density/moderate-emission, and outlier high-emission nations

---

## Challenges

1. **Multi-Dataset Integration**
   * *Challenge*: Merging earthquake and environmental datasets across four regions with inconsistent formatting differences.
   * *Solution*: Standardized column types and applied consistent preprocessing pipelines per region.

2. **Feature Scaling**
   * *Challenge*: CO2 emission rates and population density operated on vastly different scales, distorting K-Means cluster centers.
   * *Solution*: Applied MinMaxScaler to normalize the features

---

## 🔍 Improvements

* **Predictive Modeling**: Incorporate different supervised models to predict alert levels or tsunami likelihood based on environmental and seismic features
* **Time-Series Analysis**: Expand seasonal analysis into a full time-series model to forecast seismic activity trends in the future
