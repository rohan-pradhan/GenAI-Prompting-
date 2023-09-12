# Builder Workshop 1 - Prompt Engineering Lab

## Introduction 

### Foundation Models (Large Language Models)
Foundation models are a class of generative AI models that are capable of understanding and generating human-like language at a massive scale. These LLMs are trained on vast amounts of text data, often on the order of billions of words or more, using techniques such as unsupervised learning and self-supervised learning. They are capable of generating high-quality human-like language across a wide range of tasks, including language translation, text summarization, and creative writing.

One of the key advantages of foundation models is that they can be fine-tuned on smaller datasets for specific tasks, making them highly adaptable to a wide range of applications. For example, a foundation model that has been pre-trained on a large dataset of news articles and books can be fine-tuned on a smaller dataset of medical texts to generate summaries of medical research papers. Foundation models have the potential to revolutionize the field of natural language processing (NLP) by enabling new forms of language-based applications and services. As these models continue to evolve and improve, we can expect to see even more exciting and transformative applications emerge in the future.

## Zero Shot Prompt Engineering 

### Zero Shot Prompting
Zero-shot prompting enables a model to make predictions about previously unseen data without the need for any additional training.

Zero-shot learning in NLP allows a pre-trained LLM to generate responses to tasks that it hasn’t been specifically trained for. In this technique, the model is provided with an input text and a prompt that describes the expected output from the model in natural language. The pre-trained models can use its knowledge to generate coherent and relevant responses even for prompts it hasn’t specifically been trained on.

In the context of prompt engineering, zero-shot learning can be used to generate natural language text without the need for explicit programming or pre-defined templates.

Zero-shot learning can reduce the time and data required while improving efficiency and accuracy of NLP tasks. Zero-shot learning is used in a variety of NLP tasks, such as question answering, summarization, and text generation.

Here are a few examples of what you can run with your deployed model with zero-shot prompting:

### Zero-Shot Prompting Use Cases 

**1. Text Summarization**

You can enter as input prompt to the text box within the application:

```text 
Summarize the text below:

text = "Amazon Comprehend uses natural language processing (NLP) to extract insights about the content of documents. It develops insights by recognizing the entities, key phrases, language, sentiments, and other common elements in a document. Use Amazon Comprehend to create new products based on understanding the structure of documents. For example, using Amazon Comprehend you can search social networking feeds for mentions of products or scan an entire document repository for key phrases."
```

Feel free to modify the text and experiment with different models to generate variations of the text above.

**2. Question-Answering Prompts** 

You can also prompt the model endpoint with Q-A based queries to generate a relevant output response.

```text
When was the Central Intelligence Agency created?
```

Try inputting the above text in the chatbot UI and inspect your respective output.

**3. Miscelleneous examples**

As another example, here is a sample prompt:

```text
Can Geoffrey Hinton have a conversation with George Washington? 
Give the rationale before answering?
```

Similarly, you can use your creativity to test zero-shot prompting with different examples like the one below and compare the results with one-shot, few-shot and CoT prompting techniques as explained in the next lab.


## One-shot and Few-shot Prompt Engineering


### **One Shot Prompting**:

One-shot prompting is used to generate natural language text with a limited amount of input data such as a single example or template.

One-shot prompting can be combined with other natural language processing techniques like dialogue management and context modeling to create more sophisticated and effective text generation systems.

### One-shot Prompting Examples

Here, we will give one example to ensure the model generates the output structure that we would like to get back. The model will guess what we want in return based on the provided example and its training about the text:

**Example 1:**

```text
Indicate the topic from the Message below:

Message: The intelligence agency uncovered evidence of a terrorist plot targeting a government building.
Topic: national security

Message: Diplomats from several countries are meeting to negotiate a nuclear arms reduction treaty.
Topic:
```

![image_39](./assets/39.png)

**Example 2:**

```text
Generation: Task is to generate airport codes
Text: "The president flew from Washington D.C. to Chicago" Airport codes: DCA, ORD
Text: "The senator traveled from New York City to Seattle" Airport codes:
```
![image_40](./assets/40.png)

### **Few Shot Prompting**

Few-shot prompting is a technique where the model is given a small number of examples, typically between two and five, in order to quickly adapt to new examples of previously seen objects.

Few-shot learning can be used in the context of prompt engineering, to create natural language text with a limited amount of input data. Although it requires less data, this technique can allow for the creation of more versatile and adaptive text generation models.

By using advanced techniques such as few-shot prompting, it is possible to create natural language generation models that are more flexible, adaptable, and engaging for human users.

Here is an example to use few shot prompting with `Text Classification` use case:

```text
Classify the below use-case description to one of the following NLP tasks: Short form generation, Long form generation, Summarization, Classification, Question answering, Paraphrasing, Conversational agent, Information extraction, Generate code

Use case: Summarize intelligence reports into concise briefings for senior officials
NLP task: Summarization

Classify the below use-case description to one of the following NLP tasks: Short form generation, Long form generation, Summarization, Classification, Question answering, Paraphrasing, Conversational agent, Information extraction, Generate code

Use case: Extract entities and relationships from foreign language news sources
NLP task: Information extraction

Classify the below use-case description to one of the following NLP tasks: Short form generation, Long form generation, Summarization, Classification, Question answering, Paraphrasing, Conversational agent, Information extraction, Generate code

Use case: Classify documents or communications as classified or unclassified
NLP task: 
```

Run the above examples to see the output and validate the response on your end.

## Chain of Thought Prompt Engineering 

### **Chain of Thought Prompting** 

Chain-of-thought (CoT) prompting improves the reasoning ability of LLMs by prompting them to generate a series of intermediate steps that lead to the final answer of a multi-step problem.

Now, lets run through some examples.

### Question Answer Prompting

Chain of Thought (CoT) prompting is a recently developed prompting method, which encourages the LLM to explain its reasoning.

Here, we will give an example to ensure the model generates the output structure that we would like to get back with some reasoning. The model will guess what we want in return based on the provided example and its training about the text:

```text
Question: A military unit has 5 tanks. They receive 2 additional tank platoons. Each tank platoon has 3 tanks. How many tanks does the unit have now?

Answer: The military unit started with 5 tanks. 2 tank platoons with 3 tanks each is 6 additional tanks. 5 + 6 = 11 tanks. The total number of tanks is 11.

Question: An intelligence analyst reviews 3 potential threats per day. For each threat, the analyst spends 2 hours per day analyzing intelligence reports and assessing the credibility of the threat. How many hours per week does the analyst spend reviewing threats?
Answer: 
```

Once we have provided a sample response to one of our questions, the model should be able to provide a similar explanation to the previously provided example.

Run the below example and inspect the model response for your deployed model endpoint.

```text
Q1: A classified document is unredacted. Analyst John reviews the document but does not edit or redact it. Is the document still unredacted?

A1: Yes, since Analyst John reviewed but did not edit or redact the classified document, it remains unredacted.

Q2: Manager Shalonda decides only certain sections need to be redacted. She asks Analyst Bob to redact Sections 2 and 4, but not the rest of the document. Analyst Bob redacts Sections 2 and 4 as instructed. He does not edit or redact any other parts of the document. Is the document still partially unredacted?

A2:
```

