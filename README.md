# 🏸 Covid Tennis Coach

**Covid Tennis Coach** is a real-time feedback tool for tennis players built during the COVID-19 pandemic, when in-person coaching and practice partners weren’t an option. It uses a Bluetooth-connected Arduino with an IMU sensor mounted on a tennis racket to track motion data, and a custom-trained logistic regression model to classify each shot as “good” or “bad” based on the user's own training data.

---

## 📦 Features

- **Real-Time Shot Feedback**: Provides instant evaluation of tennis shots using gyroscope and accelerometer data.
- **Personalized Model Training**: Train a logistic regression classifier on your own labeled shot data.
- **Data Visualization**: View scatter plots and sigmoid curves to understand shot confidence and classification boundaries.
- **Error Analysis**: Highlights which gyroscopic dimension was most off in incorrectly classified shots.

---

## 🛠️ Tech Stack

- **Python** – Core logic and ML modeling (scikit-learn, pandas, matplotlib)
- **Arduino** – IMU sensor data collection
- **Logistic Regression** – Binary classifier to label shots
- **Bluetooth** – Racket-to-computer communication (via Arduino)

---

## 📈 How It Works

1. **Collect Data**: Sensor readings from accelerometer (`aX`, `aY`, `aZ`) and gyroscope (`gX`, `gY`, `gZ`) are collected during practice shots.
2. **Label Shots**: Each shot is labeled as `good (1)` or `bad (0)` to build a training dataset.
3. **Preprocess**: Sensor data is standardized and summed to simplify input for the logistic regression model.
4. **Train Model**: A binary classifier is trained on the user’s labeled dataset.
5. **Live Prediction**: New shots are analyzed in real-time; the model provides feedback, and identifies which motion dimension is most off for incorrect shots.

---

## 📊 Sample Visualization

- Summed motion data plotted against model confidence.
- Sigmoid curve illustrates the classification boundary.
- Gyroscope data breakdown for misclassified shots.

---

## 🚧 Future Improvements

- Real-time mobile feedback via Bluetooth.
- Advanced modeling (e.g. SVM or neural nets) for better shot analysis.
- More granular classification (e.g. topspin forehand, slice, volley).

---

## 📁 Data

- Training and testing CSVs contain columns: `aX`, `aY`, `aZ`, `gX`, `gY`, `gZ`, `g_b` (`g_b` = 1 if shot is good, 0 if bad).

---

## 🔗 Links

*This project was developed in Google Colab in 2021 and uploaded to Github in 2025*. View the full notebook here:  
[🔗 Colab Notebook](https://colab.research.google.com/drive/1enXVq_m2Cm8pYgehMSUa3IE_GoXPneM-)

