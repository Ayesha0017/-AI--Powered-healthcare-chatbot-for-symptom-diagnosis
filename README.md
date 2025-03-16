# AI-Powered Healthcare Chatbot
This project implements an AI-powered healthcare chatbot that helps users with symptom analysis and preliminary diagnosis. The chatbot is built using Natural Language Processing (NLP) and Machine Learning (ML) techniques to provide intelligent responses based on user inputs.

## Dataset
The dataset used is the disease-sympotms dataset from kaggle https://www.kaggle.com/datasets/dhivyeshrk/diseases-and-symptoms-dataset
It consists of the following columns  
- diseases- which is our target column
- anxiety and nervousness
- depression
- shortness of breath
- depressive or psychotic symptoms
- sharp chest pain
- dizziness
- insomnia
- abnormal involuntary movements
- chest tightness	etc..

  # Text Pre Processing
  Normalize column names  
  Handle missing values- Replace missing values with 0 (assuming 0 means absence of symptom)  
  Ensure all symptom columns are numeric, Exclude 'diseases'  
  Convert symptoms to binary (1 if present, 0 if not)    

  Extract Features and Labels

  ## Training
  Encode target labels  
  ### Train-Test Split
  train-test size is 80-20    
  Train the model using RandomForests

## How It Works
### User Input:
The user provides symptoms as a comma-separated list.  
Example: "fever, headache, fatigue"  
### Symptom Processing:
The input is normalized (converted to lowercase and stripped of extra spaces).  
A binary symptom array is created (1 if present, 0 otherwise).  
### Model Prediction:
The machine learning model processes the symptom array.  
It predicts the most likely disease based on learned patterns.  
### Chatbot Response:
The chatbot provides a possible disease based on the prediction.  
It advises users to consult a doctor for professional guidance.  
### Code Explanation
🔹 predict_disease(symptom_list)  
Takes a list of symptoms as input.  
Converts symptoms into a binary feature array.  
Uses the ML model to predict the most likely disease.  
Returns the predicted disease name.  
🔹 chatbot()  
Greets the user and explains how to enter symptoms.  
Waits for user input (symptoms).  
Calls predict_disease() to process the symptoms.  
Prints the predicted disease and a medical advisory message.  
Allows users to exit anytime using "exit", "quit", or "stop".  
