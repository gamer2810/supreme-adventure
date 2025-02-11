---
title: LLM Study Notes
date: February 11, 2025 10:49 AM
categories:
  - ai
tags:
  - llm
  - study
  - notes
  - ""
description: Document what I learnt from a deep dive video on LLM
toc: true
comments: true
math: false
---
# Video

<div style="left: 0; width: 100%; position:relative; aspect-ratio: 3/1;">
<iframe width="560" height="315" src="https://www.youtube.com/embed/7xTGNNLPyMI?si=UYt9JPHJjFvr5WHp" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>

# Basic concepts

## Gathering data

**Goal:** Gather clean, useful text data from arbitrary sources (website, books,...).

**Procedure**: Get all the possible text and concatenate them together to create an enormous text.

**Reference**
[HuggingFace's FineWeb](https://huggingface.co/spaces/HuggingFaceFW/blogpost-fineweb-v1) 

## Tokenization

**Goal:** Reduce the size of the text gathered while preserving the *meaning* behind it.

**Procedure:**: Using the **Byte Pair Encoding** algorithm, recognize repeating patterns and encodes them as a single token.

E.g.:

![tokenizer-example](/assets/img/uploads/tokenizer-example.png "Tokenizer Example")

**Reference**
[BPE Algorithm](https://en.wikipedia.org/wiki/Byte_pair_encoding)
[Tiktokenizer](https://tiktokenizer.vercel.app/)

## Training the language model

**Goal:** Extract the knowledge behind the text by training the neural network on the tokenized text and tune the parameters. The model trained here will be called the **BASE** model.

**Procedure:** Using machine learning, train the neural networks so that it can statistically predict what token comes next after a sequence (window) of tokens.

E.g.: 
Input text = "I view news" => Token window = "333 255"
Prediction = "992" = "Article" - 3%

## Inference

**Goal:** Generating a sequence of tokens from the trained model (generating an answer).

**Procedure:** Infer a starting token then merge that token with the input to generate the next token so that it builds subsequent tokens based on generated ones.

E.g.:
![interence-example](/assets/img/uploads/inference-example.png "Inference example")

## Post-training tuning

**Goal:** Turn the **BASE** model into a more helpful assistant.

**Procedure:** 
Multiple methods:

* Embed some starting tokens when model starts up so that it is more likely to produce related information.

E.g.: Information about the model itself so that when asked it has an idea.

* Using conversations to further tune the model's answer (i.e. let the model takes on the personality). The conversation can either be syntactic (machine-generated) or crafted by human experts.

E.g.: 

![conversation-example](/assets/img/uploads/conversation-example.png "Conversation Example")

[Video's timestamp on this matter](https://youtu.be/7xTGNNLPyMI?si=NwPn4o6tQcL9Ho28&t=3751)

* Use special tokens to allow models to use external tools like searching...

## Video's Note

All credits go to the youtube video's owner at [Youtube Link](https://www.youtube.com/watch?v=7xTGNNLPyMI)

[Drive Link](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbFhWTXhkTm50dWpLNnhnRDBnQllMaXVMZlg2Z3xBQ3Jtc0ttVndnT1V1UnRRWW1yZjB0UXFNR09WMDc0WXZKWVJFOU5TWDdVSlp0YnBrTHFJU0lRMzN2eEVncTRxbVpoYVBkTlpOTTVxUC1kWThDTEFyRDJiUTZ1djFVZmZ3OVdOZjJoSGdNLXoybk15S05GRlJLQQ&q=https%3A%2F%2Fdrive.google.com%2Ffile%2Fd%2F1EZh5hNDzxMMy05uLhVryk061QYQGTxiN%2Fview%3Fusp%3Dsharing&v=7xTGNNLPyMI)

[](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbFhWTXhkTm50dWpLNnhnRDBnQllMaXVMZlg2Z3xBQ3Jtc0ttVndnT1V1UnRRWW1yZjB0UXFNR09WMDc0WXZKWVJFOU5TWDdVSlp0YnBrTHFJU0lRMzN2eEVncTRxbVpoYVBkTlpOTTVxUC1kWThDTEFyRDJiUTZ1djFVZmZ3OVdOZjJoSGdNLXoybk15S05GRlJLQQ&q=https%3A%2F%2Fdrive.google.com%2Ffile%2Fd%2F1EZh5hNDzxMMy05uLhVryk061QYQGTxiN%2Fview%3Fusp%3Dsharing&v=7xTGNNLPyMI)

![llm-notes](/assets/img/uploads/llm-excalidraw.svg "LLM Notes")
