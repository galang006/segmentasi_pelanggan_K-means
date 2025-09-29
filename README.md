# Customer Segmentation using K-Means Clustering

This project implements customer segmentation using the K-Means clustering algorithm, based on RFM (Recency, Frequency, Monetary) analysis. It processes a transactional dataset to identify distinct customer groups, which can be valuable for targeted marketing strategies and business insights. The analysis involves data preprocessing, RFM calculation, outlier handling, data scaling, determining the optimal number of clusters, and finally applying K-Means to segment customers.

## Features
-   **Data Loading and Initial Exploration**: Loads the `customer_segmentation.csv` dataset and performs initial data inspection.
-   **Data Pre-processing**: Handles missing values (drops rows with `NaN` in `CustomerID`) and calculates the `Total_Amount` for each transaction.
-   **RFM Analysis**: Computes Recency (days since last purchase), Frequency (total number of purchases), and Monetary (total spending) values for each customer.
-   **Outlier Detection and Removal**: Identifies and removes outliers in the RFM variables using the Interquartile Range (IQR) method to ensure robust clustering.
-   **Data Standardization**: Scales the RFM features using `StandardScaler` to prevent features with larger magnitudes from dominating the clustering process.
-   **Optimal Cluster Determination**: Utilizes the Elbow Method by plotting the Within Cluster Sum of Squares (WCSS) for different `k` values (number of clusters) to help identify the optimal `k`.
-   **K-Means Clustering**: Applies the K-Means algorithm (with `n_clusters = 3` as suggested by the Elbow Method) to segment customers based on their standardized RFM scores.
-   **Model Evaluation**: Evaluates the clustering model using the Davies-Bouldin Index, a metric that quantifies the similarity between clusters and the dissimilarity within clusters.
-   **Customer Segment Visualization**: Visualizes the identified customer segments in a 3D scatter plot, showing how different clusters are distributed across the 'Monetary', 'Frequency', and 'Recency' dimensions.
-   **Segment Analysis**: Provides a grouped analysis of the mean, max, and min RFM values for each identified cluster, offering insights into the characteristics of each customer segment.

## Installation
This project is provided as a Jupyter Notebook, which requires a Python environment with specific libraries.

1.  **Install Python**: If you don't have Python installed, download it from [python.org](https://www.python.org/downloads/). It is recommended to use Python 3.8 or later.
2.  **Install Jupyter Notebook**:
    ```bash
    pip install notebook
    ```
    Alternatively, you can use Google Colab, which provides a hosted Jupyter environment with most data science libraries pre-installed.
3.  **Install Required Libraries**: Open your terminal or command prompt and install the necessary Python libraries:
    ```bash
    pip install pandas seaborn matplotlib scikit-learn
    ```
4.  **Download the Codebase**:
    -   Download the `FP_ML.ipynb` notebook file.
    -   Obtain the `customer_segmentation.csv` dataset and place it in the same directory as the notebook.

## Usage
To run and use this project:

1.  **Start Jupyter Notebook**:
    ```bash
    jupyter notebook
    ```
    This will open a new tab in your web browser with the Jupyter Notebook dashboard.
2.  **Open the Notebook**: Navigate to the directory where you saved `FP_ML.ipynb` and click on the file name to open it.
3.  **Run Cells**: Execute the notebook cells sequentially.
    -   You can run each cell individually by clicking on it and pressing `Shift + Enter`.
    -   To run all cells, go to the "Cell" menu and select "Run All".
4.  **Review Output**: Observe the output of each cell, which includes:
    -   Dataframes displaying initial data, RFM calculations, and scaled data.
    -   Box plots showing the distribution of RFM variables and identifying outliers.
    -   An Elbow Method plot to help determine the optimal number of clusters.
    -   The Davies-Bouldin Index score for model evaluation.
    -   A 3D scatter plot visualizing the customer segments.
    -   A summary table detailing the mean, max, and min RFM values for each cluster.

## Code Structure
The project consists of a single Jupyter Notebook file and an external dataset:

-   `FP_ML.ipynb`: This is the main Jupyter Notebook that contains all the Python code for:
    -   Importing necessary libraries.
    -   Loading and initial exploration of the `customer_segmentation.csv` dataset.
    -   Data cleaning and preprocessing steps (handling missing values, creating `Total_Amount`).
    -   Performing RFM analysis to derive `Recency`, `Frequency`, and `Monetary` features.
    -   Identifying and removing outliers from the RFM dataset.
    -   Standardizing the RFM features.
    -   Applying the Elbow Method to find the optimal number of clusters.
    -   Implementing the K-Means clustering algorithm.
    -   Evaluating the clustering model using the Davies-Bouldin Index.
    -   Visualizing the resulting customer segments in a 3D plot.
    -   Analyzing the characteristics of each customer cluster.

-   `customer_segmentation.csv`: This CSV file is the input dataset containing transactional data used for customer segmentation. It is expected to be present in the same directory as the `FP_ML.ipynb` notebook when running the project.
