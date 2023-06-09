## This is the code repository for my project - "Adversarial attacks on fake news detection"
### Course: COMS 6156 (Columbia University)

## Project Overview

Machine Learning (ML) and Natural Language Processing (NLP) techniques are gaining popularity in fake news detection as it is challenging and time-consuming for humans to go through a large number of news articles manually. As part of the project, I have implemented Machine learning (ML) algorithms like LSTM Neural Networks, XGBoost, and Support Vector Machines (with RBF Kernel),  along with employing Natural Language Processing techniques (NLP) such as Word2Vec, RoBERTa for detecting fake news on the ISOT dataset. Furthermore, due to the growing popularity of Large Language Models (LLMs) such as ChatGPT for generating fake data, I tried to inject adversarial attacks by using GPT-J Language model to generate synthetic fake news stories. I then evaluated the performance of the above ML/NLP models when they were tested on fake news generated by these LLMs.

## Dataset

I have used the ISOT Fake News dataset, which is made publicly available for research by the University of Victoria . The ISOT Fake News dataset is a compilation of several thousands(~45,000) of fake news and truthful articles.
Datset link:- https://onlineacademiccommunity.uvic.ca/isot/2022/11/27/fake-news-detection-datasets/
Credits for the dataset: 
1. Ahmed H, Traore I, Saad S. “Detecting opinion spams and fake news using text
classification”, Journal of Security and Privacy, Volume 1, Issue 1, Wiley,
January/February 2018.
2. Ahmed H, Traore I, Saad S. (2017) “Detection of Online Fake News Using N-Gram
Analysis and Machine Learning Techniques. In: Traore I., Woungang I., Awad A. (eds)
Intelligent, Secure, and Dependable Systems in Distributed and Cloud Environments.
ISDDC 2017. Lecture Notes in Computer Science, vol 10618. Springer, Cham (pp. 127-
138).

The data is also present under the data folder in this repository as two separate csv files - real.csv and fake.csv.
Further, the sythetic fake data generated using GPT-J is present under the syn_fake_date folder.

## Installing necessary libraries and packages

1) Install all the packages listed in requirements.txt
    1) You can use the pip command to install the packages.
    2) pip install -r requirements.txt
   3) Use Python version 3.9.12 for running the code.
   
2) The conda environment is also saved in the environment.yaml file.
3) Use the command to recreate the environment
   1) conda env create --file environment.yaml
   
4) If running the tensorflow code on Apple silicon M1, then you
would have to install miniconda / miniforge to run the LSTM - NN code
    1) Use the below instructions to ensure Tensorflow is properly
       installed in your system; otherwise it will throw an error.
       2) Install tensorflow verion 2.12.0
   2) https://developer.apple.com/metal/tensorflow-plugin/
   
## Steps to run the code

1) Run the individual pipelines for the three ML/DL models (as commented in the main file) to visualize the results of classification. 
   1) You can comment out the parts you would not like to run in the main file for this.
2) The code for hyper-parameter tuning is given separately, as running the
code with hyper-parameter tuning will take several days.
   1) Refer the hyper-parameter 'tuning' scripts if you want to experiment with hyperparameters
3) The code for generating synthetic fake news is also given in the
generate_fake_syn_data.py file.  This will also take time to generate
samples.
4) You can also test the nlp + ml/dl model output to detect synthetically
generated fake news by running the 'test_syn_fake_data.py' file.
5) Finally For Demo purposes - you can test all the classifiers on sample real news and 
synthetically generated fake news using the 'test_demo.py' file.
   1) The trained models are already saved and loaded for this demo purpose.
   2) You can see the input news sample in the sample_demo folder
   3) Demo Can be given from Command line prompt through terminal
   4) Example (For True - Real data ):-   python test_demo.py sample_true1.csv
   5) Example (For Fake - synthetic data ):-   python test_demo.py sample_fake_syn_1.csv
6) You can also run the main file directly, to get the accuracy
and other performance metrics for all the pipelines with different
NLP and ML/DL models.
7) Recommended to Test the scripts using data from ISOT, or generated synthetic fake data
in the syn_fake_data folder for accurate results from the trained models.
8) For future work - Feel free to combine and experiment any of the NLP models with any
of the ML or DL models for re-use. Also feel free to Generate additional news samples of synthetic news and test
performance of the models.

## Demo Link
The Demo slides and Demo can be accessed in the following link - https://drive.google.com/drive/u/0/folders/19ILQEnxJ7mXJuGCoUpGY7MJEb2aXLeMk

