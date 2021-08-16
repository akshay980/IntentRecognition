
# Deriving Intents from User's Queries using BERT

Intent  Classification,  also  known  as  Intent  Recognition,  is the process of taking a spoken or written text and categorizing it  based  on  the  user’s  goals. The  goal  of  ID  is  to  figure  out  what  a  sentence’s  aim  is, which  is  a  common  categorization  task. The  project  will  go  through  the  following phases:  collecting  and exploring  the  data,  pre-processing  the gathered  data,  fine-tuning  the  BERT  model  according  to  the task,  training  the  model,  and  evaluating  the  model  to  get  the desired output. This work, an  Intent  Recognition of  user’s  queries  model is based  on  pre-trained  BERT  model. Also, AWS Lex service is used to make chatbot and used these queries to get the respected intents.
## Data

The data contains various user queries categorized into seven intents.
The files train, test and validation sets can be found in Dataset folder. It has two columns text and intent. The dataset used here is SNIPS dataset, its paper can be found in (https://arxiv.org/abs/1805.10190). 
The seven intents are as follows:

  * SearchCreativeWork
  * GetWeather
  * BookRestaurant
  * PlayMusic
  * AddToPlaylist
  * RateBook
  * SearchScreeningEvent
## Pre-requisites

Download the pre-trained BERT model and unzip it.
```bash
https://storage.googleapis.com/bert_models/2018_10_18/uncased_L-12_H-768_A-12.zip
```

```bash
!unzip uncased_L-12_H-768_A-12.zip
```

This will unzip a checkpoint, config, and vocabulary, along with other files.
## Pre-processing

First convert the raw texts into vectors that can be fed into the model. For this follow these 3 steps:
* Tokenize the text
* Convert the sequence of tokens into numbers
* Convert the sequence of tokens into numbers

This can be done using BERT tokenizer:
```bash
tokenizer = FullTokenizer(
  vocab_file=os.path.join(bert_ckpt_dir, "vocab.txt")
)
```
## Fine-tuning

We will fine-tuning the pre-trained BERT model using the inputs (text and intent).
For this, load the model and attach a couple of layers (Keras) on it and add the activation function.
Now the BERT is ready to recognize intents!
  ## Training

* Batch size: 16
* Learning rate (Adam): 1e-5
* Number of epochs: 5
## How to run

* Open the ipynb file.
* Check for GPU.
* Install the required libraries.
* Download and load the BERT pre-trained model.
* Take data from your drive or local machine.
* Add custom sentences and get the intents.
* Use AWS account to create a chatbot using Amazon Lex and add intents and queries.
* Build it and test the chatbot. Ready to go!  
## Evaluation

* Train acc 0.9915119
* Test acc 0.9771429

The model is evaluated my calculating precision, recall and f1-score. The results are pretty impressive of about 97%.
This model is able to detect intent from custom sentences also with near to 98% accuracy.
## Results

Just by giving custom queries, the model will give intents.
![output](https://user-images.githubusercontent.com/33752064/129611524-870b6d64-6b19-422a-b3a8-9c2301c1fa24.PNG)

This shows quite good results.
![train-test accuracy](https://user-images.githubusercontent.com/33752064/129611680-54f32087-8fb1-4dc9-95c6-eb410a18ac81.PNG)

Integrated this intents with AWS Lex to create a chatbot.
![bot](https://user-images.githubusercontent.com/33752064/129611832-df7ad760-8987-4845-9952-2d9a08b06ecf.PNG)

## Badges

Add badges from somewhere like: [shields.io](https://shields.io/)

[![MIT License](https://img.shields.io/apm/l/atomic-design-ui.svg?)](https://github.com/tterb/atomic-design-ui/blob/master/LICENSEs)
[![GPLv3 License](https://img.shields.io/badge/License-GPL%20v3-yellow.svg)](https://opensource.org/licenses/)
[![AGPL License](https://img.shields.io/badge/license-AGPL-blue.svg)](http://www.gnu.org/licenses/agpl-3.0)

  
## Acknowledgements

 - [Awesome Readme Templates](https://awesomeopensource.com/project/elangosundar/awesome-README-templates)
 - [Awesome README](https://github.com/matiassingers/awesome-readme)
 - [How to write a Good readme](https://bulldogjob.com/news/449-how-to-write-a-good-readme-for-your-github-project)
 - [Fine-tune BERT](https://mccormickml.com/2019/07/22/BERT-fine-tuning/)
 - [Intent Identification with BERT](https://www.kaggle.com/joydeb28/intent-identification-with-bert)
 - [Multi-label Text Classification using BERT – The Mighty Transformer](https://medium.com/@nutanbhogendrasharma/step-by-step-intent-recognition-with-bert-1473202b8597)
 
  
