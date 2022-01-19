# load-forecasting

Repository holds the code and data used for my final project for DSCI 470 - Introduction to Machine Learning at Colorado School of Mines.

### Description
The project uses a Long Short-Term Memory Network to forecast the next hour's energy demand (or "load") for the Connecticut ISO Zone.

### Technologies
Python 3.8 and the following packages: matplotlib, pandas, numpy, scikit-learn, ipywidgets, keras, tensorflow, voila.

### To Use

All data used can be found in the /data subfolder. The jupyter notebooks can be used as follows:

**preprocessing.ipynb**
- Loads in *data/weather_3yback_NE.csv* and *data/load_3yback_NE.csv* which hold features related to the hourly weather and energy demand of ISO NE Zones, respectively.
- Manipulates data and subsets to only the Connecticut ISO Zone.
- Saves Connecticut ISO Zone csv.

**modeling_lstm.ipynb**
- Loads in *data/connecticutData.csv* and manipulates to use as an input to LSTM framework.
- Trains LSTM model (warning--this will take around 10 minutes) and outputs various metrics.
- Saves model to use in deployment.

**deployment.ipynb**
- Uses voila framework to bring up a webpage where the user can upload a csv of >=9 previous hour's average load, temperature, and dummy for whether the next hour is a peak/nonpeak time, and returns estimated next-hour's energy demand.
- *data/dataDeployment.csv* provides a test dataset one can use to see this in practice.
- Simply cd into your directory and run `voila deployment.ipynb` from the command line to bring up webpage. Then upload this test dataset.
