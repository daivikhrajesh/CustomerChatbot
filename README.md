# CustomerChatbot 🤖💬

CustomerChatbot is a conversational AI designed to simulate customer support interactions. This project implements chatbots for several customer service channels, including:
- [AppleSupport](https://twitter.com/AppleSupport) 🍏
- [AmazonHelp](https://twitter.com/AmazonHelp) 📦
- [Uber_Support](https://twitter.com/Uber_Support) 🚗
- [Delta](https://twitter.com/Delta) ✈️
- [SpotifyCares](https://twitter.com/SpotifyCares) 🎶

These chatbots are trained on publicly available conversations between customer support agents and users on Twitter. The goal is to provide users with an intelligent and interactive support experience.

---

## Features 🎯
- **Trainable Seq2Seq Chatbot** with encoder-decoder architecture.  
- Supports multiple **RNN cells** (LSTM/GRU).  
- Implements **Bahdanau** and **Luong** attention mechanisms.  
- Customizable embedding layers with **GloVe** support.  
- **Pre-trained customer service models** for Apple, Amazon, Uber, Delta, and Spotify.  
- **Interactive chat interface** for seamless user interaction.  
- **GPU and multi-GPU support** for efficient training and inference.  

---

## Sample Conversations 💬

### Example Conversation:
```
Bot: Hi, how can I help you?  
Me: I need help with my account.  
Bot: Sure! Can you tell me more about the issue?  
Me: My payment is not going through.  
Bot: Let me check that for you. Have you tried updating your payment method?  
```

---

## Installation 🛠️

### Install Dependencies:
First, clone the repository and install the required dependencies:
```bash
git clone https://github.com/yourusername/CustomerChatbot.git
cd CustomerChatbot
pip install -r requirements.txt
python3 -m spacy download en
```

---

## Model Architecture 🏗️
- **Encoder:** Bidirectional RNN (LSTM/GRU) with optional embedding layers.  
- **Attention:** Supports both **Bahdanau** and **Luong** mechanisms for better context understanding.  
- **Decoder:** RNN with attention for sequence prediction, making it suitable for dynamic responses. 

---

## Dataset 📊

The dataset used for training this chatbot can be found on [Kaggle](https://www.kaggle.com/thoughtvector/customer-support-on-twitter/data). This dataset was created by collecting publicly available conversations between customer support agents and users on Twitter. A big thanks to the author of the dataset!

---

## Pre-trained Models 🎯

To quickly get started, download and set up pre-trained customer service models by running the following commands:

```bash
wget https://www.dropbox.com/s/ibm49gx1gefpqju/pretrained-models.zip
unzip pretrained-models.zip
rm pretrained-models.zip
sudo chmod +x predict.py
```

You can now interact with any of the customer service chatbots by running the `predict.py` script. For example, to interact with the **Apple** customer support bot, use the following command:

```bash
./predict.py -cs apple
```

### Available Customer Service Chatbots:
- `apple`
- `amazon`
- `uber`
- `delta`
- `spotify`

---

## Training Your Own Model 🚀

You can also train the chatbot from scratch. First, download and format the Twitter dataset:

```bash
wget https://www.dropbox.com/s/nmnlcncn7jtb7i9/twcs.zip
unzip twcs.zip
mkdir data
mv twcs.csv data
rm twcs.zip
python3 datasets/twitter_customer_support/format.py  # This may take a couple of hours!
```

> ⚠️ **Warning**: The dataset formatting step may take several hours, depending on your machine.

Once the dataset is ready, you can begin training the chatbot by running:

```bash
sudo chmod +x train.py
python3 train.py
```

---

## License 📜
This project is licensed under the **MIT License**. See the [LICENSE](LICENSE) file for more information.
