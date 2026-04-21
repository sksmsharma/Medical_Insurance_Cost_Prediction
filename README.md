# Medical_Insurance_Cost_Prediction
A machine learning project that predicts individual medical insurance charges based on demographic and health-related features using Linear Regression.


##  Overview

Healthcare costs are a significant concern for individuals and insurance providers alike. This project leverages machine learning to build a predictive model that estimates annual medical insurance charges for a person based on key personal attributes such as age, BMI, smoking habits, and region.

The goal is to provide an accurate and interpretable cost prediction tool that can assist insurers in risk assessment and help individuals estimate their healthcare expenses.

---

##  Objectives

- Perform comprehensive **Exploratory Data Analysis (EDA)** to understand the distribution and relationships among features.
- Identify key factors that significantly influence medical insurance costs.
- Preprocess the data by **encoding categorical variables** for model compatibility.
- Train a **Linear Regression** model to predict insurance charges.
- Evaluate model performance using the **R² (R-squared) metric** on both training and test sets.
- Build a **prediction pipeline** that can estimate insurance cost for new input data.

---

##  Dataset

The dataset used is the popular **insurance.csv** dataset, which contains **1,338 records** with the following attributes:

| Column     | Description                                         | Type        |
|------------|-----------------------------------------------------|-------------|
| `age`      | Age of the primary beneficiary                      | Numerical   |
| `sex`      | Gender of the policyholder (male/female)            | Categorical |
| `bmi`      | Body Mass Index — a measure of body fat             | Numerical   |
| `children` | Number of children/dependents covered               | Numerical   |
| `smoker`   | Whether the policyholder is a smoker (yes/no)       | Categorical |
| `region`   | Residential area in the US (NE/NW/SE/SW)            | Categorical |
| `charges`  | Individual medical costs billed by insurance (USD)  | **Target**  |

---

##  Features

-  **Exploratory Data Analysis (EDA)**
  - Age distribution visualization
  - Gender and smoker count plots
  - BMI distribution analysis
  - Children count distribution
  - Regional distribution
  - Medical charges distribution

-  **Data Preprocessing**
  - Null value detection and handling
  - Label encoding of categorical features (`sex`, `smoker`, `region`)
  - Feature-target separation

-  **Model Training**
  - Linear Regression using Scikit-Learn
  - 80/20 train-test split

-  **Model Evaluation**
  - R² score on training data
  - R² score on test data

-  **Prediction System**
  - Real-time cost prediction for custom input data

---

## Project Workflow

```
Data Collection → EDA → Data Preprocessing → Feature Engineering
       ↓
Model Training (Linear Regression)
       ↓
Model Evaluation (R² Score)
       ↓
Predictive System
```

---

## 📐 Model Performance

| Dataset       | R² Score |
|---------------|----------|
| Training Data | ~0.75    |
| Test Data     | ~0.74    |

> *Note: Actual scores may vary slightly based on environment.*

---

## ⚙️ Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/medical-insurance-cost-prediction.git
   cd medical-insurance-cost-prediction
   ```

2. **Create a virtual environment (recommended)**
   ```bash
   python -m venv venv
   source venv/bin/activate      # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Launch the notebook**
   ```bash
   jupyter notebook Medical_Insurance_Cost_Prediction.ipynb
   ```

---

## Usage

To predict the insurance cost for a new individual, modify the `input_data` tuple at the end of the notebook:

```python
# Format: (age, sex, bmi, children, smoker, region)
# sex     → 0: male, 1: female
# smoker  → 0: yes,  1: no
# region  → 0: southeast, 1: southwest, 2: northeast, 3: northwest

input_data = (31, 1, 25.74, 0, 1, 0)

input_data_as_numpy_array = np.asarray(input_data)
input_data_reshaped = input_data_as_numpy_array.reshape(1, -1)

prediction = regressor.predict(input_data_reshaped)
print('The insurance cost is USD', prediction[0])
```

---

## 🛠️ Tech Stack

| Tool/Library     | Purpose                          |
|------------------|----------------------------------|
| Python 3.8+      | Core programming language        |
| NumPy            | Numerical computations           |
| Pandas           | Data manipulation & analysis     |
| Matplotlib       | Data visualization               |
| Seaborn          | Statistical data visualization   |
| Scikit-Learn     | Machine learning model & metrics |
| Jupyter Notebook | Interactive development environment |

---

## 📦 Requirements

```
numpy
pandas
matplotlib
seaborn
scikit-learn
jupyter
```

> Save these as `requirements.txt` and install using `pip install -r requirements.txt`.

---

## Project Structure

```
medical-insurance-cost-prediction/
│
├── Medical_Insurance_Cost_Prediction.ipynb   # Main notebook
├── insurance.csv                             # Dataset
├── requirements.txt                          # Project dependencies
└── README.md                                 # Project documentation
```

---

## Results

- Successfully built a regression model that explains approximately **74–75% of the variance** in insurance charges.
- Found that **smoking status** and **BMI** are among the most influential factors in determining insurance costs.
- The prediction pipeline accurately estimates costs for new unseen inputs.

---

## Contributing

Contributions, issues, and feature requests are welcome! Feel free to:
1. Fork the repository
2. Create a new branch (`git checkout -b feature/improvement`)
3. Commit your changes (`git commit -m 'Add some improvement'`)
4. Push to the branch (`git push origin feature/improvement`)
5. Open a Pull Request

---

## License

This project is licensed under the [MIT License](LICENSE).

---

## Author

**Saksham Sharma**
- GitHub: [@sksmsharma](https://github.com/sksmsharma)
- LinkedIn: [saksham-sharma21](https://linkedin.com/in/saksham-sharma)

---


