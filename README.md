# CustomerChatbot
Chatbot is a computer program which conducts a conversation in a human-like way. This project implements chatbot which 
tries to answer users questions as customer support agent. Following customer support chatbots were implemented: 
[AppleSupport](https://twitter.com/AppleSupport), [AmazonHelp](https://twitter.com/AmazonHelp), 
[Uber_Support](https://twitter.com/Uber_Support), [Delta](https://twitter.com/Delta) and 
[SpotifyCares](https://twitter.com/SpotifyCares). Chatbots were trained on publicly available conversations between 
customer supports and users on Twitter.

## Features
- Trainable Seq2Seq chatbot with encoder-decoder architecture.  
- Supports multiple RNN cells (LSTM/GRU).  
- Implements Bahdanau and Luong attention mechanisms.  
- Customizable embedding layers with GloVe support.  
- Pre-trained customer service models for Apple, Amazon, Uber, Delta, and Spotify.  
- Interactive chat interface.  
- GPU and multi-GPU support for training and inference.  

---

## Sample conversations
### Example Conversation
```
Bot: Hi, how can I help you?  
Me: I need help with my account.  
Bot: Sure! Can you tell me more about the issue?  
Me: My payment is not going through.  
Bot: Let me check that for you. Have you tried updating your payment method?  
```

### Install Dependencies
```bash
pip install -r requirements.txt
```

## Model Architecture
- **Encoder:** Bidirectional RNN (LSTM/GRU) with optional embedding layers.  
- **Attention:** Supports both Bahdanau and Luong mechanisms.  
- **Decoder:** RNN with attention for sequence prediction. 

# Dataset 
Dataset used for training chatbot can be found 
[here](https://www.kaggle.com/thoughtvector/customer-support-on-twitter/data). This dataset was created by collecting 
publicly available conversations between customer supports and users on Twitter. Many thanks to the author of dataset!

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
