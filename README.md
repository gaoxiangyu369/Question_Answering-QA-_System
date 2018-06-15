# Question_Answering_QA_System

## Instruction

The goal of this project is to build a Question Answering(QA) System to ﬁnd the answer to that question in the corresponding document.

## Dataset

All the data are extracted from SQuAD but with minor changes. The dataset contains over 40000 and 3000 question-answer pairs in training and developing set respectively on 441 articles. And the training data serves to build the QA model and the close inspection. While the development set should be used for detailed analysis. The test set is similar to training data but the answer fields are missing and to be completed. 

## Method

We try to build our question answering system by mimic the human process of answering a question.There are three stages in the whole process. First, we analyze the question as what the question is asking about then we find out the most related context in a given document and finally, we extract the relevant answer from the context.

![QA System Framework](https://github.com/gaoxiangyu369/Question_Answering_QA_System/blob/master/images/Picture1.png)

### Question Classification

We classify the question types base on the question words in the sentence and define six types of question that exist in our training dataset as explained below. If there were multiple question words exist in our question sentence, for example, clauses that start with question words, we use StanfordCoreNLP package to identify the clauses (will be label as SBAR in Part-Of-Speech (POS) tag parsing). Then we exclude the clauses’ token from the original question sentence and only focus on the rest of the tokens. As the example shown below, only “, what form of government did it adopt?” would be our question string. 

Question type | Definition
------------ | -------------
When | Question asking about time, date, period etc. (question words include: when, what date, what time, which years etc.)
Where | Question asking about location, organization etc. (question words include: where, what place, which place etc.)
Who | Question asking about person etc. (question words include: who, whose what person etc.)
Number | Question asking number, money etc. (question words include: how much, how many, what number etc.)
Description | Question asking description, feeling etc. (question words include: what, how)
Binary | Question does not contain any question words. E.g.  Name a reason that…

![Sentence POS Tagging]()
