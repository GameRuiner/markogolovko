---
title: 'Supervised vs Unsupervised Machine Learning'
description: "Supervised learning requires labeled data. However, in practice, unlabeled data is much more common. But what about popularity of supervised vs. unsupervised machine learning algorithms? Let's dive into that topic 🤖"
discover:
  description: "Supervised learning requires labeled data. However, in practice, unlabeled data is much more common. But what about popularity of supervised vs. unsupervised machine learning algorithms? Let's dive into that topic"
date: 2024-09-25
---

Supervised learning requires labeled data. However, in practice, unlabeled data is much more common. But what about popularity of supervised vs. unsupervised machine learning algorithms? Let's dive into that topic 🤖


## How do we gather labeled data?

To be on the same page, let's define labeled data and unlabeled data. 
Examples of unlabeled data:
 - images
 - audio files
 - text

Unlabeled data consists of raw samples. When we annotate this data, we create labeled data:
- a photo labeled as a "Labrador retriever"
- a song with its lyrics transcribed
- a product review with an assigned rating

Adding labels to data makes it more useful for machine learning, but it comes at a cost. Annotating data usually requires manual human effort. This process can be accelerated by using machine learning models to automatically annotate data when they are highly confident. However, the initial dataset for training these models still needs to be annotated manually.

## Which algorithms are more common?

As mentioned in the previous section, it's easier and cheaper to obtain unlabeled data. With powerful unsupervised machine learning algorithms, we have much more data to train them compared to supervised algorithms. Let's explore the different learning methods used in machine learning.

### Transformers

Today, in 2024, the first model architecture that comes to mind is the transformer. With constant releases of new products and updates to existing ones, the transformer serves as a good example to understand what is happening in the world of AI. 
A detailed explanation of how the model works is beyond the scope of this article, so today we'll focus on the type of data used to train the model. Transformers can be applied in both supervised and unsupervised learning, depending on their usage. 

#### Supervised learning

Referring to, the "Attention Is All You Need" paper, the original transformer model was trained on datasets consisting of sentence pairs. The model's task was machine translation, which means it used labeled data, making it an example of supervised learning.

#### Semi-supervised learning

In model results section of the paper, the authors also shared the transformer's performance on English Constituency Parsing. 
Let's clarify what English Constituency Parsing entails. This task, also related to NLP, involves breaking a sentence into its hierarchical components.
Example:

```
S
├── NP (The cat)
└── VP (sat on the mat)
    ├── V (sat)
    └── PP (on the mat)
        ├── P (on)
        └── NP (the mat)
```

In this example,  the sentence **“The cat sat on the mat”** (S), was divided into **"The cat"** (a noun phrase  NP) and **"sat on the mat"** (a verb phrase VP).  The VP was further broken down into a verb (V), a prepositional phrase (PP), a preposition (P) and another noun phrase (NP).
Here, we are again dealing with supervised learning. The training was performed on Wall Street Journal portion of Penn Treebank corpus. Later, we learn that the model was also trained in a semi-supervised setting using BerkleyParser corpus,  which increased the number of training sentences from 40K to 17M.

#### Self-supervised learning

Let's explore another approach: self-supervised learning, using the transformer model as a reference again. Specifically, we will look at a generative chatbot model based on large language models (LLMs). I'll briefly explain self-supervised aspect of training the GPT model. 
The Generative Pre-trained Transformer (GPT) model is usually fine-tuned for specific tasks using supervised learning, which we discussed earlier. However, the focus in this section is a pre-training phase, where large datasets of unlabeled text are used. One approach for self-supervised "pre-training" is teaching the model to recreate text by predicting one word at a time, based on previous tokens (encoded words). Once the model is trained, it uses the input text as context for predictions and continues generating new tokens until it reaches a stop token.


### Autoencoders

To cover unsupervised learning, let's take autoencoders as an example. An autoencoder is a neural network designed to compress (encode) input data to its essential features and then reconstruct (decode) the original input from this compressed representation. Although autoencoders include both an encoder and a decoder, not all encoder-decoder models are autoencoders. In sequence-to-sequence (seq2seq) tasks, for example, we encounter supervised learning, as we expect the  output to be different from the input.

## Conclusion

After a quick glance at a few model architectures, we can observe that modern machine learning algorithms employ different approaches, each with its own advantages and disadvantages. The choice of approach usually depends on the  model task the model is designed to solve. We also see models trained initially with supervised techniques can be enhanced by incorporating unlabeled data.