## Pre-Training
pre-training is basically training an LLM on a large amount of data (like internet data) with the primary task of predicting words in a sentence. 

Now there are two ways in which we can do this.
1. MLM (Masked Language Model): certain percentage of words in the training set are masked, and the task of the model is to predict these missing words. used by bi-directional models like BERT.
Note that in this task, the model can see the words preceding as well as succeeding the missing word and thats why its called bi-directional.

2. Auto-regressive (eg. GPT): Uni-directional and they are trained to predict the next word without seeing the succeeding ones. This pre-training process is usually very expensive (few thousand to more than a million dollars) and takes a long time (few days to few months) to complete.


## Fine-Tuning
- If use these pre-trained language models (PLMs) for specific tasks (eg. sentence classification, named entity recognition, question-answering, etc), we need to fine-tune them
- It usually requires much less data (~ 100k words) as compared to whats needed for pre-training (few billion words). 
- During the fine-tuning process, we add a task-specific layer to the PLMs and carry out the usual backpropagation method using a suitable loss function. All the model parameters are updated through gradient descent and not just the task-specific layer.
- You can also freeze certain layers and fine-tune the rest
- Hugging face library for PLMs

## In-Context Learning
- Task-specific fine-tuning becomes quite expensive for large GPT-like models which have several billion parameters. Because during fine-tuning also, all the model parameters have to be updated and even on a smaller dataset.
- So, instead of fine-tuning the model with a hundred or thousand input texts, the model just takes a few task-specific examples (<10 usually) as input, and then quickly figures out how to perform well on that tasks using some sort of bayesian inference (link below)
- There is no update of the model weight that happens! No backpropagation and no gradient descent!
- Like super smart students who needs to study for couple of hours before exams.

References:
- https://medium.com/@atmabodha/pre-training-fine-tuning-and-in-context-learning-in-large-language-models-llms-dd483707b122

- Chat GPT telling how it performs the Bayesian Inference: 
https://medium.com/@atmabodha/how-does-gpt-do-in-context-learning-5f37866813dc