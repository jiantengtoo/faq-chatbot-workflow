# FAQ Chatbot Workfow

1. Background
2. Overview
3. Requirement Specification
4. Data Pre-processing
5. Intent &amp; Response
6. Testing &amp; Improving

## Background

Frequently asked questions (FAQs) provide a list of question and answer pairs on a particular topic. The purpose of FAQ is to provide information on frequent question. The purpose of a FAQ chatbot is to streamline the process of user finding the information they want. So instead of finding the answers from a long list, user can query the FAQ chatbot to get an immediate answer.

## Overview


The process of building a FAQ chatbot involves 4 steps.

## Requirement Specification

- Know your users
  - Who are they?
  - In what situation will they be using?
  - What words or phrases they will be using?
- Persona of chatbot
  - Does the chatbot need to make small talks?
  - The tone of the chatbot need to be more casual or professional?
- Scaling (This can be helpful when deploying the chatbot)
  - How many people will be using?
  - How frequently will they be using?

These questions only serve as a guide to better understand the requirements. Knowing the requirements are essential to designing of the chatbot.

## Data Pre-processing

There can be question &amp; answer pairs in the FAQ that do not fit the chatbot. Some examples are:

- Long answers can look daunting in a small chat window. Summarizing of the text might help.
- Tables &amp; diagrams. Can be display in image.
- Multiple parts answers. Can be split into smaller question and answer pairs.

## Intent &amp; Response


Each question and answer pairs in the knowledge base can be map to an intent and response pair.



Come up with multiple queries that can be map to an intent. The more queries that can be matched to the intent, the more accurate the FAQ chatbot will be.

These queries &amp; intents can then be fit into a machine learning engine to build a model. This model can then match user&#39;s query to the correct intent even when the user query isn&#39;t an exact match to the queries trained.

Identifying the keywords for each question and answer pair can be helpful. One such method can be to use the _tf-idf method_. The keywords identify can be used to form query for the intent.

A fall-back intent is an intent that will be match when no other intents are matched. The response to the fall-back intent can be:

- To notify the user that the chatbot do not understand
  - &quot;Sorry I don&#39;t understand, could you rephrase your question?&quot;
- To narrow down the intents for the user
  - &quot;Sorry I don&#39;t understand, do you mean \_questions\_?

## Testing and improving

After users test out the chatbot, there will be 4 different outcomes.

| Intent Match and Correct Match | True Positive |
| --- | --- |
| Intent Match but Wrong Match | False Positive |
| Fall-back Intent and Correct Match | True Negative |
| Fall-back Intent but Wrong Match | False Negative |

The goal is to maximise the true positive and true negative outcomes, at the same time minimise the false positive and false negative outcomes.

False negative outcomes – the questions can be added to the queries that match the correct intent and retrain the ML model.

False positive outcomes – either

1. a)The query can be match to other intent, then the questions can be add to the correct intent and retrain the ML model
2. b)The query cannot to match to any intent, that means the query is impossible to answer by the chatbot based on the knowledge base that is train upon.
  1. Add a new intent to resolve the query OR
  2. Add the query to match the fall-back intent

The testing phase is an **iterative process**. As more users uses the chatbot, you can understand the user&#39;s interaction with the chatbot and improve on it.

### Good Reads

[Welcome - Conversation design](https://designguidelines.withgoogle.com/conversation/)

[Chapter 11: ChatBots to Que](https://medium.com/deep-math-machine-learning-ai/chapter-11-chatbots-to-question-answer-systems-e06c648ac22a)[stion &amp; Answer systems. - Deep Math Machine learning.ai - Medium](https://medium.com/deep-math-machine-learning-ai/chapter-11-chatbots-to-question-answer-systems-e06c648ac22a)
