# Measure uncertainty with the CatBoost library 

The aim of this repository is to explore a confidence score between 0 and 1

## 1. Define a confidence score based on uncertainty
- Introduce types of uncertainty: data, knowledge, and total uncertainty
- Interpret the uncertainties’ magnitude
- Introduce formula of confidence score based on uncertainties

## 2.  Explore uncertainty methods with CatBoost
- Try two methods (Models with different seeds vs Virtual Ensemble)
- Compare both methods with different number of samples 
- Measure coverage rate from confidence intervals

## 3. Explore correlations of confidence score with model performances
- Statistics of confidence score
- Correlations of model’s metrics (RMSE, NRMSE, FA) with confidence score with plots
- Introduce PRR metric (not possible with Virtual Ensemble)

## Slides
The slides available here include the paper on which this internal project was based on, as well as the detailed methods applied in this notebook: 
https://docs.google.com/presentation/d/1HmOwRD3ftBowUlPkd9cjF02UTRyW7Vrx73qMqhhxOJ8/edit

## Organisation of the repo

### Noteebooks in the notebook 

Let's specify that the entire research was based on the M5 sales predictions daily per store. We have aggregated all the stores sales to change to a higher granularity to reduce the number of zeros in the sales data. The data is stored in a GCS Google Cloud Storage and will then be exported as pickles once processed (the pickles are too large to be stored in git).

    The files name should be self sufficient, however some extra details:
    - Uncertainty_project_M5_dataprep.ipynb: load the M5 dataset and put it in the correct format
    - Uncertainty_project_M5_macro_aggregation.ipynb: aggregate the sales for all stores
    - Ucertainty_project_confidence_correlation.ipynb: compute the confidence scores with the 3 different CatBoost methods: Models with different seeds, Virtual Ensemble and quantile and compute the correlation with Forecast accuracy

