# Uber Ride Cancellation Prediction

## 🎯 Objective
Build a machine learning model to predict whether a customer will cancel a ride before it begins, using only booking metadata available at the time of booking.  
The goal is to optimize driver dispatch efficiency by proactively identifying high-risk cancellations.

## 📊 Dataset
The dataset includes ride booking information:
- Booking details (ID, status, datetime)
- Customer information
- Vehicle type
- Location details (pickup/drop)
- Timing metrics (VTAT - Vehicle Time of Arrival, CTAT - Customer Time of Arrival)
- Rating and payment information

## 🛠️ Tech Stack
**Python 3.x**

**Key Libraries:**
- pandas & numpy: Data manipulation
- scikit-learn: Machine learning models
- xgboost: Gradient boosting
- matplotlib & seaborn: Visualization

## 📝 Project Structure

1. **Data Preprocessing**
   - Standardized column names
   - Handled missing values
   - Combined date-time features
   - Created derived features (`is_weekend`, `hour`, etc.)

2. **Feature Engineering**
   - Time-based features (peak hours, weekday/weekend)
   - Location-based encoding
   - Customer booking patterns
   - Categorical variable encoding

3. **Model Development**
   - Three models were evaluated:
     - Logistic Regression
     - Random Forest
     - XGBoost (Best performing)

4. **Model Performance**

| Model                | Accuracy | ROC-AUC | Precision (Class 1) | Recall (Class 1) | F1-Score (Class 1) |
|----------------------|----------|---------|---------------------|------------------|--------------------|
| Logistic Regression  | 0.9402   | 0.7848  | 0.9852              | 0.1476           | 0.2568             |
| **Random Forest** (Best) | 0.9667   | 0.9532  | 1.0000              | 0.5241           | 0.6878             |
| XGBoost              | 0.9558   | 0.9539  | 0.7388              | 0.5702           | 0.6436             |

![Random Forest Confusion Matrix Plot](RF_CMatrix.PNG.png)

## 🔍 Key Findings

- High VTAT (Vehicle Arrival Time) strongly correlates with cancellations
- Ride Distance, booking value and customer ratings also influence ride cancellations moderately.


## 💡 Recommendations

- **Driver Rebalancing:** Focus on high VTAT areas
- **Dynamic Dispatching:** Proactive driver allocation
- **Customer Communication:** Early notifications for high-risk bookings
- **Continuous Monitoring:** Track VTAT and cancellation trends

## 🚀 Future Improvements

- Incorporate distance calculations between locations
- Add real-time traffic data
- Include weather conditions
- Consider special events impact

## 👥 Author
Tirthankar Raha
