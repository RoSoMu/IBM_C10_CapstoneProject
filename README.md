# IBM Data Science Capstone — SpaceX Launch Analysis

Capstone project completed as part of the **IBM Data Science Professional Certificate**.

The project follows a complete data-analysis workflow using SpaceX launch data: data collection through APIs and web scraping, data wrangling, exploratory analysis with SQL and Python, interactive visualisation, and machine-learning classification.

**Methods & tools:** Python · pandas · NumPy · SQL · Matplotlib · Folium · Plotly Dash · scikit-learn

## Project workflow

The original course structure is preserved in the repository filenames:

- `M#` = course module
- `L#` = lesson/lab within that module

### 1. Data collection & wrangling

SpaceX launch data was collected from API and web sources and prepared for subsequent analysis.

- **M1L1 — Data Collection with API:** [View notebook](M1L1_jupyter-labs-spacex-data-collection-api.ipynb)
- **M1L2 — Data Collection with Web Scraping:** [View notebook](M1L2_jupyter-labs-webscraping.ipynb)
- **M1L3 — Data Wrangling:** [View notebook](M1L3_labs-jupyter-spacex-Data%20wrangling.ipynb)

### 2. Exploratory data analysis

Launch data was explored using SQL and Python to examine relationships between flight characteristics and launch outcomes.

- **M2L1 — Exploratory Data Analysis with SQL:** [View notebook](M2L1_jupyter-labs-eda-sql-coursera_sqllite%20.ipynb)
- **M2L2 — Exploratory Data Analysis with Pandas and Matplotlib:** [View notebook](M2L2_edadataviz.ipynb)

### 3. Interactive visualisation

Launch sites and outcomes were explored through geospatial visualisation with Folium and an interactive Plotly Dash dashboard.

- **M3L1 — Interactive Visual Analytics with Folium:** [View notebook](M3L1_lab_jupyter_launch_site_location.ipynb)
- **M3L2 — Interactive Dashboard with Plotly Dash:** [View app](M3L2_spacex-dash-app.py)
- **Dashboard instructions:** [View PDF](M3L2_Dashboard_Instructions.pdf)

The screenshots below preserve the rendered interactive outputs, which were not retained when the original notebooks were downloaded from the course platform.

<details>
<summary><strong>Folium output screenshots (8)</strong></summary>

<br>

1. [CircleMarker popup](M3L1_Folium_Screenshot_1_CircleMarker_Popup_Label.png)
2. [Site marker popup](M3L1_Folium_Screenshot_2_SiteMarker_Popup_Label.png)
3. [Marker cluster](M3L1_Folium_Screenshot_3_%20Cluster_Popup_Label.png)
4. [Mouse position](M3L1_Folium_Screenshot_4_%20MousePosition.png)
5. [Distance to railway](M3L1_Folium_Screenshot_5_DistanceMarker_railway.png)
6. [Railway polyline](M3L1_Folium_Screenshot_6_PolyLine_railway.png)
7. [Distance to coastline](M3L1_Folium_Screenshot_7_DistanceMarker_coastline.png)
8. [Coastline polyline](M3L1_Folium_Screenshot_8_Polyline_coastline.png)

</details>

<details>
<summary><strong>Plotly Dash output screenshots (7)</strong></summary>

<br>

1. [Dashboard skeleton](M3L2_Dash_Screenshot%20_1_skeleton_test.png)
2. [All-sites dropdown](M3L2_Dash_Screenshot_2_Dropdown_AllSites.png)
3. [Single-site dropdown](M3L2_Dash_Screenshot_3_Dropdown_OneSite.png)
4. [Payload range — all sites](M3L2_Dash_Screenshot_4_PayloadRange_AllSites.png)
5. [Payload range — single site](M3L2_Dash_Screenshot_5_PayloadRange_OneSite.png)
6. [Complete dashboard — all sites](M3L2_Dash_Screenshot_6_Complete_AllSites.png)
7. [Complete dashboard — single site](M3L2_Dash_Screenshot_7_Complete_OneSite.png)

</details>

### 4. Machine-learning classification

The original analysis compared four classification algorithms — **Logistic Regression, SVM, K-Nearest Neighbors and Decision Tree** — for predicting successful first-stage landing outcomes.

The four models produced almost identical results:

| Model | Training accuracy | Test accuracy |
|---|---:|---:|
| Logistic Regression | 85% | 83% |
| SVM | 85% | 83% |
| Decision Tree | 84% | 83% |
| K-Nearest Neighbors | 85% | 83% |

On the test data, the baseline models also produced the same number of false positives (3) and a precision of **0.80**, leaving little basis for selecting one model from the original comparison.

- **M4L1 — Decision Tree experiment (`max_features="log2"`):** [View notebook](M4L1_SpaceX_Machine%20Learning%20Prediction_Part_5_TreeLog2.ipynb)
- **M4L2 — Baseline models and threshold analysis:** [View notebook](M4L2_SpaceX_Machine%20Learning%20Prediction_Part_5_TreeAuto_Threshold.ipynb)

#### Extension beyond the original lab

Because the baseline classifiers produced essentially equivalent results, I extended the original analysis to investigate whether precision could provide a more useful basis for model selection.

Changing the Decision Tree from `max_features="auto"` to `"log2"` increased precision from **0.80 to 0.83**, but reduced test accuracy from **83% to 78%**.

I then explored alternative classification thresholds. Increasing the Logistic Regression threshold to **0.7** again increased precision to **0.83**, but test accuracy decreased to **78%**.

Increasing the SVM threshold to **0.8** produced a better trade-off: precision increased from **0.80 to 0.91**, false positives were reduced from **3 to 1**, and the original **83% test accuracy was retained**.

Given the practical cost of false-positive predictions in this context, the threshold-adjusted SVM provided a more useful model-selection rationale than accuracy alone.

**Note**: Results are based on the course-provided test split (n = 18). The analysis therefore illustrates model evaluation and comparison, while a larger dataset would be needed to assess whether these performance differences generalise reliably.

## Final presentation

The final course presentation summarises the complete project workflow, results and conclusions.

**[View final capstone presentation (PDF)](M5L1_IBM_Capstone_Project_SorayaRodriguez.pdf)**

## Course context

This repository contains the capstone project for the **IBM Data Science Professional Certificate**. The original course lab structure and `M#L#` filename convention have been retained, while the machine-learning analysis includes additional experimentation with model configuration and classification thresholds.

