# 🏠 California House Price Predictor

A modern, interactive web application that predicts housing prices in California using machine learning. Built with Flask, LightGBM, and a stunning glassmorphism UI design.

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Flask](https://img.shields.io/badge/Flask-2.0+-green.svg)
![LightGBM](https://img.shields.io/badge/LightGBM-ML-orange.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

## ✨ Features

- 🗺️ **Interactive California Map** - Click anywhere on the map to select your location
- 📍 **Geolocation Support** - Use your current location with one click
- 🤖 **ML-Powered Predictions** - Trained LightGBM model for accurate price estimates
- 🎨 **Modern UI Design** - Beautiful glassmorphism design with smooth animations
- 📱 **Fully Responsive** - Works seamlessly on desktop, tablet, and mobile
- ⚡ **Real-time Calculations** - Auto-calculates derived features as you type
- 🔄 **Sample Data** - Quick-load sample data for testing

## 🚀 Quick Start

### Prerequisites

- Python 3.8 or higher
- pip (Python package manager)

### Installation

1. **Clone the repository**

2. **Create a virtual environment** (recommended)
   ```bash
   python -m venv venv
   
   # On Windows
   venv\Scripts\activate
   
   # On macOS/Linux
   source venv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the application**
   ```bash
   python app.py
   ```

5. **Open your browser**
   Navigate to `http://127.0.0.1:5000`

## 📁 Project Structure

```
california-house-price-predictor/
│
├── app.py                 # Flask application & API endpoints
├── requirements.txt       # Python dependencies
├── README.md             # Project documentation
│
├── models/
│   ├── LightGBM_housing_model.pkl    # Primary prediction model
│   ├── RandomForest_housing_model.pkl # Alternative model
│   └── xgboost_housing_model.pkl      # Alternative model
│
├── static/
│   ├── css/
│   │   └── style.css     # Modern glassmorphism styles
│   └── js/
│       └── script.js     # Frontend logic & map integration
│
└── templates/
    └── index.html        # Main HTML template
```

## 🛠️ Tech Stack

### Backend
- **Flask** - Lightweight Python web framework
- **Flask-CORS** - Cross-Origin Resource Sharing support
- **LightGBM** - Gradient boosting framework for predictions
- **NumPy** - Numerical computing
- **Joblib** - Model serialization

### Frontend
- **HTML5** - Semantic markup
- **CSS3** - Modern styling with glassmorphism effects
- **JavaScript (ES6+)** - Interactive functionality
- **Leaflet.js** - Interactive maps
- **Font Awesome** - Beautiful icons
- **Google Fonts (Poppins)** - Modern typography

## 📊 Input Features

| Feature | Description | Example |
|---------|-------------|---------|
| **Latitude** | Geographic latitude (from map) | 37.7749 |
| **Longitude** | Geographic longitude (from map) | -122.4194 |
| **Median Income** | Median household income (in $10,000s) | 3.87 |
| **Housing Median Age** | Median age of houses in the area | 41 |
| **Total Rooms** | Total rooms in the block | 8802 |
| **Total Bedrooms** | Total bedrooms in the block | 2185 |
| **Population** | Block population | 3228 |
| **Households** | Number of households | 1267 |
| **Ocean Proximity** | Location relative to ocean | Near Bay |

### Auto-Calculated Features
- **Rooms per Household** = Total Rooms ÷ Households
- **Bedrooms per Room** = Total Bedrooms ÷ Total Rooms
- **Population per Household** = Population ÷ Households

## 🔌 API Endpoints

### `GET /`
Serves the main web application.

### `GET /api`
Returns API information and available endpoints.

### `GET /api/features`
Returns feature descriptions and valid options.

**Response:**
```json
{
  "ocean_proximity_options": ["NEAR BAY", "<1H OCEAN", "INLAND", "NEAR OCEAN", "ISLAND"],
  "california_bounds": {...},
  "features_description": {...}
}
```

### `POST /api/predict`
Makes a price prediction based on input features.

**Request Body:**
```json
{
  "latitude": 37.7749,
  "longitude": -122.4194,
  "median_income": 3.87,
  "housing_median_age": 41,
  "total_rooms": 8802,
  "total_bedrooms": 2185,
  "population": 3228,
  "households": 1267,
  "ocean_proximity": "NEAR BAY",
  "rooms_per_household": 6.95,
  "bedrooms_per_room": 0.248,
  "population_per_household": 2.55
}
```

**Response:**
```json
{
  "predicted_price": 452000.00,
  "formatted_price": "$452,000.00",
  "status": "success",
  "input_features": {...},
  "location": {
    "latitude": 37.7749,
    "longitude": -122.4194
  }
}
```

## 📈 Model Information

The application uses a **LightGBM** (Light Gradient Boosting Machine) model trained on the California Housing Dataset. This dataset contains information about housing in California based on the 1990 census.

### Dataset Details
- **Source**: California Housing Dataset
- **Location Range**: 
  - Latitude: 32.5° to 42.0°
  - Longitude: -124.5° to -114.0°

### Available Models
1. **LightGBM** (Default) - Fast and accurate (~1.4 MB)
2. **XGBoost** - Alternative model (~2.2 MB)
3. **Random Forest** - Alternative model (~42 MB)

## 🎨 UI Features

- **Animated Background** - Floating gradient orbs with smooth animations
- **Glassmorphism Design** - Frosted glass effect on cards
- **Micro-interactions** - Hover effects and smooth transitions
- **Gradient Accents** - Purple/indigo color scheme
- **Responsive Layout** - Adapts to all screen sizes
- **Custom Scrollbar** - Styled to match the theme

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 📧 Contact

If you have any questions or suggestions, feel free to open an issue or reach out!

---

