## Multilabel-Toxicity-Detection-App

This is a Streamlit app that allows you to analyze the toxicity of text using different pre-trained models. The app supports multi-label toxicity detection and sentiment analysis.

## Installation

To run this application, make sure you have the following dependencies installed:
```
streamlit
pandas
transformers
You can install the dependencies using the following command:
```
pip install streamlit pandas transformers
```
## Importing Dependencies

The code begins by importing the necessary dependencies: streamlit, pandas, and transformers. These libraries will be used for building the Streamlit app, data manipulation, and loading pre-trained models.

## Loading Pre-trained Models
The code defines two functions: load_finetune_model() and load_model(). These functions are responsible for loading the pre-trained models used for toxicity detection and sentiment analysis.

load_finetune_model(model_name): This function takes the name of a pre-trained model as input and returns the tokenizer and model objects.
load_model(model_name): This function also takes the name of a pre-trained model as input and returns a sentiment analysis pipeline object. It uses the pipeline class from the transformers library to create a pipeline for sentiment analysis.
## Streamlit App Setup
The code sets up the Streamlit app by displaying the title and a description of the multi-label toxicity detection app.

## User Input
The code prompts the user to enter a text for toxicity analysis using a text input field. The default text is provided as an example.

## Model Selection
The code defines a dictionary model_options that contains different pre-trained models for toxicity detection and sentiment analysis. Each model is associated with a description and, if applicable, a list of labels.

The user is presented with a dropdown menu to select a fine-tuned model from the available options.

## Model Information
The code displays the description of the selected model below the model selection dropdown. The description provides information about the capabilities and training data of the model.

## Initial Table
The code creates an initial table with prepopulated data for demonstration purposes. The table contains columns for the input text (or a portion of it), the highest toxicity class, and its corresponding probability. The initial table is stored in a DataFrame initial_table_df.

## Analyzing Toxicity
When the user clicks the "Analyze" button, the code checks if a text is entered. If no text is provided, a message is displayed requesting the user to enter a text.

If a text is entered, the code proceeds to analyze the toxicity using the selected model. If the model is "Olivernyu/finetuned_bert_base_uncased", the code uses the load_model() function to load the model and perform toxicity analysis. It retrieves the top two toxicity predictions and their probabilities for the input text. The results are then added to the table data.

If the selected model is not "Olivernyu/finetuned_bert_base_uncased", the code uses the load_model() function to load the model and perform sentiment analysis. It retrieves the sentiment label and confidence score for the input text.

The updated table with the toxicity or sentiment analysis results is displayed using the st.table() function.

## Displaying Results
If the "Analyze" button is not clicked, the code displays a message instructing the user to enter a text and click "Analyze" to perform toxicity analysis.

## Usage

To use this code, follow these steps:

Install the required dependencies: streamlit, pandas, and transformers.

Run the code using the command streamlit run app.py.

The Streamlit app will be launched in your browser.

Enter a text in the provided text input field.

Select a fine-tuned model from the dropdown menu.

Click the "Analyze" button to perform toxicity or sentiment analysis on the entered text.

The results will be displayed in the table below.
