# EV-Adoption-Analysis-SDGs
HKU final-year project analyzing EV impacts using Python and ML

__Overview__

This project is my final-year capstone (BSDS4999) for the BASc in Social Data Science at The University of Hong Kong. It investigates global electric vehicle (EV) adoption patterns from 2010-2023 using descriptive statistics, k-means clustering (k=6), and multiple linear regression (MLR) to highlight disparities, identify regional archetypes, and predict EV sales share. The analysis aligns with UN Sustainable Development Goals (SDGs) 7 (Affordable and Clean Energy) and 9 (Industry, Innovation, and Infrastructure) by promoting sustainable transport and examining industrial/infrastructural roles.
Key skills showcased: Python (Pandas, NumPy, Scikit-learn, Matplotlib/Seaborn), data preprocessing, exploratory data analysis (EDA), unsupervised learning (clustering), supervised learning (regression), visualization, and deriving policy insights for socio-economic impact.
Note: Generative AI (Grok) was used to assist in drafting the project report, but all code, data analysis, and interpretations are my original work.

__Data Sources__

•  IEA Global EV Data 2024: EV sales share, stock share, sales volumes, and charging points (12,654 rows, 8 columns).

•  World Bank GDP per Capita: GDP per capita (USD) for 1960–2024, reshaped for 2023 (261 rows, 70 columns).

•  World Bank Urban Population: Urban population percentage for 1960–2024, reshaped for 2023 (261 rows, 70 columns).

•  SDG Indicator 9.2.2: Manufacturing employment percentage for 2023 (4,815 rows, 8 columns).

Datasets were sourced publicly and focused on 2023 data for 30 regions (26 after merging for clustering/regression).

__Methodology__

Data Preprocessing

•  Standardized region names (e.g., ‘United States’ to ‘USA’).

•  Filtered to 2023 historical data.

•  Features for Clustering/Regression:

	•  ev_sales_share (%): Target for regression, predictor for clustering.

	•  ev_stock (vehicles): Sum of BEV, PHEV, FCEV stock.

	•  GDP per capita (USD).

	•  Urban population (% of total).

	•  Manufacturing employment (%).

	•  Charging points: Excluded due to 100% missing data.

•  Descriptive Features: EV sales/stock share by vehicle type (cars, buses, trucks, vans); EV sales by powertrain; AAGR for car sales share (2010–2023).

•  Missing Data: Imputed 2 values each for GDP per capita, urban population, manufacturing employment using median; noted but not imputed for non-car vehicles.

•  Outlier Handling: Winsorized ev_stock and GDP per capita at 5%.

•  Scaling: Standardized features for clustering and regression.

Descriptive Analysis

•  Metrics: EV sales/stock share by vehicle type; EV sales by powertrain; AAGR.

•  Visualizations: Bar charts (sales share, AAGR), heatmap (vehicle types), line plot (growth trends). Run the Jupyter notebook to generate and view these visualizations.
![image](https://github.com/user-attachments/assets/5bf0e1a4-ba37-49a3-be30-a0067b03d9ed)

K-Means Clustering

•  Algorithm: K-means with n_init=10.

•  Optimal k=6 selected via elbow method and silhouette scores.

•  Clustered 26 regions on standardized features.

![image](https://github.com/user-attachments/assets/e4b37d5b-33f3-4cce-b235-c21047116718)

Multiple Linear Regression

•  Model: Linear regression predicting ev_sales_share.

•  Features: ev_stock, GDP per capita, urban population, manufacturing employment.

•  Data Split: 80% training, 20% testing (random_state=42).

•  Evaluation: MSE, R²; feature importance via coefficients.

•  Visualizations: Actual vs. predicted scatter, feature importance bar, residuals histogram. Run the Jupyter notebook to generate and view these visualizations.

__Results__

Descriptive Analysis

•  EV Sales Share (%) for Cars in 2023: Norway (93%), Iceland (71%), Sweden (60%), Finland (54%) led; South Africa (0.29%), Chile (0.31%), Mexico (1.3%) lagged. Disparities: Austria (26%) vs. Brazil (3%).

•  Global EV Sales for Cars by Powertrain (2010-2023): Rapid growth in BEV/PHEV.

•  EV Sales Share Trends (Top 10 Regions, 2010-2023): High AAGR in UAE (249.3%), Costa Rica (143.8%).

•  EV Stock Share (%) by Vehicle Type (Top 20 Regions): Cars dominate; buses high in China (50%), Switzerland (65%).
Multiple Linear Regression

•  Performance: Train MSE: 112.5898, Test MSE: 129.9202; Train R²: 0.2356, Test R²: 0.1611.

•  Coefficients: ev_stock (3.473750), GDP per capita (5.348962), Urban population (-0.426285), Manufacturing employment (-0.777969).

__Discussion and Insights__

•  Descriptive: Stark disparities (e.g., Norway 93% vs. Brazil 3%) highlight economic/infrastructural gaps; cars lead adoption, buses show SDG 7 progress.

•  Clustering: Six archetypes (e.g., Cluster 3: Norway as SDG exemplar; Cluster 4: Brazil/Australia lagging).

•  Regression: Positive drivers (ev_stock, GDP) confirm economic role; negative coefficients suggest multicollinearity.

•  Societal Implications: Tailored policies (e.g., subsidies for Cluster 1, chargers for Cluster 5) to advance SDGs 7/9.

__Limitations__

•  Missing charging data (100% for 2023).

•  Small sample (26 regions).

•  Imputation bias; k-means assumptions; linear model limitations.

•  Sparse non-car data; static 2023 focus.

__Conclusion__

Integrated analysis reveals disparities, archetypes, and drivers in EV adoption. Future: Add charging data, more regions, non-linear models.
Technologies Used

•  Programming: Python 3.x

•  Libraries: Pandas, NumPy, Scikit-learn (clustering, regression), Matplotlib/Seaborn (visualization)

•  Environment: Jupyter Notebook

__References__

•  BloombergNEF. (2023). Electric Vehicle Outlook 2023.

•  Hardman, S., et al. (2017). A review of consumer preferences… Transportation Research Part D, 54, 11–24.

•  Hardman, S., et al. (2018). Driving the market… International Journal of Sustainable Transportation, 12(5), 343–356.

•  IEA. (2024). Global EV Data 2024.

•  Li, W., et al. (2019). A review of factors… Renewable and Sustainable Energy Reviews, 78, 318–328.

•  Sierzchula, W., et al. (2014). The influence of financial incentives… Energy Policy, 68, 183–194.

•  Zhang, X., et al. (2020). Clustering analysis… Energy Policy, 141, 111414.

__Author__

•  Kyle Chan (Chan Wang Tik)

•  Final-year BASc (Social Data Science) student at HKU

•  Email: u3610176@connect.hku.hk

•  LinkedIn: linkedin.com/in/wang-tik-chan

•  GitHub: github.com/Kyle715-hk

Feel free to reach out for collaborations or questions! This project demonstrates my ability to apply data science for impactful, SDG-aligned research.
