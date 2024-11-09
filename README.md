# AgriVision 🌾

An intelligent agricultural advisory system that integrates AI, machine learning, and real-time environmental monitoring to provide precise crop and fertilizer recommendations.

[![Python](https://img.shields.io/badge/python-v3.10+-blue.svg)](https://www.python.org/)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

## Overview

AgriVision is a comprehensive agricultural decision support system that helps farmers make data-driven decisions through:
- AI-powered crop recommendations
- Intelligent fertilizer management
- Real-time weather monitoring
- Soil analysis
- Interactive data visualizations

## Features

### 🌱 Crop Recommendation System
- Machine learning-based crop suggestions using LightGBM
- Considers soil parameters (N, P, K, pH)
- Integrates real-time weather data
- Provides confidence scores for recommendations

### 🧪 Fertilizer Advisory
- Intelligent fertilizer type and quantity recommendations
- Soil type analysis
- Nutrient balance monitoring
- Application timing suggestions

### 🌤️ Environmental Monitoring
- Real-time weather data integration
- Temperature and humidity tracking
- Rainfall monitoring
- Weather alerts and advisories

### 📊 Data Visualization
- Interactive dashboards
- Soil parameter analysis plots
- Prediction confidence visualization
- Environmental condition trends

## Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/agrivision.git

# Navigate to the project directory
cd agrivision

# Install required packages
pip install -r requirements.txt
```

## Dependencies

- pandas
- numpy
- scikit-learn
- lightgbm
- plotly
- gradio
- anthropic
- requests
- geopy

## Usage

```python
# Initialize the system
system = IntegratedAgriSystem()

# Launch the web interface
demo = system.create_interface()
demo.launch()
```

## Environmental Variables

Create a `.env` file in the project root and add:

```
WEATHER_API_KEY=your_openweather_api_key
ANTHROPIC_API_KEY=your_anthropic_api_key
```

## API Documentation

### Crop Recommendation Endpoint
```python
predict_crop(
    location: str,
    N: int,
    P: int,
    K: int,
    temperature: float,
    humidity: float,
    ph: float,
    rainfall: float,
    soil_type: str,
    use_weather: bool
) -> Tuple[str, Figure, Figure]
```

### Fertilizer Recommendation Endpoint
```python
predict_fertilizer(
    temperature: float,
    humidity: float,
    moisture: float,
    soil_type: str,
    crop_type: str
) -> str
```

## Model Architecture

The system uses ensemble learning techniques:
- LightGBM Classifier for crop prediction
- Random Forest for fertilizer recommendations
- Feature importance analysis
- Cross-validation for model evaluation

## Directory Structure

```
agrivision/
├── data/
│   ├── Crop_recommendation.csv
│   └── Fertilizer_prediction.csv
├── models/
│   ├── crop_model.txt
│   └── fertilizer_model.txt
├── src/
│   ├── __init__.py
│   ├── preprocessing.py
│   ├── models.py
│   ├── visualization.py
│   └── utils.py
├── notebooks/
│   └── model_training.ipynb
├── tests/
│   └── test_predictions.py
├── requirements.txt
└── README.md
```

## Testing

Run the test suite:

```bash
python -m pytest tests/
```

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- OpenWeather API for weather data
- Anthropic for AI insights
- Kaggle for the initial datasets

## Contact

For questions and support, please open an issue in the GitHub repository.

## Roadmap

- [ ] Mobile application development
- [ ] Integration with IoT sensors
- [ ] Multi-language support
- [ ] Advanced crop disease detection
- [ ] Yield prediction module
- [ ] Marketplace integration
