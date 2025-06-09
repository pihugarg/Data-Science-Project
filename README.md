Bangalore Property Value Predictor

This Helpbook will guide you through installing, using, and understanding the core features of the Bangalore Property Value Predictor web application.

Installation Guide
Clone or Download the Project:
•	Download or clone the project folder from your repository.
•	Open the project in PyCharm Community Edition.

Install Dependencies
Use the following command to install all required packages:
pip install pandas numpy scikit-learn joblib


Running the Application
Step 1: Start the Backend Server 
In PyCharm terminal or your system terminal, run:
python server.py

Step 2: Open Frontend	
Open app.html in a browser.
The frontend (HTML/CSS/JS) is connected to the backend and communicates via HTTP requests (e.g., using fetch() from app.js).
(typically at local host-http://127.0.0.1:5000).

How to Use:
User Input Form
Enter property details such as:
•	Location
•	Total Square Footage
•	Number of Bathrooms
•	Number of BHK (Bedrooms, Hall, Kitchen)
Get Prediction
Click the "Predict Price" button.
The predicted property price (in ₹ lakhs) is displayed immediately.
Optional Visuals
View model performance charts or feature importance graphs, if included.

How It Works
Dataset
•	Source: Kaggle Bengaluru House Price Data
•	Total Records: 13,320
•	Features: Location, size, square footage, bathrooms, balconies, etc.
Preprocessing
•	Missing values handled via imputation or removal.
•	Numerical features scaled using StandardScaler.
•	Categorical features (like location) encoded using One-Hot Encoding.
Feature Selection
•	Recursive Feature Elimination (RFE) and correlation analysis applied.
•	Redundant features removed; PCA used for variance preservation.
Skewness & Outliers
•	Outliers identified in sqft, price/sqft, and BHK.
•	Log transformation applied to skewed data for normalization.
Models Used
•	Linear Regression: Best overall performance
•	Lasso Regression: Helped in feature selection
•	Decision Tree Regressor: Handled non-linear data but prone to overfitting
Hyperparameter Tuning
•	Used Grid Search and Randomized Search
•	Optimized using cross-validation scores

Evaluation Metrics
•	R² Score: Measures model fit
•	MAE: Mean Absolute Error
•	MSE: Mean Squared Error
•	RMSE: Root Mean Squared Error

Deployment Details
•	Backend: server.py – Handles preprocessing, prediction, and response
•	Frontend: HTML + CSS + app.js for UI and HTTP communication
•	Model: Final LinearRegression model stored via joblib
•	Validation: Ensures all form inputs are meaningful before prediction
•	Hosting: Localhost – typically at http://127.0.0.1:5000

Files & Folders Guide
Folder/File	Description
dataset/	Raw and cleaned Kaggle dataset files
models/	Saved models (linear_regression_model.pkl, scaler.pkl)
Server.py 	  Backend server handling predictions
util.py 	  Contains helper functions (e.g., preprocessing, transformation)
app.js 		   Frontend logic to send inputs and display predictions
app.html 	   Web page layout and structure
app.css	   Custom styling for the web page

Troubleshooting
Issue	Solution
Server not starting 				Ensure dependencies are installed; server.py
Model not loading 				Confirm file paths and model file exists in /models/
No prediction response	Check if frontend correctly communicates with backend

Incorrect predictions 	Recheck preprocessing pipeline and model training
UI not displaying well	Inspect app.html and app.css for errors

Discussion
•	Linear Regression delivered the most reliable and generalizable results.
•	Lasso Regression helped eliminate unnecessary features.
•	Decision Tree Regressor captured non-linear relationships but overfit the data.
•	HTML/CSS/JavaScript provided a clean, interactive frontend.
•	PyCharm Community Edition allowed seamless development and debugging.

Conclusion
This project demonstrates a complete ML pipeline — from data preprocessing to deployment — applied to predicting real-estate prices in Bangalore. It combines:
•	Data science techniques (EDA, modeling, validation)
•	Software development (backend APIs, UI design)
•	Practical deployment (custom server + web interface


Future Enhancements
•	Incorporate external data (e.g., metro stations, schools, crime rate)
•	Add charts for data insights using charting libraries (e.g., Chart.js)
•	Build user authentication for multiple users


