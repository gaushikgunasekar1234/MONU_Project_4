# Real vs Fake News Classification

Submitted for Monash University Bootcamp Project 4.

## Description
With the lines of truth being blurred between real and fake in the daily news, every day people becoming more reliant on social media for their news sources - it is more important than ever to be able to differentiate the two for reliable and accurate new sources. In light of this, we've built an effective model using data analysis, machine learning and Neural Network to judge news stories. Our frontend, powered by Streamlit, lets users easily check articles. Simply put in the text, hit submit, and get an immediate real-or-fake verdict.

## Dataset
Our analysis is grounded on a comprehensive dataset that separates authentic news from fake stories. We sourced our data from a widely-recognized collection available on Kaggle, which comprises two CSV files—one with verified news and the other with false news. 

The key points about the dataset:
- **Source**: [Fake and Real News Dataset](https://www.kaggle.com/datasets/clmentbisaillon/fake-and-real-news-dataset) on Kaggle
- **Composition**: Two CSV files, one labeled 'Fake' and the other 'True'.
- **Data Fields**: Each record includes the title, text, subject, and date of the news article.
- **Volume**: The dataset provides a substantial number of articles, offering a robust foundation for training our machine learning model.

## Toolkit
- Python (pandas, pathlib, matplotlib, numpy, seaborn, scikit-learn, nltk, spacy, tensorflow, keras) 
- Streamlit for web application frontend
- Tableau for advanced data visualizations and data analysis
  
## Applications/Code Editors
- Jupyter Notebook
- Google Colab
- VS Code
 
## File Structure
This repository is organized into several directories and key files as follows:
- `/Resources/`: Raw CSV files of fake and true news articles used for analysis.
- `DataExploration.ipynb`: Jupyter notebook for initial data exploration and analysis.
- `SentimentAnalysis.ipynb`: Jupyter notebook for conducting sentiment analysis on the dataset.
- `DataModelling_SVM_NB.ipynb`: Notebook containing code for machine learning modelling using Naive Bayes and Support Vector Machines classifiers.
- `model_svm.pkl`: Support Vector Machines classification model.
- `model_naive.pkl`: Naive Bayes classification model.
- `DataModelling_LSTM.ipynb`: Notebook containing code for Neural Network modelling using RNN-LSTM/BiLSTM. This also includes unit testing for the successful model.
- `streamlit_BiLSTM.py`: Python and Streamlit code for frontend output by using BiLSTM model.
- `P4.twbx`: Tableau workbook download
- `/Output/`: Contains output files such as processed datasets or results from the analysis.
- `Presentation.pdf`: Pdf version of the powerpoint presentation of the project.
- `README.md`: Documentation explaining the project, its structure, and how to run it.

### Additional deliverables:
- Explore our `BiLSTM model` in detail: [View Model](https://drive.google.com/file/d/1jKFM2dT83sMtHRZO8X3xWp8I6pVy0SPV/view?usp=sharing)  
- Dive into our `Tableau` data visualizations: [View Presentation](https://public.tableau.com/views/P4_16990786163050/Homepage?:language=en-GB&publish=yes&:display_count=n&:origin=viz_share_link)

Explore our BiLSTM model in detail: View Model
Dive into our data visualizations: View Tableau Presentation

## Structure

### Backend

### Exploratory Data Analysis (EDA)
The EDA process involved examining and summarizing the main characteristics of the dataset, often using visual methods.
It provided a better understanding of the data's distribution and uncovered patterns, anomalies, and relationships between variables. </br>
The EDA was conducted in two distinct Jupyter notebooks: `DataExploration.ipynb` and `SentimentAnalysis.ipynb`.  </br>
`DataExploration.ipynb` focused on initial data exploration, including data cleaning and standardization, while `SentimentAnalysis.ipynb` delved deeper into the emotional tone of the articles through sentiment analysis, utilizing natural language processing techniques to assess the polarity and subjectivity of the text.


##### Data Exploration (`DataExploration.ipynb`)
Utilising Google Colab to separately inspect the fake and true CSV files, the initial phase of the process involved data cleaning, which included segregating the publisher information into a distinct column to enhance the clarity of the text column. After a thorough review of the publisher data, it became apparent that the predominant source of information was Reuters outlets in the United States, with some contributions from global sources. Further data cleansing steps were undertaken, including the removal of duplicate articles, headlines, and date information, as the latter was considered irrelevant for the analysis.

![1](https://github.com/jyojay/MONU_Project_4/assets/134185577/1a8099a9-da03-450e-89ff-5eb21b497433)

Following these data preparation activities, the cleaned datasets were merged and produced multiple visualisations to generate insights. These visualisations encompassed:
- comparisons of real vs. fake news article counts

  ![2](https://github.com/jyojay/MONU_Project_4/assets/134185577/ae751438-9c76-4bea-9736-a97746ae1929)

- a pie chart illustrating the percentage distribution by subject
  
  ![3](https://github.com/jyojay/MONU_Project_4/assets/134185577/c41bc249-91ac-4e67-a824-28ef9b3e199e)

- an analysis of the number of words in the text, a word cloud visualization

  ![4](https://github.com/jyojay/MONU_Project_4/assets/134185577/6a40c049-eaa6-4b0f-9799-c62f107f35c8)

  
- an examination of unigrams, bigrams, and trigrams to identify key word combinations.

  ![6](https://github.com/jyojay/MONU_Project_4/assets/134185577/8f0512c0-10f5-4bc4-ae47-4528dded5dfb)


This comprehensive analysis enabled the identification of valuable insights and trends within the dataset, providing a deeper understanding of the characteristics and patterns associated with fake and true news articles.


##### Sentiment Analysis (`SentimentAnalysis.ipynb`) 
- **Objective**: To assess the emotional tone and subjectivity of news articles, differentiating between true and fake news.
- **Process**:
  - Loaded and cleaned articles from a cleaned CSV file containing both fake and true news, standardizing text for analysis.
  - Tokenized articles using spaCy and NLTK to break down text into individual words, removing stopwords and non-alphabetic characters.
  - Calculated word frequency distribution to identify the most common words in true and fake news.
  - Generated word clouds for a visual depiction of frequent words in each news type.
    
    ![1](https://github.com/jyojay/MONU_Project_4/assets/134185577/4fca347b-ca77-4758-bf92-2146835aa456)
    
  - Analyzed polarity and subjectivity using TextBlob to evaluate the emotional content and the amount of personal opinion in articles.
  - Categorized articles based on polarity scores and compared sentiment distribution between true and fake news.

    ![2](https://github.com/jyojay/MONU_Project_4/assets/134185577/bb10da28-03c8-4651-80be-4843742af99f)

  - Plotted histograms to show the polarity distribution, revealing sentiment trends within articles.
 
    ![3](https://github.com/jyojay/MONU_Project_4/assets/134185577/240b32ac-5e2e-4b92-9b99-f12bb7f47652)

  - Calculated and compared average polarity and subjectivity scores between true and fake news.
 
    ![4](https://github.com/jyojay/MONU_Project_4/assets/134185577/7087c3f1-31d9-43fa-ac65-f69edd0b5fe1)
    
- **Findings**:
  - Both true and fake news articles generally have a slightly positive tone, with fake news showing a higher average polarity  
  - Fake news articles exhibit a higher level of subjectivity, indicating more opinion-based content.
  - A higher proportion of negatively toned articles were found in fake news compared to true news.
  - Politically charged words were often associated with negative sentiments in fake news ("trump", "clinton", "obama", "police", "media").
  
   ![5](https://github.com/jyojay/MONU_Project_4/assets/134185577/b4324c5f-c4d8-4f7d-ae1e-b64827fe6d35)

### Machine Learning and Recurrent Neural Network Modelling  

#### Machine Learning Models
Since we had a two-group classification problem at hand vis-a-vis Fake and True, we started out exploring various models and zeroed out on two Machine Learning `(ML) Models` and two `Recurrent Neural Network (RNN)` models for our purpose. Ref: https://developers.google.com/machine-learning/guides/text-classification/step-2-5 </br>
**ML Models** </br>
1)	`Naïve Bayes` – This model was chosen because, despite its simplicity, it can handle large feature spaces, which makes them suitable for text classification where the feature set can be the size of the vocabulary. Ref: https://web.stanford.edu/class/cs124/lec/naivebayes2021.pdf
2)	`Support Vector Machines (SVM)` – This model was selected due to their capability to manage high dimensionality and establish effective decision boundaries in the form of hyperplanes.  Ref: https://www.cs.cornell.edu/people/tj/svmtcatbook/ </br>

**RNN-LSTM Models**</br>
1)	`Long Short-term Memory (LSTM)` – We were looking for a model that could process Natural Language and selected this model due to its ability to process sequential data and remember patterns over time. 
2)	`Bidirectional LSTM (BiLSTM)` – To improve the model we selected this extension of the traditional LSTM since It involves duplicating the first recurrent layer in the network so that there are two layers side-by-side in training. This was done to provide additional training to the model to improve predictions.

#### Data Preperation for model training
Data which was tokenized, lemmatized and from which stop words and special characters were removed in the EDA step was taken as an input for both ML and RNN-LSTM modules.</br></br>

1) **ML Models** </br>
Input data was vectorized using SKLearn TfidfVectorizer</br>

2) **RNN-LSTM Models**</br>
The input data was tokenized to numeric form using TensorFlow/Keras Tokenizer and then padded using pad_sequences.</br>

**Jupyter notebook on desktop was used for ML models whereas Google Colab was used for training Neural Network Models due to GPU processing requirements.** </br>

#### Model training and Results
1) **ML Models** 
  -	The data was split into Train and Test data at 3:1 ratio.
  -	Target used: class column values which were 0 or 1 depending on Fake or True news  
  -	Features used: text column values with the news text</br></br>
  
**Naive Bayes Model** </br></br>
   ![image](https://github.com/jyojay/MONU_Project_4/assets/132628129/78c5cdfa-4a8f-4fdc-903b-af21fa18212d) </br></br>
  
  **Result**</br></br>
  ![image](https://github.com/jyojay/MONU_Project_4/assets/132628129/2fe44593-3889-43f2-9a91-a5eec67d99a6) </br></br>

**SVM Model** </br></br>
 ![image](https://github.com/jyojay/MONU_Project_4/assets/132628129/9c21ea6a-c3f6-4269-9cf0-08e08d7595a4) </br></br>
 
  **Result**</br></br>
 ![image](https://github.com/jyojay/MONU_Project_4/assets/132628129/dd017a69-5b8c-4e29-be7b-25cff985d7d4) </br></br>

**SVM Model was observed to have a better accuracy, recall and precision than Naive Bayes CLassification model**

2) **RNN-LSTM Models**
  -	The data was split into Train and Test data at 3:1 ratio.
  -	Target used: class column values which were 0 or 1 depending on Fake or True news  
  -	Features used: text column values with the news text</br></br>

**LSTM Model** </br></br>
    ![image](https://github.com/jyojay/MONU_Project_4/assets/132628129/d078d439-a771-4cb5-838b-49099a22065a)</br></br>
    ![image](https://github.com/jyojay/MONU_Project_4/assets/132628129/323e2d58-1f92-433c-b1c9-0195a481e230) </br></br>
    ![image](https://github.com/jyojay/MONU_Project_4/assets/132628129/c26a8ad7-b4b2-4d2f-a6df-27393dd3581d) </br></br>

   **It was observed on training the model that the accuracy didn't improve beyond 0.52 in 10 epochs, increasing neurons or adding additioanl layers, varying other activation functions, so on a clean code run, only 2 epochs were run with one combination of the above factors to save on Google Colab GPU usage**</br></br>
   
   **Result**</br></br>
    ![image](https://github.com/jyojay/MONU_Project_4/assets/132628129/b7858eb5-b794-4ebb-9e68-fa91dde897c8) </br></br>

 **Bidirectional LSTM** </br></br>
    ![image](https://github.com/jyojay/MONU_Project_4/assets/132628129/c7bfa551-acb6-492c-aca8-adaede865371) </br></br>
    ![image](https://github.com/jyojay/MONU_Project_4/assets/132628129/1cc2eeed-7ef5-4088-b422-1e163870e458) </br></br>

  **Result**</br></br>
    ![image](https://github.com/jyojay/MONU_Project_4/assets/132628129/b97ef204-a4c4-4c00-bafa-d42883077a50) </br></br>
    ![image](https://github.com/jyojay/MONU_Project_4/assets/132628129/8ff31bb5-552e-4c61-9f94-91381b0a6351) </br></br>


  **It was observed on training the model with an embedding layer, 1 Bidirectional LSTM layer, a relu and an output sigmoid layer, that the accuracy reached 1 in 3 epochs itself when run for 5 epochs so on a clean code run, only 3 epochs were run**</br></br>
  
**BiLSTM had the best accuracy of 99.8%**

#### Limitations

- Data Diversity: The dataset originates predominantly from Reuters, limiting exposure to diverse journalistic styles. 
- Temporal Coverage: Data spans from March 2015 to February 2018, potentially missing contemporary linguistic nuances in news reporting. 
- Computational Constraints: Limited computational resources restricted extensive experimentation with hyperparameters and complex architectures.
- Continuous Learning: The current static models lack re-training capabilities, essential for adapting to new data. Future versions should integrate continuous learning to adjust to emerging data patterns and maintain performance over time.
- Prediction Specificity: Models are tailored to the specific dataset and may not perform optimally on varied news texts. Adaptation through fine-tuning or transfer learning techniques is suggested for applications beyond the initial dataset.

### Frontend

- Integration of Streamlit for dynamic data handling
- Interactive dashboard for user engagement and visualization
- Use of Tableau for data visualization components and comprehensive analysis

#### Streamlit Setup and Installation

**Introduction to Streamlit** 

- Streamlit is an open-source app framework in Python language.
- It helps us create web apps for data science and machine learning.
- Streamlit is an all-in-one tool that encompases web serving as well as data analysis
- It is compatible with major Python libraries such as scikit-learn, Keras, PyTorch, SymPy(latex), NumPy, pandas, Matplotlib etc.

**Installation:**

<< pip install streamlit >> in windows commandprompt / gitbash / anaconda

**Execution:**

<<   <Code Terminal> streamlit run <your_script>.py   >>
- Runs an interactive application on your local computer at http://localhost:8501.

 **Output**

![image](https://github.com/jyojay/MONU_Project_4/assets/132317668/16b0a984-157e-404f-b249-7c48355a8b13)

**Development Workflow :**

![2023_11_07_19_19_31_](https://github.com/jyojay/MONU_Project_4/assets/134185577/d4db5e5c-8ae1-485b-80eb-883cc6840e90)

**Tableau**

- Data visualisation and analysis involved further cleansed data into smaller filetypes for use in Tableau, such that irrelevant data was removed and columns were relabelled for ease of comprehension
- Designed each worksheet with a visualisation taken from the clean data sets and compiled into relevant dashboards
- Created dashboards for each analysis and model created and differentiated the data 
- Wrote a comprehensive and detailed data analysis per each visualisation and an intepretation of the results
- Compiled all dashboards into a story to be linked to the website incorporating the model
- Designed color theme, imagery and stylization.

### Usage

**The word analysis page created in Tableau using a variety of visual techniques including word cloud analysis, sentiment analysis and a comprehensive breakdown of the visulisations can be be found** [here](https://public.tableau.com/views/P4_16990786163050/Homepage?:language=en-GB&publish=yes&:display_count=n&:origin=viz_share_link)<br> <br>

<img width="1440" alt="Tableau data analysis image" src="https://github.com/jyojay/MONU_Project_4/blob/ac061a849b0c0064e2dec6e8a02635e56a8bef3a/ToRemove%20(Working%20files)/Taryn%20Fordyce/tableau%20page.png">

***
## Note on execution of code: 
`DataExploration.ipynb` code should be executed before running any other modules in order to generate a merged cleaned input file.

## Disclaimer

This work has been submitted by students. </br>
This is not to be considered an official document from the institution or a representation of the institution's views. </br>
The content herein is the result of academic coursework and has been created for educational purposes only. </br>
While the work is indicative of the student's understanding of the subject matter, it should be taken in the context of a learning exercise. </br>

