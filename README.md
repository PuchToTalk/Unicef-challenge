# Mobility Analysis During Crisis: Understanding Vulnerable Areas and Trends

## Project Overview

This project analyzes mobility data during a crisis (e.g., COVID-19 lockdown) to understand trends, identify vulnerable areas where mobility restrictions were ineffective, and evaluate patterns of movement. By combining spatial analysis, clustering, feature engineering, and machine learning, we provide actionable insights.

## Objectives
	•	Analyze Mobility Trends Over Time: Identify peaks and drops in mobility across different days and time windows.
	•	Cluster Areas with Similar Behavior: Group areas based on origin-destination coordinates to identify zones with persistent movement.
	•	Identify Vulnerable Areas: Highlight regions with the highest mobility increases during the crisis.
	•	Predict Reduction (%): Use machine learning to explain and predict mobility reduction based on key features.

## Dataset

The mobility data contains the following:
	•	Baseline: Pre-crisis mobility count.
	•	Crisis: Mobility count during the crisis.
	•	x0, y0: Origin coordinates (longitude, latitude).
	•	x1, y1: Destination coordinates (longitude, latitude).
	•	time_window: 8-hour intervals for each day (e.g., day1_0000, day1_0800).

## Key Steps

1. Data Cleaning and Feature Engineering
	•	Calculated Distance between origin and destination points.
	•	Extracted Time of Day from time_window:
	•	Night (00:00–08:00), Day (08:00–16:00), and Evening (16:00–00:00).
	•	Extracted Day Numbers (e.g., day1, day2).
	•	Created Crisis-to-Baseline Ratio to measure relative mobility changes.
	•	Categorized Reduction (%) into:
	•	High Reduction, Medium Reduction, and Low Reduction.

2. Exploratory Data Analysis (EDA)

Mobility Trends Over Time
	•	Visualizations:
	•	Line charts comparing Baseline and Crisis mobility over days.
	•	Change (%) trends across different time windows.

Insights:
	•	Mobility peaked on Day 4 across all time windows.
	•	08:00–16:00 had the highest mobility increases.
	•	Mobility declined sharply on Days 6 and 7, possibly due to policy enforcement.

Heatmaps for Vulnerable Areas
	•	Origin Heatmap: Shows regions where movement originates and increased significantly.
	•	Destination Heatmap: Highlights zones where mobility terminates.

Key Finding:
	•	The upper-right region (Longitude ~65.5–66.0, Latitude ~12.5–13.0) is the most vulnerable hotspot.
	•	The lower-left region also showed moderate vulnerability.

3. Clustering of Mobility Patterns
	•	Applied KMeans Clustering to spatial coordinates (x0, y0, x1, y1).
	•	Identified 4 clusters:
	•	Clusters 1 and 2: High-mobility zones, concentrated in the upper-right region.
	•	Cluster 3: Low-mobility zones with better adherence to restrictions.

Visualizations:
	•	Scatter plots of origin and destination clusters.
	•	Heatmaps highlighting mobility hotspots.

4. Machine Learning: Predicting Reduction (%)
	•	Model: Random Forest Regressor.
	•	Features:
	•	Baseline, Crisis, Distance, Day, Crisis-to-Baseline Ratio, and Time of Day.

Performance:
	•	Mean Absolute Error: 0.04
	•	R-squared: 1.00 (perfect prediction).

Cross-Validation:
	•	Achieved consistent R² scores, verifying the model’s robustness.

Key Insights
	•	Mobility increased significantly in vulnerable areas, with the upper-right region being the most critical hotspot.
	•	The 08:00–16:00 time window had the highest mobility activity.
	•	Clusters identified high-mobility zones and regions of lower compliance.
	•	Baseline mobility, crisis mobility, and distance were the most important predictors of reduction.

Recommendations
	1.	Focus mobility control efforts on the upper-right region where mobility persists.
	2.	Prioritize interventions during the 08:00–16:00 time window to reduce daytime activity.
	3.	Monitor and enforce restrictions in high-mobility origin and destination zones.

Next Steps
	•	Integrate external data such as population density, economic zones, and transport hubs.
	•	Analyze route-based patterns to identify frequent connections.
	•	Use DBSCAN clustering to uncover natural clusters and outliers in spatial data.

Deliverables
	•	Visualizations:
	•	Heatmaps, line charts, and scatter plots to highlight trends and vulnerable areas.
	•	Machine Learning Model:
	•	Predicts Reduction (%) with strong accuracy.
	•	Actionable Insights:
	•	Identified key regions and time windows for targeted intervention.

Dashboard

For interactive exploration, this analysis can be visualized using tools like Tableau, Dash, or Power BI to allow policymakers to:
	•	Monitor mobility trends.
	•	Identify vulnerable areas.
	•	Evaluate the impact of interventions over time.

Technologies Used
	•	Python: Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn.
	•	Machine Learning: Random Forest, KMeans Clustering.
	•	Visualization: Heatmaps, scatter plots, line charts.



