# Synthetic_NMR_Develop
****Creating a Synthetic NMR Well-log from Conventional Logs with Machine Learning****  
*By Amalendu Das*  
**Definition of NMR:**

*Nuclear Magnetic Resonance (NMR) is a geophysical technique used to analyze the internal structure of rocks and sediments. NMR measures the magnetic properties of atomic nuclei, particularly hydrogen, within a sample. This data provides insights into pore size distribution, fluid saturation, and permeability of geological formations, which is crucial for understanding subsurface properties such as porosity and permeability. In the context of well logging, the NMR log can provide valuable information about the variation of pore sizes within the rock layers.*
**About the Project**


The project aims to predict a missing NMR well log by utilizing other well logs that are available. Specifically, the objective is to predict the NMR log from the Gamma Ray (GR) log, Caliper log, Resistivity log, and the interpreted porosity log in one well located in Atwater Valley, Gulf of Mexico. The model developed for this purpose is then applied to predict the NMR log of a different well in the same region, which is significant for studying methane hydrate deposits.

The two wells in question are located in the Atwater Valley Block 13 (AT-13) and Block 14 (AT-14). These wells were drilled and logged during Leg I of the U.S. Department of Energy/Chevron Gas Hydrate Joint Industry Project (JIP) in 2005. The raw well log data for AT-13 and AT-14 are available for analysis, as well as the processed well logs used in the project for both sites. The project’s aim is to use machine learning tools to construct a model that predicts the missing NMR log by utilizing the available logs for one well and applying it to predict the NMR log in another well located nearby.

### **Approach**  

To effectively characterize the Nuclear Magnetic Resonance (NMR) data, the relaxation time distribution from the NMR log was transformed into two statistical parameters: **Mean of T2 (MLT2)** and **Standard Deviation of T2 (SDT2)**. These two derived metrics serve as the response features that the model aims to predict. The predictor variables include other available well logs: **Gamma Ray (GR)**, **Caliper**, **Resistivity**, and the **interpreted porosity**.  

1. **Initial Data Exploration**  
   - A preliminary analysis was performed on the well logs to evaluate their individual (univariate) distributions and mutual (bivariate) relationships.  
   - The logs were also visualized with respect to depth to understand their variability and patterns.  

2. **Linear Regression Modeling**  
   - A basic linear regression model was applied to predict both MLT2 and SDT2 using the predictor variables.  
   - The results highlighted the limitations of linear regression due to:  
     - Noise in the data (short-distance variations).  
     - Complex, non-linear relationships between predictor and response variables.  

3. **Feature Standardization**  
   - To mitigate the impact of outliers and the varying units of predictor variables, feature standardization was applied.  
   - This step ensures that all variables contribute equally to the model and enhances the performance of complex algorithms.  
   - Additionally, **feature ranking** was conducted to identify and prioritize the most influential predictors for the response variables.  

4. **Noise Reduction and Advanced Modeling**  
   - The data was pre-processed to reduce noise and improve the quality of input features.  
   - The dataset was split into training and testing subsets to validate the model’s performance.  
   - A **polynomial regression model** was employed to capture the non-linear relationships and achieve a better fit for predicting the NMR log at **Keathley Canyon**.
5. **Prediction at Walker Ridge**  
   - After successfully training the model using data from Keathley Canyon, it was applied to predict the NMR log at **Walker Ridge**, where NMR data was not recorded.  

---

### **Pre-requisites**  

To execute this workflow, the following software and tools are required:  

1. **Python 3.x**:  
   - A high-level programming language used for implementing the machine learning models and data processing pipelines.  

2. **Anaconda Distribution**:  
   - A comprehensive platform that simplifies package management and deployment.  
   - It includes popular libraries like **NumPy**, **pandas**, **Matplotlib**, and **scikit-learn**, which are essential for data analysis, visualization, and machine learning.  

---

This approach combines statistical transformation, advanced modeling, and rigorous feature engineering to effectively predict missing NMR logs in regions of interest.

## Acknowledgement
I would like to acknowledge Abhishek D. Bihani for the original source code for the synthetic well log polynomial regression, available on GitHub (https://github.com/abhishekdbihani/synthetic_well-log_polynomial_regression ). I have made slight modifications to the code to suit the specific needs of my project.
