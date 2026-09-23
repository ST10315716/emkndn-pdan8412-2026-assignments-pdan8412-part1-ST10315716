# PDAN8412 Part 1 – RNN & LSTM Author Prediction

**Student:** Ubaid Omarjee
**Student Number:** ST10315716
**Module:** PDAN8412 – Programming for Data Analytics 2

## About the Project

This project uses **Recurrent Neural Networks (RNNs)** and **Bidirectional LSTM** to predict the author of a blog post based on writing style.

The **Blog Authorship Corpus** was analysed using **Apache Spark** and processed using **TensorFlow/Keras**. The project includes data cleaning, exploratory analysis, text preprocessing, model training, evaluation and hyperparameter experimentation.

## Dataset

The project uses the **Blog Authorship Corpus**, containing blog posts and author information.

**Dataset:** Blog Authorship Corpus
**Source:** Kaggle
**Link:** https://www.kaggle.com/datasets/rtatman/blog-authorship-corpus

The original dataset contains **681,284 records** from **19,320 authors**. Ten authors were selected for the final classification task.

## Technologies Used

* Python
* Google Colab
* Apache Spark / PySpark
* TensorFlow & Keras
* Scikit-learn
* Pandas
* NumPy
* Matplotlib
* Seaborn

## Setup & Usage

### Requirements

The project is designed to run in **Google Colab**.

The notebook installs the additional required packages automatically:

```python
!pip -q install pyspark kagglehub
```

TensorFlow, Pandas, NumPy, Scikit-learn and the plotting libraries are used for the analysis and modelling.

### Running the Notebook

1. Open the `.ipynb` notebook in **Google Colab**.
2. Run the notebook **from top to bottom**.
3. The notebook automatically downloads the Blog Authorship Corpus using **KaggleHub**.
4. Apache Spark is started locally using the available Colab resources.
5. The notebook performs:

   * Dataset loading and inspection
   * Data quality checks
   * Author selection and balancing
   * Text cleaning
   * Exploratory data analysis
   * Text vectorisation
   * Train/validation/test splitting
   * Bidirectional LSTM training
   * Model evaluation
   * Confusion matrix analysis
   * Hyperparameter experimentation
   * Example prediction

A fixed random seed of **42** is used to improve reproducibility.

## Data Processing

The original dataset was reduced to a manageable working dataset of **10,000 records**, with 1,000 posts initially selected for each of ten authors.

After cleaning:

* **8,524 records** remained
* **10 authors** remained
* Short texts and duplicate author-text records were removed

The final dataset was divided into:

* **Training:** 6,819
* **Validation:** 852
* **Testing:** 853

## Model

The baseline model uses:

* TextVectorization
* Embedding layer
* Bidirectional LSTM – 64 units
* Dense layer – 64 units
* Dropout – 0.50
* Softmax output – 10 classes
* Adam optimiser
* Learning rate – 0.001

The text vectorisation uses a **20,000-word vocabulary** and a **sequence length of 300 tokens**.

## Results

The final baseline Bidirectional LSTM achieved:

| Metric             |     Result |
| ------------------ | ---------: |
| Test Accuracy      | **54.87%** |
| Weighted Precision | **53.93%** |
| Weighted Recall    | **54.87%** |
| Weighted F1-Score  | **52.42%** |

An experimental model was also tested with different LSTM capacity, dropout and learning-rate settings. The baseline model achieved higher test performance and was therefore retained as the final model.

## Repository Files

* `PDAN8412_Part1_ST10315716_Google_Collab.ipynb` – Complete Google Colab notebook
* `ST10315716_PDAN8412_PART1_REPORT.pdf` – Final written report
* `README.md` – Project documentation

## Example Prediction

The final model was tested using an artificial text sample.

**Predicted Author:** `303162`
**Prediction Probability:** **89.44%**

This probability represents the model's prediction for the selected class and should not be interpreted as proof of authorship.

## Conclusion

The project demonstrates how **Apache Spark, TensorFlow, Keras and Bidirectional LSTM networks** can be used for text classification and author prediction.

The final model achieved **54.87% test accuracy** and a **52.42% weighted F1-score** on the selected ten-author classification task.

## Author

**Ubaid Omarjee**
**ST10315716**
**PDAN8412 – Programming for Data Analytics 2**
