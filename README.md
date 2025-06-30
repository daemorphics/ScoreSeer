# ScoreSeer: La Liga Match Outcome Prediction

# ScoreSeer ⚽📊

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python&logoColor=white)](https://www.python.org/)
[![Dependencies](https://img.shields.io/badge/dependencies-up%20to%20date-brightgreen.svg)](requirements.txt)

## 🌟 Overview
ScoreSeer adalah proyek *machine learning* yang bertujuan untuk memprediksi hasil pertandingan sepak bola La Liga. Dengan memanfaatkan data historis pertandingan, termasuk statistik tim, informasi pemain, dan peristiwa pertandingan, model ini memberikan wawasan tentang potensi hasil pertandingan. Proyek ini menggunakan `RandomForestClassifier` untuk menganalisis berbagai fitur dan memprediksi apakah tim tuan rumah akan menang (target = 1) atau tidak (target = 0).

## Project Structure
This repository follows a standard data science project structure to ensure maintainability and reproducibility:

```
ScoreSeer/
├── .gitignore
├── LICENCE.txt
├── LICENSE
├── README.md
├── data/
│   └── raw/
│       └── matches_full.csv
├── models/
│   └── random_forest_model.joblib
├── notebooks/
│   ├── .gitkeep
│   └── run.ipynb
├── references/
│   └── folder_structure.txt
├── reports/
│   ├── Confusion Matrix heatmap.png
│   └── ROC Curve.png
├── requirements.txt
└── src/
    └── __init__.py
```

## Installation

To set up the project locally, follow these steps:

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/daemorphics/ScoreSeer.git
    cd ScoreSeer
    ```

2.  **Create a virtual environment (recommended):**
    ```bash
    python -m venv venv
    # On Windows
    .\venv\Scripts\activate
    # On macOS/Linux
    source venv/bin/activate
    ```

3.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

## Usage

### Data Preparation

Ensure you have your raw match data (e.g., `matches_full.csv`) placed in the `data/raw/` directory.

### Running the Notebook

The `notebooks/run.ipynb` file contains the full workflow from data loading and preprocessing to model training, prediction, and evaluation.

1.  **Start Jupyter Notebook:**
    ```bash
    jupyter notebook
    ```

2.  **Navigate to `notebooks/run.ipynb`** and open it.

3.  **Run all cells** in the notebook sequentially. The notebook will perform the following steps:
    *   Load raw data.
    *   Convert datetime columns and create the target variable.
    *   Handle missing values.
    *   Calculate rolling averages for key performance metrics.
    *   Perform one-hot encoding on categorical features.
    *   Split data into training and testing sets.
    *   Train a `RandomForestClassifier` model.
    *   Make predictions and evaluate model performance (Accuracy, Precision, Recall, F1-Score).
    *   Visualize results using Confusion Matrix and ROC Curve.

### Model Evaluation

The notebook includes code to evaluate the model's performance using standard metrics:

*   **Accuracy:** Overall correctness of the model.
*   **Precision:** Ability of the model to correctly identify positive cases.
*   **Recall:** Ability of the model to find all positive cases.
*   **F1-Score:** Harmonic mean of precision and recall.
*   **Confusion Matrix:** A table showing true positives, true negatives, false positives, and false negatives.
*   **ROC Curve and AUC:** Visual representation of the classifier's performance across all possible classification thresholds.

### Using External Data for Prediction

To test the trained model with new, external data, ensure the external data is in the same format as the training data. The notebook provides a section demonstrating how to load new data and apply the same preprocessing steps before making predictions.

## 📈 Results

After running the `run.ipynb` notebook, you will see the evaluation metrics and visualizations of the model's performance. The model aims to achieve high accuracy and F1-score in predicting match outcomes.

Example metrics (results may vary based on data and model tuning):

*   Accuracy: 0.9606
*   Precision: 0.9533
*   Recall: 0.9346
*   F1-Score: 0.9439

Visualizations such as the Confusion Matrix and ROC Curve will be generated in the `reports/figures/` directory.

## 🛠️ Tech Stack

*   **Python**: The primary programming language.
*   **Pandas**: For data manipulation and analysis.
*   **NumPy**: For numerical computations.
*   **Scikit-learn**: For machine learning (RandomForestClassifier model, evaluation metrics).
*   **Matplotlib**: For data visualization.
*   **Seaborn**: For enhanced data visualization.

## Contributing

Feel free to fork this repository, open issues, or submit pull requests. Any contributions to improve the model, add new features, or enhance documentation are welcome.

## License

This project is licensed under the [Your License Name] License - see the [LICENCE.txt](LICENCE.txt) file for details.