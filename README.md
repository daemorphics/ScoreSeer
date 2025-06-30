# ScoreSeer: La Liga Match Outcome Prediction ⚽📊

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

Setelah menjalankan *notebook* `run.ipynb`, Anda akan melihat metrik evaluasi dan visualisasi kinerja model. Model ini bertujuan untuk mencapai akurasi dan F1-score yang tinggi dalam memprediksi hasil pertandingan.

Contoh metrik (hasil dapat bervariasi berdasarkan data dan *tuning* model):

*   Accuracy: 0.9606
*   Precision: 0.9533
*   Recall: 0.9346
*   F1-Score: 0.9439

Visualisasi seperti *Confusion Matrix* dan *ROC Curve* akan dihasilkan di direktori `reports/figures/`.

## 🛠️ Tech Stack

*   **Python**: Bahasa pemrograman utama.
*   **Pandas**: Untuk manipulasi dan analisis data.
*   **NumPy**: Untuk komputasi numerik.
*   **Scikit-learn**: Untuk *machine learning* (model `RandomForestClassifier`, metrik evaluasi).
*   **Matplotlib**: Untuk visualisasi data.
*   **Seaborn**: Untuk visualisasi data yang lebih menarik.

## Contributing

Feel free to fork this repository, open issues, or submit pull requests. Any contributions to improve the model, add new features, or enhance documentation are welcome.

## License

This project is licensed under the [Your License Name] License - see the [LICENCE.txt](LICENCE.txt) file for details.
