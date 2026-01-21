# Diabetes Prediction System

## 📋 Project Overview

This is a machine learning-based medical decision support tool for predicting diabetes risk using patient health metrics. The system uses a trained classification model to assess whether a patient is likely to have diabetes based on clinical measurements.

## ✨ Features

- **Real-time Prediction**: Interactive web interface for instant diabetes risk assessment
- **Comprehensive Input**: Considers 8 key health indicators including derived features
- **Probability Scores**: Provides confidence levels for predictions
- **User-Friendly Interface**: Clean, intuitive Gradio-based web application
- **Robust Processing**: Includes data scaling and feature engineering

## 🔬 Model Details

- **Algorithm**: Ensemble method (XGBoost/LightGBM with fallback to Random Forest)
- **Features Used**:
  - Pregnancies
  - Glucose Level
  - Blood Pressure
  - Skin Thickness
  - Insulin
  - BMI (Body Mass Index)
  - Diabetes Pedigree Function
  - Age
  - **Derived Feature**: Insulin-to-Glucose Ratio (engineered feature)

- **Preprocessing**: StandardScaler normalization
- **Performance**: Optimized for medical decision support with balanced precision/recall

## 🚀 Quick Start

### Prerequisites

- Python 3.8 or higher
- pip package manager

### Installation

1. **Clone or download the project files**

2. **Install required dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Ensure model files are present**:
   - `diabetes_model.pkl` - Trained ML model
   - `scaler.pkl` - Feature scaler object

### Running the Application

1. **Start the web application**:
   ```bash
   python app.py
   ```

2. **Access the interface**:
   - Open your browser and navigate to `http://localhost:7860`
   - The application will launch automatically

## 📊 Usage Instructions

1. **Enter Patient Data**:
   - Fill in all 8 input fields with clinical measurements
   - Values should be in standard medical units

2. **Make Prediction**:
   - Click the "🔍 Predict Diabetes" button
   - Wait for the analysis to complete

3. **Interpret Results**:
   - **🩺 Diabetes Detected**: High risk - probability shown in red
   - **✅ No Diabetes Detected**: Low risk - probability shown in green
   - Probability scores indicate confidence level (0-100%)

### Input Field Guidelines

| Field | Description | Typical Range |
|-------|-------------|---------------|
| Pregnancies | Number of pregnancies | 0-20 |
| Glucose Level | mg/dL blood glucose | 0-300 |
| Blood Pressure | mm Hg diastolic | 0-140 |
| Skin Thickness | mm triceps skin fold | 0-100 |
| Insulin | μU/mL serum insulin | 0-900 |
| BMI | Body Mass Index | 10-70 |
| Diabetes Pedigree Function | Genetic predisposition score | 0.0-2.5 |
| Age | Patient age in years | 1-120 |

## 🏗️ Technical Architecture

### Core Components

1. **Model Pipeline** (`app.py`):
   - Environment configuration
   - Model and scaler loading
   - Feature engineering (insulin-glucose ratio)
   - Prediction logic with probability estimation

2. **Web Interface** (Gradio):
   - Responsive layout with input controls
   - Real-time prediction handling
   - Formatted result display

3. **Data Processing**:
   - Pandas DataFrame construction
   - Scikit-learn StandardScaler transformation
   - Feature order preservation

### Dependencies

- **gradio**: Web interface framework (≥4.0.0)
- **pandas**: Data manipulation (≥1.3.0)
- **numpy**: Numerical computing (≥1.21.0)
- **scikit-learn**: Machine learning utilities (≥1.0.0)
- **matplotlib**: Plotting (≥3.5.0)
- **seaborn**: Statistical visualization (≥0.11.0)
- **xgboost**: Gradient boosting (≥1.5.0)
- **lightgbm**: Light gradient boosting (≥3.3.0)
- **plotly**: Interactive plots (≥5.0.0)

## 🔧 Model Training

*Note: Training scripts and datasets are not included in this deployment version.*

For model retraining:
1. Original dataset: Pima Indians Diabetes Dataset or similar clinical data
2. Feature engineering includes insulin-glucose ratio calculation
3. Cross-validation and hyperparameter tuning applied
4. Final model serialized using pickle protocol

## ⚠️ Important Disclaimers

- **Medical Advisory**: This tool is for educational/research purposes only
- **Not a Substitute**: Does not replace professional medical diagnosis
- **Clinical Validation**: Should be validated by healthcare professionals
- **Data Privacy**: Ensure compliance with healthcare data regulations (HIPAA, GDPR)

## 🐛 Troubleshooting

### Common Issues

1. **Model Loading Error**:
   - Verify `diabetes_model.pkl` exists and is not corrupted
   - Ensure pickle protocol compatibility

2. **Proxy Connection Issues**:
   - Script includes automatic proxy environment cleanup
   - Check network settings if external resources needed

3. **Feature Mismatch**:
   - Input order must match training feature order exactly
   - Derived features calculated automatically

## 📈 Performance Notes

- **Response Time**: <2 seconds for prediction
- **Browser Compatibility**: Modern browsers (Chrome, Firefox, Edge)
- **Scalability**: Single-instance deployment; horizontal scaling possible

## 🤝 Contributing

This is a research/prototype system. For production use:
1. Implement proper model validation
2. Add comprehensive error handling
3. Include audit logging
4. Ensure regulatory compliance
5. Conduct clinical validation studies

## 📞 Support

For technical issues related to this implementation, review:
- Code comments in `app.py`
- Dependency versions in `requirements.txt`
- Model serialization format compatibility

---

**Version**: 1.0 - Production Ready  
**Last Updated**: January 2026  
**License**: Research/Educational Use