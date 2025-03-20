# AI-Powered Resume Analysis and Intelligent Job Recommendation System

[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Overview

This project provides an intelligent solution for analyzing resumes and recommending suitable job opportunities. Leveraging the power of Natural Language Processing (NLP) and Machine Learning, the application efficiently processes uploaded resumes to categorize their professional domain, extract key information, and suggest relevant job roles. This tool is designed to streamline the job application process for individuals and enhance talent acquisition for recruiters.

## Key Features

* **Intelligent Resume Parsing:** Accepts resume uploads in both PDF and TXT formats, extracting textual content for analysis.
* **Automated Resume Categorization:** Employs a sophisticated machine learning model to automatically classify resumes into predefined professional categories (e.g., HR, Information Technology, Design).
* **Personalized Job Recommendation:** Utilizes a dedicated machine learning model to analyze resume content and recommend relevant job titles based on skills and experience.
* **Comprehensive Information Extraction:** Automatically identifies and extracts crucial details from resumes, including:
    * Contact Information (Phone Number, Email Address)
    * Technical and Soft Skills
    * Educational Qualifications
    * Applicant's Name
* **Scalable Web Application:** Built using the robust and flexible Flask framework, making it easily deployable and scalable.
* **Robust Model Training Pipeline:** Includes well-documented Jupyter notebooks detailing the data preprocessing, model training, and evaluation processes for both categorization and recommendation models.

## Technologies

This project is built using the following key technologies:

* **Backend Framework:** Python (>=3.7) with Flask
* **PDF Processing:** PyPDF2
* **Text Extraction (Alternative):** pdfminer.six
* **Machine Learning & Data Analysis:**
    * scikit-learn
    * pandas
    * numpy
* **Data Visualization (for Model Development):**
    * matplotlib
    * seaborn
* **Version Control:** Git

## Installation

Follow these steps to set up the project locally:

1.  **Clone the repository:**
    ```bash
    git clone <your_repository_url>
    cd <your_project_directory>
    ```
    *(Replace `<your_repository_url>` and `<your_project_directory>` with the actual URL and directory name.)*

2.  **Install Dependencies:**
    It is highly recommended to create a virtual environment for this project.
    ```bash
    # Create a virtual environment (if you don't have one already)
    python -m venv venv
    # Activate the virtual environment
    source venv/bin/activate  # On Linux/macOS
    venv\Scripts\activate  # On Windows

    # Install the required Python packages
    pip install -r requirements.txt
    ```
    *(Create a `requirements.txt` file with the following content, or generate it using `pip freeze > requirements.txt` after installing the dependencies manually):*
    ```
    Flask>=2.0
    PyPDF2>=1.27
    scikit-learn>=1.0
    pandas>=1.3
    numpy>=1.21
    matplotlib>=3.4
    seaborn>=0.11
    pdfminer.six>=20221105
    ```

3.  **Verify Model Availability:**
    Ensure that the pre-trained machine learning models are located in the `models` directory within the project. These files should include:
    * `rf_classifier_categorization.pkl`
    * `tfidf_vectorizer_categorization.pkl`
    * `rf_classifier_job_recommendation.pkl`
    * `tfidf_vectorizer_job_recommendation.pkl`

## Usage

1.  **Run the Flask Application:**
    ```bash
    python app.py
    ```

2.  **Access the Web Interface:**
    Open your web browser and navigate to `http://127.0.0.1:5000/`.

3.  **Upload Your Resume:**
    On the homepage, you will find a file upload section. Click "Choose File" and select your resume in either PDF or TXT format.

4.  **Analyze Resume:**
    Click the "Upload" button to submit your resume for analysis.

5.  **View Results:**
    The application will process your resume and display the following results on the same page:
    * **Predicted Resume Category:** The identified professional domain of your resume.
    * **Recommended Job Role:** A suggested job title based on your resume content.
    * **Extracted Contact Information:** Your phone number and email address (if found).
    * **Extracted Skills:** A list of technical and soft skills identified in your resume.
    * **Extracted Education:** The educational qualifications mentioned in your resume.
    * **Extracted Name:** The name identified from your resume.

## Model Training and Datasets

The machine learning models at the core of this application were developed using the provided Jupyter notebooks:

* **`Resume Catogorization prediction.ipynb`:** This notebook details the process of training the Random Forest classifier for resume categorization. The training data likely resides in the `clean_resume_data.csv` file.
* **`Resume Job Recommendation System.ipynb`:** This notebook outlines the training of the Random Forest classifier for job recommendation, potentially using the `jobs_dataset_with_features.csv` dataset.

These notebooks provide a transparent view into the model development lifecycle, including data loading, preprocessing, feature engineering (using TF-IDF vectorization), model selection, training, and evaluation.

## Contributing

We encourage contributions to make this project even better! If you have suggestions for improvements, bug fixes, or new features, please follow these guidelines:

1.  **Fork the repository:** Create your own copy of the project on GitHub.
2.  **Create a new branch:** `git checkout -b feature/your-feature-name` or `git checkout -b bugfix/your-bug-fix`.
3.  **Make your changes:** Implement your desired modifications or fixes.
4.  **Commit your changes:** `git commit -m "Add your descriptive commit message"`
5.  **Push to the branch:** `git push origin feature/your-feature-name` or `git push origin bugfix/your-bug-fix`.
6.  **Open a Pull Request:** Submit a pull request from your branch to the main repository. Please provide a clear description of your changes and their purpose.

## License

This project is licensed under the [MIT License](LICENSE). See the `LICENSE` file for more details.

## Acknowledgements

We would like to acknowledge the open-source community and the developers of the libraries used in this project for their valuable contributions.
