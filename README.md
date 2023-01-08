#  Clustering Cryptocurrencies - UW FinTech Bootcamp Module 10 Challenge

In this project I apply the unsupervised learning technique of K-Means clustering to group cryptocurrencies by their performance in an effort to create profitable portfolio recommendations.

### Data Used
[crypto_market_data.csv](/Resources/crypto_market_data.csv) - market data of different cryptocurrencies during different time periods 

### Summary

I start by using the elbow curve method, using normalized data, to find the optimal k value for the K-Means model that will use all of the original features of the dataset. 

![Elbow curve line plot showing a value of 4 for k to be optimal for the dataset with all features](/Resources/Images/elbow_curve.png)

Then, using the optimal k value I train and predict the K-Means model to generate 4 clusters of cryptocurrencies. The inertia of each cluster was significant enough to consider reducing the amount of features. 

![A scatter plot showing 4 clusters with heavy inertia](/Resources/Images/all_features_scatter.png)

To reduce the amount of features used, I applied Principal Component Analysis to create 3 primary clusters. 

![DataFrame holding 3 primary clusters as columns and cryptocurrency as index](/Resources/Images/pca.png)

I then used the PCA data to again calculate the optimal k value for the K-Means model. 

![Elbow curve line plot from the PCA data that shows 4 to be the optimal k value](/Resources/Images/pca_elbow_curve.png)

Finally, with the optimal k value for the PCA features, I plot the new clusters. 

![Scatter plot showing 4 low inertia clusters generated using the PCA dataframe](/Resources/Images/pca_scatter.png)

---

## Technologies

This is a Python 3.7 project ran using a JupyterLab in a conda dev environment. 

The following dependencies are used: 
1. [Jupyter](https://jupyter.org/) - Running code 
2. [Conda](https://github.com/conda/conda) (4.13.0) - Dev environment
3. [Pandas](https://github.com/pandas-dev/pandas) (1.3.5) - Data analysis
4. [Matplotlib](https://github.com/matplotlib/matplotlib) (3.5.1) - Data visualization
5. [Numpy](https://numpy.org/) (1.21.5) - Data calculations + Pandas support
6. [hvPlot](https://hvplot.holoviz.org/index.html) (0.8.1) - Interactive Pandas plots 
7. [scikit-learn](https://scikit-learn.org/stable/) (1.0.2) - KMeans clustering, data normalization, and PCA 

---

## Installation Guide

If you would like to run the program in JupyterLab, install the [Anaconda](https://www.anaconda.com/products/distribution) distribution and run `jupyter lab` in a conda dev environment.

To ensure that your notebook runs properly you can use the [requirements.txt](/Resources/requirements.txt) file to create an exact copy of the conda dev environment used in development of this project. 

Create a copy of the conda dev environment with `conda create --name myenv --file requirements.txt`

Then install the requirements with `conda install --name myenv --file requirements.txt`

---

## Usage

The Jupyter notebook [crypto_investments.ipynb](/crypto_investments.ipynb) will provide all steps of the data collection, preparation, and analysis. Data visualizations are shown inline and accompanying analysis responses are provided.

---

## Contributors

[Ethan Silvas](https://github.com/ethansilvas)

---

## License

This project uses the [GNU General Public License](https://choosealicense.com/licenses/gpl-3.0/)
