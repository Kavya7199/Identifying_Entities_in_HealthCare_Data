# Natural Language Processing (Syntactic Procesing)

Let’s consider a hypothetical example of a health tech company called ‘BeHealthy’. Suppose ‘BeHealthy’ aims to connect the medical communities with millions of patients across the country. 

‘BeHealthy’ has a web platform that allows doctors to list their services and manage patient interactions and provides services for patients such as booking interactions with doctors and ordering medicines online. Here, doctors can easily organise appointments, track past medical records and provide e-prescriptions.

So, companies like ‘BeHealthy’ are providing medical services, prescriptions and online consultations and generating huge data day by day.

Let’s take a look at the following snippet of medical data that may be generated when a doctor is writing notes to his/her patient or as a review of a therapy that he or she has done.

“The patient was a 62-year-old man with squamous cell lung cancer, which was first successfully treated by a combination of radiation therapy and chemotherapy.”

As you can see in this text, a person with a non-medical background cannot understand the various medical terms. We have taken a simple sentence from a medical data set to understand the problem and where you can understand the terms ‘cancer’ and ‘chemotherapy’. 

Suppose you have been given such a data set in which a lot of text is written related to the medical domain. As you can see in the dataset, there are a lot of diseases that can be mentioned in the entire dataset and their related treatments are also mentioned implicitly in the text, which you saw in the aforementioned example that the disease mentioned is cancer and its treatment can be identified as chemotherapy using the sentence.

But, note that it is not explicitly mentioned in the dataset about the diseases and their treatment, but somehow, you can build an algorithm to map the diseases and their respective treatment.

Suppose you have been asked to determine the disease name and its probable treatment from the dataset and list it out in the form of a table or a dictionary like this.

After discussing the problem given above, you need to build a custom NER to get the list of diseases and their treatment from the dataset.



## Identifying_Entities_in_HealthCare_Data

There are eight major tasks that you need to perform to complete the assignment. They are as follows:

- Data preprocessing
- Concept identification
- Defining the features for CRF
- Getting the features words and sentences
- Defining input and target variables
- Building the model
- Evaluating the model
- Identifying the diseases and predicted treatment using a custom NER
- Let's break down the steps into subtasks to understand this better.


## Data preprocessing: 
As you are already aware that the dataset is in the token format instead of sentences, you need to construct the sentences from the words. There are blank lines after the completion of each sentence or a set of labels in label files ('train_label' and 'test_label') and you need to build a logic to arrange them into sentences or a sequence of labels in the case of label files. You can refer to the following two images to understand this better.
A similar step is to be performed for the 'train_label' and 'test_label' datasets.
 

You need to do the following three tasks after processing and modifying the datasets:

- Construct proper sentences from individual words and print five sentences along with their labels.
- Print the correct count of the number of sentences in the processed train and test dataset.
- Correctly count the number of lines of labels in the processed train and test dataset.
 

## Concept identification: 
After preprocessing, we will first explore what are the various concepts present in the dataset. For this task, we will use PoS tagging. It is good to identify all the words from the corpus that have a tag of NOUN or PROPN (nouns) and prepare a dictionary of their counts. We will then output the top 25 most frequently discussed concepts in the entire corpus.

An important point to note here is that we are using both test and train sentences for concept identification. This is an exploratory analysis on the complete data. In this step, you need to perform the following two tasks by considering the train and the test dataset as a single unit of data:

- Use a toolkit like spaCy to extract those tokens that have NOUN or PROPN as their PoS tag and find their frequency from the entire dataset that comprises both the train and the test datasets.
- Print the top 25 most common tokens with NOUN or PROPN PoS tags for the entire dataset that comprises both the train and the test datasets.

## Defining the features for CRF: 
Here, you need to perform the following three steps:

- Define the features with the PoS tag as one of the features.
- While defining the features in which you have used the PoS tags, you also need to consider the preceding word of the current word. The use of the information of the preceding word makes the CRF model more accurate and exhaustive.
- Mark the beginning and the end words of a sentence correctly in the form of features.
 

## Getting the features and the labels of sentences: 
In this step, you need to perform the following two tasks:

- Write the code to get the features' value of a sentence after defining the features in the previous step.
- Write the code to get a list of labels of a given preprocessed label line that you have created earlier.
 

## Defining input and target variables: 
In this step, you need to perform the following two tasks:

- Extract the features' values for each sentence as an input variable for the CRF model in the test and the train dataset.
- Extract the labels as the target variable for the test and the train dataset.
 

## Building the model: 
You need to build the CRF model for a custom NER application using the features and the target variables.

## Evaluation: 
Evaluate the model using the following two steps:

- Predict the labels of each of the tokens in each sentence of the test dataset that has been preprocessed earlier.
- Calculate the f1 score using the actual and the predicted labels of the test dataset.
 

## Identifying the diseases and treatment using a custom NER: 
Create the code or logic to get all the predicted treatments (T) labels corresponding to each disease (D) label in the test dataset. You can refer to the following image to get an idea on how to create a dictionary where diseases are working as keys and treatments are working as values.
 

### Predict the treatment for the disease named 'hereditary retinoblastoma'.

