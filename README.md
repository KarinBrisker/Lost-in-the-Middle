## Lost in the Middle: How Language Models Use Long Contexts

This repository contains code that is inspired by the research paper '_Lost in the Middle: How Language Models Use Long Contexts_' (https://arxiv.org/abs/2307.03172) to investigate how well large language models perform when presented with long contexts. The goal is to investigate the effectiveness of various models and components when processing long contexts.
 
### Overview

The code is provided as a Jupyter Notebook (`NLP task.ipynb`) and is designed to be executed on Google Colaboratory. It uses various libraries and models to carry out the task, including sentence embeddings, transformers, and retrievers.

### Installation

Before running the code, ensure that you have the required packages installed. The following packages are used:

- `farm-haystack`: A library for building and training large-scale QA pipelines.
- `transformers`: A popular library for utilizing pre-trained transformer models.
- `sentence-transformers`: A library for generating sentence embeddings using transformer models.
- `langchain`: A library for loading documents from Wikipedia.
- `wikipedia`: A Python wrapper for the Wikipedia API.
- `seaborn` and `matplotlib`: Libraries for data visualization.

You can install these packages using the following commands:

```bash
pip install farm-haystack
pip install farm-haystack[faiss]
pip install transformers
pip install sentence-transformers
pip install langchain
pip install wikipedia
pip install seaborn matplotlib
```

### Model Choices

The code employs several models and components:

- A SentenceTransformer model ("distilbert-base-nli-stsb-mean-tokens") for generating sentence embeddings.
- A FAISSDocumentStore that uses the FAISS library for efficient vector similarity search.
- A FARMReader model ("deepset/roberta-base-squad2") for extractive question answering.
- An EmbeddingRetriever that uses the SentenceTransformer model for retrieving documents based on embeddings.
- An ExtractiveQAPipeline that combines the retriever and reader for extractive question answering.
- A pipeline for extractive question answering using the "distilbert-base-cased-distilled-squad" model.

### Evaluation

The notebook focuses on evaluating the accuracy of the QA pipeline under different conditions:

1. **Accuracy vs. Number of Documents in Input Context**: The code evaluates how the accuracy of the QA pipeline changes with different numbers of documents (passages) in the input context. It retrieves passages from Wikipedia, varying the number of passages, and evaluates the QA pipeline's accuracy.

2. **Accuracy vs. Position of GT (Ground Truth) in Input Context**: The code examines how the accuracy of the QA pipeline is affected by the position of the ground truth answer within the input context. It retrieves passages, inserts the ground truth answer at different positions, and evaluates the accuracy.

### Running the Code

To run the code, follow these steps:

1. Make sure you have installed the required packages as mentioned above.
2. Load the provided Jupyter Notebook (`NLP task.ipynb`) in a Jupyter environment, preferably on Google Colaboratory.
3. Execute the cells in the notebook one by one to observe the evaluation results and visualizations.
