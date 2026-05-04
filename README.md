🛠 Model Artifacts
The model artifacts listed below are the core components necessary to run the RootSense Soil Intelligence Pipeline. These files handle everything from predictive modeling to human-readable output and explainability.

🤖 Predictive Models
score_regressor_rf.joblib

The primary Soil Health Score model. This is a Random Forest Regressor (best_rf_reg) that predicts a numerical soil health score on a scale of 0–100.

crop_classifier_xgb.joblib

The Crop Recommendation model. This XGBoost Classifier (best_xgb_crop) predicts the most suitable crop based on environmental and soil data.

soil_classifier_rf.joblib

The Soil Type Identification model. A Random Forest Classifier (best_rf_soil) used to identify the specific category of soil.

🔍 Interpretability & Metadata
shap_explainer_score.joblib

The SHAP TreeExplainer (explainer_score) trained specifically on the Soil Health Score model. This is crucial for the SHAP Explainability feature, allowing you to understand which sensor readings are driving the soil health score up or down.

label_encoder_crop.joblib

A mapping object (le_crop) used to convert the numerical outputs of the Crop Recommendation model back into human-readable crop names (e.g., turning a model's prediction of 0 into 'Maize').

label_encoder_soil.joblib

Similar to the crop encoder, this object (le_soil) converts the numerical outputs of the Soil Type Identification model back into human-readable soil type names (e.g., turning a model's prediction of 0 into 'Clay').

⚙️ Configuration
pipeline_config.json

The blueprint for the entire inference pipeline. This JSON file contains all non-model configuration parameters, such as:

Lists of raw and engineered features.

Ideal ranges and weights used for calculating the soil health score.

Defined crop and soil type classes.

It guides exactly how raw sensor data is transformed and interpreted by the models.
