# Resume Parsing Using BERT based Transfer Learning

This Resume Parser uses BERT-base-cased Transfer Learning for Named Entity Recognition (NER). 
It can extract key resume information accurately with advanced NLP techniques.
Transfer learning with models like BERT has achieved state-of-the-art results in various NLP tasks, including NER. 
This approach can lead to more accurate and reliable parsing of resume information.
Traditional machine learning-based NER models require a large amount of labeled data for training. 
Transfer learning, on the other hand, benefits from the pre-training on extensive corpora, requiring less labeled data for fine-tuning.

# Data Source
Resumes in pdf format from www.livecareer.com available on open platform Kaggle 
Link : https://www.kaggle.com/datasets/snehaanbhawal/resume-dataset
Total Resumes - 2400+
Used Resumes- 462 (Domain- IT, HR, Engineer, Consultant)

# PDF To Text Conversion
Resumes are converted from pdf to text format using PYPDF2 library.

# Manual Annotations
Manual Annotations are done on 180 resumes using NER text annotator (https://tecoholic.github.io/ner-annotator/) 
Files are obtained in json format after annotations.
Entities tagged in a resume:
1. Job Title - This entity represents the the type of job a candidate wants
2. Experience - Previous experience of the candidate and timeline
3. Skill - Important skills a candidate possess
4. Education- Educational details (Degree and College)

# Evaluation Metrics
Precision, Recall and F1 Score with main weightage to F1 score.

# Modelling

1. Training- A BERT-base model  is utilised for the Named Entity Recognition (NER) task in the modeling process.
The model is trained on 144 resumes using spaCy library version 3 and validated on 36.
The modeling process involves two parts.
The first part requires converting the annotated json data into spaCy format to facilitate training.
Second is to set config file for training which is already present on github.
After that we can train our pipeline with just one line of code.
"python -m spacy train config.cfg --paths.train ./train.spacy --paths.dev ./dev.spacy"

2. Validation- The model is validated on 36 resumes.
3. Testing - Testing is done on a sample resume for NE predictions.

