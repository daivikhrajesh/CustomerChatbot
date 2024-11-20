# About
Chatbot is a computer program which conducts a conversation in a human-like way. This project implements chatbot which 
tries to answer users questions as customer support agent. Following customer support chatbots were implemented: 
[AppleSupport](https://twitter.com/AppleSupport), [AmazonHelp](https://twitter.com/AmazonHelp), 
[Uber_Support](https://twitter.com/Uber_Support), [Delta](https://twitter.com/Delta) and 
[SpotifyCares](https://twitter.com/SpotifyCares). Chatbots were trained on publicly available conversations between 
customer supports and users on Twitter.

Chatbot is implemented as sequence to sequence deep learning model with attention. Project is mostly based on 
[Bahdanau et al. 2014](https://arxiv.org/abs/1409.0473), [Luong et al. 2015.](https://arxiv.org/abs/1508.04025) 
and [Vinyals et al., 2015.](https://arxiv.org/abs/1506.05869).

# Sample conversations
Sample conversations with customer support chatbots. Conversations with chatbots are not ideal but show promising 
results. Chatbot answers are in grey bubbles.

# Dataset 
Dataset used for training chatbot can be found 
[here](https://www.kaggle.com/thoughtvector/customer-support-on-twitter/data). This dataset was created by collecting 
publicly available conversations between customer supports and users on Twitter. Many thanks to the author of dataset!

# Try it out!
You can try out chatbot by using pre-trained models or by training your own chatbot.

## Installation 
```bash
pip3 install -r requirements.txt
python3 -m spacy download en
```

## Pre-trained models
Run following commands in root of this repository to download pre-trained customer service chatbots.

```bash
wget https://www.dropbox.com/s/ibm49gx1gefpqju/pretrained-models.zip
unzip pretrained-models.zip
rm pretrained-models.zip
sudo chmod +x predict.py
```

Now you can "talk" with customer service chatbots using `predict.py` script. Following customer service chatbots are 
available: `apple,amazon,uber,delta,spotify`. Following example shows how to run `apple` customer service chatbot:
```bash
./predict.py -cs apple
```

## Train
You can choose to train chatbot yourself. Run following commands to download and format Twitter dataset used in this 
project:
```bash
wget https://www.dropbox.com/s/nmnlcncn7jtb7i9/twcs.zip
unzip twcs.zip
mkdir data
mv twcs.csv data
rm twcs.zip
python3 datasets/twitter_customer_support/format.py # this runs for couple of hours
sudo chmod +x train.py
```
> WARNING this block will run for couple of hours!

Now you can use `train.py` to train chatbot.
