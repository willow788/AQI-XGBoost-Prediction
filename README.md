

## Overview

This project provides a **Machine Learning-based Air Quality Predictor** that forecasts PM2.5 levels using historical air quality data from OpenAQ and optional weather data from OpenWeather. It includes a **Streamlit web app** for visualization and interaction, as well as a **reproducible Colab notebook** for training and evaluating the model with XGBoost.

The app features:

* Interactive dashboards and graphs using Plotly and Matplotlib
* KPI cards with AQI categorization and colored banners
* Station map visualization using PyDeck
* Model training, saving, and loading
* Downloadable charts as PNGs

## Features

* Fetch historical PM2.5 data from OpenAQ
* Preprocess data: hourly aggregation, lag features, rolling averages, time-based features
* Optional weather augmentation from OpenWeather
* Train and evaluate XGBoost regression model
* Interactive Streamlit UI:

  * Station selector
  * Validation window control
  * Graphs: Actual vs Predicted, Residuals, Feature Importance, Hourly Heatmap
  * Download charts as PNG

## Installation

1. Clone this repository

```bash
git clone <repo_url>
cd aq-predictor
```

2. Install dependencies

```bash
pip install -r requirements.txt
```

3. (Optional) Add OpenWeather API key for weather features

```bash
export OPENWEATHER_API_KEY='your_api_key_here'
```

Or set in Streamlit secrets.

## Usage

### Streamlit App

```bash
streamlit run app.py
```

* Use the sidebar to select station, set data limit, and trigger model training.
* Interactive charts with zoom, hover, and download options.

### Colab Notebook

* Copy the provided notebook cells into a Colab notebook.
* Run each cell sequentially to fetch data, preprocess, train model, and generate graphs.
* PNG figures are saved to the `figures/` folder.

## Project Structure

```
aq-predictor/
├── app.py                  # Streamlit app
├── requirements.txt        # Python dependencies
├── figures/                # Generated graphs
├── models/                 # Saved XGBoost models
└── README.md
```

## Graphs

* **Actual vs Predicted**: Time-series PM2.5 comparison
* **Residuals Distribution**: Histogram and scatter
* **Feature Importance**: XGBoost gain-based ranking
* **Hourly Heatmap**: Average PM2.5 by hour and day of week

## Notes

* The app uses caching to speed up API calls.
* Interactive Plotly charts require `kaleido` for PNG downloads.
* The model currently uses the station with the most historical data; future improvements can include multi-station predictions.

## WILL UPDATE THE PROJECT SOON. A BIT LAZY RIGHT NOW!
