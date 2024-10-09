# Generative AI with Python: A Comprehensive Guide

## Table of Contents
1. [Introduction](#introduction)
2. [LangChain](#langchain)
3. [Embeddings](#embeddings)
   - [Cosine Similarity](#cosine-similarity)
   - [PGVector](#pgvector)
   - [FAISS](#faiss)
   - [Pinecone](#pinecone)
   - [Typesense](#typesense)
4. [Speech to Text](#speech-to-text)
5. [Text to Speech](#text-to-speech)
6. [Image Processing](#image-processing)
7. [Video Processing](#video-processing)
8. [Data Loaders and DataFrames](#data-loaders-and-dataframes)
9. [Chatbot Implementation with LangChain](#chatbot-implementation-with-langchain)
10. [Comparative Analysis of LLM Models](#comparative-analysis-of-llm-models)
11. [Additional Resources](#additional-resources)

## Introduction

Generative AI involves using algorithms to generate new content based on input data. With Python, a rich ecosystem of libraries allows developers to implement generative models for various applications, from natural language processing to audio-visual generation.

## LangChain

**LangChain** is a framework designed for building applications with LLMs. It provides modular components for chaining together different steps in a process, such as text generation, conversation history management, and more.

### Example:
```python
from langchain import LLMChain, OpenAI

llm = OpenAI(model="gpt-3.5-turbo")
chain = LLMChain(llm=llm, prompt="What are the benefits of using generative AI?")
response = chain.run()
print(response)
```

## Embeddings

Embeddings are numerical representations of data that capture semantic relationships. They are crucial in tasks like similarity search and clustering.

### Cosine Similarity
Cosine similarity measures the cosine of the angle between two vectors, providing a metric of similarity.

**Example:**
```python
from sklearn.metrics.pairwise import cosine_similarity
import numpy as np

# Sample embeddings
vec_a = np.array([[1, 2, 3]])
vec_b = np.array([[4, 5, 6]])
similarity = cosine_similarity(vec_a, vec_b)
print(similarity)
```

### PGVector
PGVector is a PostgreSQL extension for storing and querying vector embeddings.

### FAISS
FAISS (Facebook AI Similarity Search) is a library for efficient similarity search and clustering of dense vectors.

### Pinecone
Pinecone is a managed vector database service optimized for similarity search.

### Typesense
Typesense is an open-source search engine optimized for speed and relevancy.

### Comparison Table for Embedding Models

| Model      | Dimensions | Method Used         | Use Case                                |
|------------|------------|---------------------|-----------------------------------------|
| PGVector   | Up to 1536 | PostgreSQL           | Storing and querying embeddings          |
| FAISS      | Variable   | Approximate Nearest Neighbor | Large-scale similarity search          |
| Pinecone   | Up to 512  | Managed Service      | Real-time vector similarity search      |
| Typesense  | Up to 2048 | Inverted Index       | Fast, relevant search                   |

## Speech to Text

Speech-to-text (STT) technology converts spoken language into text. Libraries like `SpeechRecognition` can be used for this purpose.

### Example:
```python
import speech_recognition as sr

recognizer = sr.Recognizer()
with sr.Microphone() as source:
    print("Say something!")
    audio = recognizer.listen(source)

try:
    print("You said: " + recognizer.recognize_google(audio))
except sr.UnknownValueError:
    print("Sorry, I could not understand the audio.")
```

## Text to Speech

Text-to-speech (TTS) technology converts written text into spoken language. Libraries like `gTTS` (Google Text-to-Speech) can facilitate this.

### Example:
```python
from gtts import gTTS
import os

text = "Hello, welcome to Generative AI with Python!"
tts = gTTS(text=text, lang='en')
tts.save("welcome.mp3")
os.system("mpg321 welcome.mp3")
```

## Image Processing

Image processing involves manipulating images to extract or modify information. Libraries like `OpenCV` and `PIL` are popular in Python.

### Example:
```python
import cv2

# Load an image
image = cv2.imread('image.jpg')
# Convert to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
cv2.imwrite('gray_image.jpg', gray_image)
```

## Video Processing

Video processing involves manipulating video files for various applications, such as video editing, object detection, etc. Libraries like `OpenCV` and `moviepy` are commonly used.

### Example:
```python
import cv2

# Capture video from the webcam
cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    cv2.imshow('Video', frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()
```

## Data Loaders and DataFrames

Data loaders and DataFrames are crucial for handling and processing datasets in Python. The `pandas` library is widely used for this purpose.

### Example:
```python
import pandas as pd

# Load a CSV file into a DataFrame
df = pd.read_csv('data.csv')

# Perform operations
df['new_column'] = df['existing_column'] * 2
print(df.head())
```

## Chatbot Implementation with LangChain

Building a chatbot with LangChain involves setting up an LLM to respond to user inputs.

### Example:
```python
from langchain import LLMChain, OpenAI

llm = OpenAI(model="gpt-3.5-turbo")

def chatbot_response(user_input):
    chain = LLMChain(llm=llm, prompt=f"User: {user_input}\nBot:")
    return chain.run()

user_input = "What is generative AI?"
response = chatbot_response(user_input)
print(response)
```

## Comparative Analysis of LLM Models

Various LLM models are available, each with unique capabilities. Below is a comparison table of several popular LLMs:

| Model   | Provider          | Capabilities                                   | Use Cases                     |
|---------|-------------------|------------------------------------------------|-------------------------------|
| GPT-3   | OpenAI            | Text generation, conversation, summarization   | Chatbots, content creation    |
| Claude  | Anthropic         | Safety-focused, contextual understanding        | Customer service, education    |
| LLaMA   | Meta              | Research-oriented, customizable                 | Research, experimentation      |
| Groq    | Groq              | Fast inference, low-latency                     | Production-scale applications  |

## Additional Resources

- **Documentation**: Refer to the official documentation for libraries like LangChain, OpenAI, and others for advanced features.
- **Tutorials**: Explore online tutorials for practical implementations of generative AI models.
- **Communities**: Engage with communities on platforms like GitHub, Stack Overflow, and Reddit for support and collaboration.

## OpenAI Models Overview

| Model Name              | Description                                                 | Max Tokens (Input) | Max Tokens (Output) | Context Length (Tokens) |
|------------------------|-------------------------------------------------------------|---------------------|----------------------|--------------------------|
| **GPT-3**              | The original GPT-3 model, capable of generating coherent and contextually relevant text. Ideal for various NLP tasks like summarization, translation, and creative writing. | 4096                | 4096                 | 4096                     |
| **GPT-3.5 Turbo**     | A more optimized and faster variant of GPT-3, specifically designed for chat applications. It offers better performance and lower latency. Suitable for real-time applications and interactive systems. | 4096                | 4096                 | 4096                     |
| **GPT-4**              | The latest model with improved understanding and generation capabilities, providing better context handling and nuanced responses. It excels in complex reasoning tasks and creative content generation. | 8192                | 8192                 | 8192                     |
| **GPT-4 Turbo**       | An optimized version of GPT-4, providing similar capabilities at a lower cost and faster response times. Particularly effective for applications requiring high throughput. | 8192                | 8192                 | 8192                     |
| **GPT-4 Turbo Mini**  | A smaller variant of GPT-4 Turbo designed for low-latency applications, capable of handling up to 128k tokens for both input and output. Ideal for scenarios requiring extensive context and fast processing. | 128000              | 128000               | 128000                   |
| **Codex**              | A specialized version of GPT-3 tailored for code generation and understanding. It is capable of translating natural language prompts into code snippets in various programming languages. | 4096                | 4096                 | 4096                     |
| **DALL·E**             | A model focused on generating images from textual descriptions. It can create unique images based on the prompts provided. Primarily used for creative visual applications. | -                   | -                    | -                        |
| **Whisper**            | A speech recognition model capable of transcribing audio into text. It supports multiple languages and is useful for applications requiring speech-to-text capabilities. | -                   | -                    | -                        |

### Key Points

- **Max Tokens (Input/Output)**: Indicates the maximum number of tokens the model can accept as input and generate as output. A token can be a word or part of a word.

- **Context Length**: Refers to the amount of prior text the model can consider during text generation. A longer context allows for more coherent and contextually relevant responses.

- **Specialized Models**: Models like Codex and DALL·E are optimized for specific tasks, such as code generation and image generation, and may have different parameters.


# Chatbots -

1. **RAG-based Chatbot**
2. **RAG-based Chatbot with Memory (Conversational)**
3. **SQL Agent Chatbot**

### 1. RAG-based Chatbot

A Retrieval-Augmented Generation (RAG) chatbot combines retrieval-based techniques with generative models. It retrieves relevant documents based on user input and uses a language model to generate responses based on those documents.

#### Implementation

```python
import os
from langchain import OpenAI
from langchain.chains import RetrievalQA
from langchain.document_loaders import SimpleDocumentLoader
from langchain.vectorstores import FAISS
from langchain.embeddings import OpenAIEmbeddings

# Load documents
loader = SimpleDocumentLoader("path/to/your/documents")
documents = loader.load()

# Create embeddings
embeddings = OpenAIEmbeddings()
vector_store = FAISS.from_documents(documents, embeddings)

# Initialize RetrievalQA
llm = OpenAI(model="gpt-3.5-turbo")
retrieval_qa = RetrievalQA(llm=llm, retriever=vector_store.as_retriever())

# Chatbot function
def rag_chatbot(query):
    response = retrieval_qa({"query": query})
    return response["result"]

# Example usage
user_query = "What are the benefits of RAG?"
print(rag_chatbot(user_query))
```

### 2. RAG-based Chatbot with Memory (Conversational)

This version retains conversational context by storing the chat history, allowing the model to remember previous interactions.

#### Implementation

```python
from langchain.memory import ConversationBufferMemory
from langchain.chains import ConversationalRetrievalChain

# Initialize memory
memory = ConversationBufferMemory()

# Initialize Conversational RetrievalQA
conversational_qa = ConversationalRetrievalChain(
    llm=llm,
    retriever=vector_store.as_retriever(),
    memory=memory
)

# Chatbot function with memory
def rag_chatbot_with_memory(user_input):
    response = conversational_qa({"question": user_input})
    return response["answer"]

# Example usage
print(rag_chatbot_with_memory("What are the benefits of RAG?"))
print(rag_chatbot_with_memory("Can you elaborate on that?"))
```

### 3. SQL Agent Chatbot

This chatbot uses an SQL database to retrieve information based on user queries. It generates SQL commands and executes them to fetch relevant data.

#### Implementation

```python
import sqlite3
from langchain.agents import SQLDatabase, create_sql_agent
from langchain.llms import OpenAI

# Connect to the database
connection = sqlite3.connect("path/to/your/database.db")
database = SQLDatabase(connection)

# Create the SQL agent
llm = OpenAI(model="gpt-3.5-turbo")
sql_agent = create_sql_agent(llm, database)

# Chatbot function for SQL agent
def sql_chatbot(query):
    response = sql_agent({"input": query})
    return response["output"]

# Example usage
user_query = "What are the top 5 products by sales?"
print(sql_chatbot(user_query))
```
