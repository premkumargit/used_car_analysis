# Key Drivers for Used Car Prices

## 📊 Overview

**Key Drivers for Used Car Prices** is a data-driven project that aims to identify and analyze the most influential factors affecting the pricing of used cars. By leveraging machine learning models and statistical analysis, this project uncovers insights that can help dealerships, buyers, and sellers make informed pricing decisions.

## 🧠 Objectives

- Analyze used car datasets to discover key price determinants  
- Build regression and clustering models to predict car prices and recommend inventory  
- Visualize trends related to car age, mileage, manufacturer, fuel type, and more  
- Provide actionable recommendations to optimize used car inventory and pricing strategies

## 📂 Dataset Overview

The provided dataset contains information on approximately **426,000 used cars**. To ensure efficient processing and faster experimentation during development, this project uses a **sample size of 10,000 records** to build and test the models.

### Data Reduction Strategy

- **State**: The dataset includes 51 distinct U.S. states. However, the **top 25 states** account for **81.76%** of the data. For modeling and analysis, only these top 25 states are retained; the remaining are grouped under a single category labeled **"Others"**.

- **Manufacturer**: There are **42 distinct manufacturers** in the dataset. The **top 25 manufacturers** cover **95%** of the records. These are retained individually, while the rest are categorized as **"Others"** to reduce noise and sparsity.

- **Year**: The dataset spans **122 distinct model years**. The **most recent 50 years (1970–2022)** account for **99%** of the data. Therefore, only records from the last 50 years are used for Exploratory Data Analysis (EDA) to maintain relevance and data density.

<p float="left">
    <img src="/images/State_SoldCars.png" width="45%"> 
    <img src="/images/Manu_SoldCars.png" width="45%"> 
</p>    
<p float="left">
    <img src="/images/Year_SoldCars.png" width="45%"> 
    <img src="/images/Price_SoldCars.png" width="45%">
</p>    



### Feature Engineering Note

- **Price**: The `price` feature is **heavily right-skewed**, which can negatively impact model performance. To normalize the distribution and stabilize variance, the **square root transformation (`sqrt(price)`)** is applied during modeling.


## 📌 Key Findings

- **Car Age**:  
  Customers prefer newer vehicles. It’s recommended to stock inventory with cars from the last 10 years (model years **2011 to 2021**).

- **Mileage**:  
  Vehicles with odometer readings under **120,000 miles** align better with buyer preferences.

- **Price Point**:  
  Cars priced below **$40,000** tend to sell better, with particularly strong demand for those under **$10,000**.

- **Title Status**:  
  Vehicles with **salvage titles** have the lowest demand, while those with **clean titles** attract more buyers.

- **Popular Manufacturers**:  
  Vehicles from **Chevy, Ford, Toyota, Honda, and Nissan** are especially in demand.

- **Fuel Type**:  
  **Gasoline-powered cars** remain significantly more popular than electric, diesel, or hybrid alternatives.

## 🤖 Model Recommendations

### Recommendation Score (1–10)

This score indicates how strongly a vehicle is recommended for dealership inventory. The model uses **K-Means Clustering** to group similar cars into 10 clusters based on historical sales data. Clusters with larger populations represent vehicles that have historically sold more frequently and faster. A higher score suggests a stronger likelihood of quick turnover and high demand.

### Suggested Price

To predict an optimal price for each vehicle, the project uses **Ridge Regression**, a regularized linear model well-suited for datasets with multicollinearity. Prior to modeling, **SelectKBest** is applied to perform feature selection and retain the most statistically significant predictors. This combination helps improve model generalizability and interpretability. Due to variability in features and regional trends, the suggested prices may deviate by **$5,000–$8,000** from actual market prices.

## 🔧 Tech Stack

- **Programming Language**: Python  
- **Libraries**: pandas, numpy, scikit-learn, matplotlib, seaborn  
- **Modeling Techniques**: Linear Regression, Ridge Regression, KMeans Clustering, SelectKBest  
- **Environment**: Jupyter Notebook

## 📥 Installation

1. Clone the repository:
   ```bash
   git clone https://github.dev/premkumargit/used_car_analysis.git
   cd used-car-price-analysis
   ```

## 🚀 Usage

1. Load the dataset into `prompt_II1.ipynb`.
2. Run cells sequentially to:
   - Clean and preprocess data
   - Perform exploratory data analysis (EDA)
   - Train and evaluate models
   - Generate recommendation scores and price predictions
