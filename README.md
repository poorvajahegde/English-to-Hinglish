# Hinglish Translation with Fine-tuned Language Model

This document provides an overview of the code used for fine-tuning a language model for Hinglish translation. The model is fine-tuned on a custom dataset and then used to generate Hinglish translations of English sentences.

# Table of Contents
1.Code Overview  
2.Key Components 
3.Future Work

# Code Overview
The code can be divided into several sections:
1.Model and Tokenizer Loading: The code begins by specifying the name of the pre-trained model (modelname = "ai-forever/mGPT"). This model is then loaded along with its tokenizer.

2.Fine-tuning Preparation: The custom dataset for fine-tuning is loaded from a text file (custom_dataset.txt). The dataset is split into pairs of English sentences and their corresponding Hinglish translations.

3.Model Fine-tuning: The model is fine-tuned on the custom dataset using the SFTTrainer class from Hugging Face's Transformers library. The training arguments specify details such as the learning rate, batch size, and number of training epochs.

4.Post-training Model Loading: After training, the fine-tuned model weights are saved and then loaded back into a new model instance.

5.Translation Function: A function (translate_to_hinglish) is defined to use the fine-tuned model to generate Hinglish translations of English sentences.

6.Translation Examples: Finally, the translate_to_hinglish function is used to translate some example sentences and print the results.

# Key Components
mGPT Model: This is the pre-trained model that serves as the starting point for fine-tuning. It's a variant of the GPT model, which is a transformer-based language model.

SFTTrainer: This is a class from Hugging Face's Transformers library that's used for fine-tuning the model. It handles tasks like gradient accumulation, learning rate scheduling, and saving/loading model checkpoints.

# Running on colab
Install the required libraries.
Then set the path for custom dataset.
Here for dataset preparation I used bard, but if we write our own sentences, it will yield better and accurate results.
I used mGPT LLM text generation model. Better use GPT 3.5, BLOOM or LLama2. As I had memory issues couldn't use those.
Then set the parameters and train it.
Use the trained weights for queries.
Calculate the BLEU score on test dataset.
Improve the model i.e. hyperparameter tuning.
