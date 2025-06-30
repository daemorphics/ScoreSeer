# ScoreSeer: La Liga Match Outcome Prediction

## Overview
ScoreSeer is a machine learning project aimed at predicting the outcomes of La Liga football matches. By leveraging historical match data, including team statistics, player information, and match events, the model provides insights into potential match results. This project utilizes a RandomForestClassifier to analyze various features and predict whether a home team will win (target = 1) or not (target = 0).

## Project Structure
This repository follows a standard data science project structure to ensure maintainability and reproducibility:

```
ScoreSeer/
├── data/
│   ├── external/       # Data from external sources (e.g., web scraping)
│   ├── interim/        # Intermediate data that has been transformed
│   ├── processed/      # The final, canonical data sets for modeling
│   └── raw/            # The original, immutable raw data
├── docs/
│   └── .gitkeep        # Project documentation
├── models/
│   └── .gitkeep        # Trained and serialized models
├── notebooks/
│   └── run.ipynb       # Jupyter notebooks for experimentation and development
├── reports/
│   ├── figures/        # Generated plots and figures for reports
│   └── .gitkeep
├── src/
│   ├── data/           # Scripts to download or generate data
│   ├── features/       # Scripts to build features from raw data
│   ├── models/         # Scripts to train models and make predictions
│   └── visualization/  # Scripts to create visualizations
├── .gitignore          # Specifies intentionally untracked files to ignore
├── LICENCE.txt         # Project license
├── LICENSE             # Project license
├── README.md           # This README file
├── requirements.txt    # Python dependencies
└── folder_structure.txt # Explanation of the folder structure
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

## Results

After running the `run.ipynb` notebook, you will see the evaluation metrics and visualizations of the model's performance. The model aims to achieve high accuracy and F1-score in predicting match outcomes.

Example metrics (results may vary based on data and model tuning):

*   Accuracy: 0.9606
*   Precision: 0.9533
*   Recall: 0.9346
*   F1-Score: 0.9439

Visualizations such as the Confusion Matrix and ROC Curve will be generated in the `reports/figures/` directory.

## Contributing

Feel free to fork this repository, open issues, or submit pull requests. Any contributions to improve the model, add new features, or enhance documentation are welcome.

## License

This project is licensed under the [Your License Name] License - see the [LICENCE.txt](LICENCE.txt) file for details.