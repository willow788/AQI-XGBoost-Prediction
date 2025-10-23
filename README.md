# AQI XGBoost Prediction

A machine learning project for predicting Air Quality Index (AQI) using XGBoost algorithm. This project fetches real-time air quality data from OpenAQ API and weather data to analyze and predict PM2.5 levels and AQI categories for Delhi, India.

## Features

- **Real-time Data Fetching**: Retrieves PM2.5 measurements from OpenAQ API
- **Weather Integration**: Incorporates temperature and humidity data from OpenWeather API
- **AQI Categorization**: Converts PM2.5 values to standardized AQI categories
- **Data Preprocessing**: Comprehensive data cleaning and feature engineering
- **Streamlit Integration**: Ready for interactive web applications with caching support
- **XGBoost Prediction**: Machine learning model for AQI prediction (implementation in progress)

## AQI Categories

The project uses US EPA standard AQI breakpoints for PM2.5:

| PM2.5 Range (μg/m³) | AQI Category |
|---------------------|--------------|
| 0.0 - 12.0 | Good |
| 12.1 - 35.4 | Moderate |
| 35.5 - 55.4 | Unhealthy for Sensitive Groups |
| 55.5 - 150.4 | Unhealthy |
| 150.5 - 250.4 | Very Unhealthy |
| 250.5 - 500.4 | Hazardous |

## Prerequisites

- Python 3.7 or higher
- OpenWeather API Key (for weather data integration)

## Installation

1. Clone the repository:
```bash
git clone https://github.com/willow788/AQI-XGBoost-Prediction.git
cd AQI-XGBoost-Prediction
```

2. Create a virtual environment (recommended):
```bash
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
```

3. Install required dependencies:
```bash
pip install -r requirements.txt
```

## Dependencies

The project uses the following Python libraries:

- **pandas**: Data manipulation and analysis
- **numpy**: Numerical computing
- **requests**: HTTP library for API calls
- **xgboost**: Gradient boosting framework for machine learning
- **scikit-learn**: Machine learning utilities
- **matplotlib**: Data visualization
- **streamlit**: Web application framework (optional, for interactive apps)

## Usage

### Data Utilities

The `data_utils.ipynb` Jupyter notebook contains utility functions for data fetching and preprocessing:

1. **Fetch Air Quality Data**:
```python
# Fetch PM2.5 data from OpenAQ API for Delhi
df = fetch_openaq(city="Delhi", parameter="pm25", limit=10000)
```

2. **Convert PM2.5 to AQI Category**:
```python
# Convert PM2.5 value to AQI category
aqi_category = pm25_to_aqi(pm25_value)
```

3. **Preprocess Data**:
```python
# Preprocess raw data with weather integration
df_processed = preprocess(df_raw, openweather_api_key)
```

### API Configuration

To use the weather integration feature, you need an OpenWeather API key:

1. Sign up for a free API key at [OpenWeather](https://openweathermap.org/api)
2. Pass the API key to the `preprocess()` function

### Running the Notebook

Open and run the Jupyter notebook:
```bash
jupyter notebook data_utils.ipynb
```

## Project Structure

```
AQI-XGBoost-Prediction/
├── data_utils.ipynb      # Data fetching and preprocessing utilities
├── requirements.txt      # Project dependencies
└── README.md            # Project documentation
```

## Data Sources

- **OpenAQ API**: Real-time air quality measurements
  - Endpoint: `https://api.openaq.org/v2/measurements`
  - Free, open-source air quality data from around the world

- **OpenWeather API**: Weather data (temperature, humidity)
  - Endpoint: `https://api.openweathermap.org/data/2.5/weather`
  - Requires free API key

## Features in Development

- XGBoost model training and prediction
- Model evaluation and performance metrics
- Streamlit web application for interactive predictions
- Historical data analysis and visualization
- Multi-city support

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is open source and available under the MIT License.

## Acknowledgments

- [OpenAQ](https://openaq.org/) for providing free air quality data
- [OpenWeather](https://openweathermap.org/) for weather data API
- US EPA for AQI standards and guidelines

## Contact

For questions or suggestions, please open an issue on GitHub.
