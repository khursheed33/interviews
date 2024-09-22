# Generative AI QnA

**Generative AI (LLMs):**
Generative AI (gen AI) is a type of artificial intelligence (AI) that uses models to create content such as text, images, code, and synthetic data. Large language models (LLMs) are a specific type of generative AI that are designed to perform natural language processing (NLP) tasks. LLMs are deep learning models that analyze large amounts of data to identify patterns and predict language responses. They can then create new text combinations that mimic natural language based on their training data. The more parameters an LLM has, the more detailed and specific the content it can create.

**OpenAI APIs**

| Model | Description |
|-------|-------------|
| GPT-4o | The fastest and most affordable flagship model |
| GPT-4 Turbo and GPT-4 | The previous set of high-intelligence models |
| GPT-3.5 Turbo | A fast, inexpensive model for simple tasks |
| DALL·E | A model that can generate and edit images given a natural language prompt |
| TTS | A set of models that can convert text into natural sounding spoken audio |
| Whisper | A model that can convert audio into text |
| Embeddings | A set of models that can convert text into a numerical form |
| Moderation | A fine-tuned model that can detect whether text may be sensitive or unsafe |
| GPT base | A set of models without instruction following that can understand as well as generate natural language or code |
| Deprecated | A full list of models that have been deprecated along with the suggested replacement |

1. Text-to-Text

This involves generating text based on input text. We'll use OpenAI's GPT model for this example.

```python
import openai

openai.api_key = 'your-api-key'

def text_to_text(prompt):
    response = openai.Completion.create(
        engine="text-davinci-002",
        prompt=prompt,
        max_tokens=100
    )
    return response.choices[0].text.strip()

prompt = "Translate the following English text to French: 'Hello, how are you?'"
result = text_to_text(prompt)
print(result)
```

2. Text-to-Speech

For this, we'll use Azure's Text-to-Speech service.

```python
import azure.cognitiveservices.speech as speechsdk

def text_to_speech(text):
    speech_config = speechsdk.SpeechConfig(subscription="your-subscription-key", region="your-region")
    speech_config.speech_synthesis_voice_name = "en-US-AriaNeural"

    speech_synthesizer = speechsdk.SpeechSynthesizer(speech_config=speech_config)
    result = speech_synthesizer.speak_text_async(text).get()

    if result.reason == speechsdk.ResultReason.SynthesizingAudioCompleted:
        print("Speech synthesized for text [{}]".format(text))
    elif result.reason == speechsdk.ResultReason.Canceled:
        print("Speech synthesis canceled")

text_to_speech("Hello, how are you?")
```

3. Speech-to-Text

We'll use OpenAI's Whisper model for this task.

```python
import openai

openai.api_key = 'your-api-key'

def speech_to_text(audio_file):
    with open(audio_file, "rb") as file:
        transcript = openai.Audio.transcribe("whisper-1", file)
    return transcript['text']

audio_file = "path/to/your/audio/file.mp3"
result = speech_to_text(audio_file)
print(result)
```

4. Text-to-Image

For this, we'll use OpenAI's DALL-E model.

```python
import openai

openai.api_key = 'your-api-key'

def text_to_image(prompt):
    response = openai.Image.create(
        prompt=prompt,
        n=1,
        size="1024x1024"
    )
    image_url = response['data'][0]['url']
    return image_url

prompt = "A cute baby penguin wearing a top hat"
image_url = text_to_image(prompt)
print(f"Generated image URL: {image_url}")
```

5. Text-to-Video

OpenAI doesn't have a direct text-to-video API, but we can use other services like Runway ML for this task.

```python
import runway

runway.api_key = "your-runway-api-key"

def text_to_video(prompt):
    model = runway.Model("stable-diffusion-v1-5")
    output = model.generate(
        prompt=prompt,
        num_frames=30,
        fps=30,
        guidance_scale=7.5,
        num_inference_steps=50
    )
    output.save("output_video.mp4")

prompt = "A spaceship launching from Earth into a starry sky"
text_to_video(prompt)
```

6. Text-to-Avatar

For this, we can use the Ready Player Me API, which creates 3D avatars based on text descriptions.

```python
import requests
import json

def text_to_avatar(description):
    url = "https://api.readyplayer.me/v1/avatars"
    
    payload = json.dumps({
        "description": description,
        "style": "realistic"
    })
    
    headers = {
        'Content-Type': 'application/json',
        'Authorization': 'Bearer your-api-key'
    }
    
    response = requests.post(url, headers=headers, data=payload)
    
    if response.status_code == 200:
        avatar_url = response.json()['avatar']
        return avatar_url
    else:
        return f"Error: {response.status_code}, {response.text}"

description = "A tall man with short brown hair and blue eyes, wearing a red t-shirt"
avatar_url = text_to_avatar(description)
print(f"Generated avatar URL: {avatar_url}")
```

1. Microsoft Text to Speech:
Microsoft's Text to Speech (TTS) is part of Azure Cognitive Services. It converts text into natural-sounding speech using advanced neural network models. It supports multiple languages and voices, and can be customized for specific use cases.

Example using Python:

```python
import azure.cognitiveservices.speech as speechsdk

speech_config = speechsdk.SpeechConfig(subscription="your-key", region="your-region")
speech_config.speech_synthesis_voice_name = "en-US-JennyNeural"

speech_synthesizer = speechsdk.SpeechSynthesizer(speech_config=speech_config)
result = speech_synthesizer.speak_text_async("Hello, world!").get()
```

2. D-ID Speech to Avatar:
D-ID is a company that provides AI-powered video generation. Their Speech to Avatar technology can create realistic talking head videos from audio input. This can be used for creating virtual presenters, digital humans, or animated avatars.

Example using their API (pseudo-code):

```python
import requests

url = "https://api.d-id.com/talks"
payload = {
    "script": {
        "type": "text",
        "input": "Hello, I'm a digital avatar created by D-ID."
    },
    "source_url": "https://example.com/avatar_image.jpg"
}
headers = {
    "Authorization": "Basic your_api_key",
    "Content-Type": "application/json"
}

response = requests.post(url, json=payload, headers=headers)
```

3. VASA-1:
VASA-1 (Visual Affective Speech Animation) is an AI model developed by ByteDance that generates realistic talking face videos from audio input. It can create highly expressive and emotionally responsive animations.

As of my last update, there wasn't a public API for VASA-1, but researchers could potentially implement it using the published paper and code if available.

4. Emote-Portrait-Alive:
Emote-Portrait-Alive is a technique for creating animated portraits from still images. It uses AI to add realistic facial expressions and movements to static portraits.

This is typically implemented as part of larger AI image processing pipelines, often using frameworks like PyTorch or TensorFlow.

5. Langchain:
Langchain is a framework for developing applications powered by language models. It provides tools for combining LLMs with other sources of computation or knowledge.

Example:

```python
from langchain import OpenAI, ConversationChain

llm = OpenAI(temperature=0)
conversation = ConversationChain(llm=llm, verbose=True)

response = conversation.predict(input="Hi there!")
print(response)
```

6. Hugging Face Transformers:
Hugging Face Transformers is a popular library that provides pre-trained models for various NLP tasks. It supports models like BERT, GPT, and T5.

Example:

```python
from transformers import pipeline

classifier = pipeline("sentiment-analysis")
result = classifier("I love this product!")
print(result)
```

7. spaCy:
spaCy is an open-source library for advanced Natural Language Processing in Python. It's designed for production use and helps in tasks like named entity recognition, part-of-speech tagging, and dependency parsing.

Example:

```python
import spacy

nlp = spacy.load("en_core_web_sm")
doc = nlp("Apple is looking at buying U.K. startup for $1 billion")

for ent in doc.ents:
    print(ent.text, ent.label_)
```

8. TensorFlow:
TensorFlow is an open-source machine learning framework developed by Google. It's used for both research and production at Google and many other companies.

Example:

```python
import tensorflow as tf

mnist = tf.keras.datasets.mnist
(x_train, y_train), (x_test, y_test) = mnist.load_data()
x_train, x_test = x_train / 255.0, x_test / 255.0

model = tf.keras.models.Sequential([
  tf.keras.layers.Flatten(input_shape=(28, 28)),
  tf.keras.layers.Dense(128, activation='relu'),
  tf.keras.layers.Dropout(0.2),
  tf.keras.layers.Dense(10)
])
```

9. PyTorch:
PyTorch is an open-source machine learning library developed by Facebook's AI Research lab. It's known for its ease of use in dynamic computational graphs.

Example:

```python
import torch
import torch.nn as nn

class SimpleNet(nn.Module):
    def __init__(self):
        super(SimpleNet, self).__init__()
        self.fc = nn.Linear(10, 5)

    def forward(self, x):
        return self.fc(x)

model = SimpleNet()
input = torch.randn(3, 10)
output = model(input)
print(output)
```

10. Keras:
Keras is a high-level neural networks API, written in Python and capable of running on top of TensorFlow, CNTK, or Theano. It's known for its user-friendliness and modularity.

Example:

```python
from tensorflow import keras

model = keras.Sequential([
    keras.layers.Dense(64, activation='relu', input_shape=(32,)),
    keras.layers.Dense(64, activation='relu'),
    keras.layers.Dense(10, activation='softmax')
])

model.compile(optimizer='adam',
              loss='categorical_crossentropy',
              metrics=['accuracy'])
```


1. OpenAI Gym:
OpenAI Gym is a toolkit for developing and comparing reinforcement learning algorithms. It provides a standard API for communication between learning algorithms and environments, as well as a standard set of environments to benchmark algorithm performance.

Example:
```python
import gym

env = gym.make('CartPole-v1')
observation = env.reset()

for _ in range(1000):
    env.render()
    action = env.action_space.sample()  # your agent here (this takes random actions)
    observation, reward, done, info = env.step(action)
    
    if done:
        observation = env.reset()

env.close()
```

2. NVIDIA CUDA:
CUDA (Compute Unified Device Architecture) is a parallel computing platform and programming model developed by NVIDIA for general computing on their GPUs. It allows developers to use GPU acceleration for various computational tasks.

Example (using PyCUDA):
```python
import pycuda.autoinit
import pycuda.driver as drv
import numpy as np
from pycuda.compiler import SourceModule

mod = SourceModule("""
__global__ void multiply_them(float *dest, float *a, float *b)
{
  const int i = threadIdx.x;
  dest[i] = a[i] * b[i];
}
""")

multiply_them = mod.get_function("multiply_them")

a = np.random.randn(400).astype(np.float32)
b = np.random.randn(400).astype(np.float32)

dest = np.zeros_like(a)
multiply_them(
    drv.Out(dest), drv.In(a), drv.In(b),
    block=(400,1,1), grid=(1,1))

print(dest-a*b)
```

3. cuDNN:
NVIDIA cuDNN (CUDA Deep Neural Network library) is a GPU-accelerated library of primitives for deep neural networks. It provides highly tuned implementations for standard routines such as forward and backward convolution, pooling, normalization, and activation layers.

cuDNN is typically used as a backend for higher-level frameworks like TensorFlow or PyTorch, rather than being used directly.

4. Dask:
Dask is a flexible library for parallel computing in Python. It scales Python libraries like NumPy, Pandas, and Scikit-Learn to distributed environments and provides an advanced task scheduling system.

Example:
```python
import dask.dataframe as dd

# Read a large CSV file
df = dd.read_csv('large_file.csv')

# Perform operations
result = df.groupby('column').mean().compute()
```

5. FAISS:
FAISS (Facebook AI Similarity Search) is a library for efficient similarity search and clustering of dense vectors. It's particularly useful for tasks involving large-scale nearest neighbor search.

Example:
```python
import faiss
import numpy as np

d = 64                           # dimension
nb = 100000                      # database size
nq = 10000                       # nb of queries
np.random.seed(1234)             # make reproducible
xb = np.random.random((nb, d)).astype('float32')
xq = np.random.random((nq, d)).astype('float32')

index = faiss.IndexFlatL2(d)   # build the index
index.add(xb)                  # add vectors to the index
k = 4                          # we want to see 4 nearest neighbors
D, I = index.search(xq, k)     # actual search
print(I[:5])                   # neighbors of the 5 first queries
```

6. AllenNLP:
AllenNLP is an open-source NLP research library built on PyTorch. It provides high-level abstractions and APIs for developing deep learning models, particularly for tasks like machine comprehension, textual entailment, and more.

Example:
```python
from allennlp.predictors.predictor import Predictor

predictor = Predictor.from_path("https://storage.googleapis.com/allennlp-public-models/bert-base-srl-2020.03.24.tar.gz")
prediction = predictor.predict(
  sentence="Did Uriah honestly think he could beat the game in under three hours?"
)
print(prediction)
```

7. T5:
T5 (Text-to-Text Transfer Transformer) is a transformer model developed by Google. It frames all NLP tasks as a "text-to-text" problem, where both inputs and outputs are always text strings.

Example using Hugging Face Transformers:
```python
from transformers import T5Tokenizer, T5ForConditionalGeneration

tokenizer = T5Tokenizer.from_pretrained("t5-small")
model = T5ForConditionalGeneration.from_pretrained("t5-small")

input_text = "translate English to German: The house is wonderful."
input_ids = tokenizer(input_text, return_tensors="pt").input_ids

outputs = model.generate(input_ids)
print(tokenizer.decode(outputs[0], skip_special_tokens=True))
```

8. Haystack:
Haystack is an open-source framework for building search systems that work intelligently over large document collections. It's particularly useful for question answering and semantic search applications.

Example:
```python
from haystack.nodes import EmbeddingRetriever
from haystack.document_stores import InMemoryDocumentStore

document_store = InMemoryDocumentStore(use_bm25=True)

retriever = EmbeddingRetriever(
    document_store=document_store,
    embedding_model="sentence-transformers/multi-qa-mpnet-base-dot-v1"
)

# Assuming you have documents in the document_store
documents = document_store.get_all_documents()
document_store.update_embeddings(retriever)

# Query
query = "What is the capital of France?"
retrieved_docs = retriever.retrieve(query)

for doc in retrieved_docs:
    print(doc.content)
```


1. AutoGen:

AutoGen is a framework developed by Microsoft for building Large Language Model (LLM) applications using multiple agents. It allows for the creation of conversable AI agents that can interact with each other and with humans to solve tasks.

Key features of AutoGen:
- Multi-agent conversations
- Human-AI interaction
- Customizable agent roles and behaviors
- Integration with various LLMs

Here's a basic example of using AutoGen:

```python
from autogen import AssistantAgent, UserProxyAgent, config_list_from_json

# Load LLM configuration
config_list = config_list_from_json("OAI_CONFIG_LIST")

# Create an assistant agent
assistant = AssistantAgent(name="assistant", llm_config={"config_list": config_list})

# Create a user proxy agent
user_proxy = UserProxyAgent(name="user_proxy", code_execution_config={"work_dir": "coding"})

# Start a conversation
user_proxy.initiate_chat(assistant, message="How can I create a simple web server in Python?")
```

In this example, we create two agents: an assistant and a user proxy. The user proxy initiates a conversation with the assistant about creating a web server in Python. The agents can then engage in a back-and-forth conversation to solve the task.

2. CrewAI:

CrewAI is a framework for orchestrating role-playing, autonomous AI agents. It's designed to facilitate collaborative task completion by AI agents, each with its own specialized role.

Key features of CrewAI:
- Role-based agent creation
- Task planning and execution
- Inter-agent communication
- Integration with various AI models

Here's a basic example of using CrewAI:

```python
from crewai import Agent, Task, Crew
from langchain.llms import OpenAI

# Initialize the language model
llm = OpenAI()

# Create agents
researcher = Agent(
    role='Researcher',
    goal='Uncover groundbreaking information',
    backstory='You are an expert researcher with a keen eye for detail',
    verbose=True,
    llm=llm
)

writer = Agent(
    role='Writer',
    goal='Craft compelling content',
    backstory='You are a skilled writer with a way with words',
    verbose=True,
    llm=llm
)

# Create tasks
research_task = Task(
    description='Research the latest advancements in AI',
    agent=researcher
)

writing_task = Task(
    description='Write an article about AI advancements',
    agent=writer
)

# Create a crew
crew = Crew(
    agents=[researcher, writer],
    tasks=[research_task, writing_task],
    verbose=2
)

# Execute the crew's plan
result = crew.kickoff()

print(result)
```

In this example, we create two agents (a researcher and a writer) and assign them specific tasks. The Crew object orchestrates the execution of these tasks, allowing the agents to work together to research AI advancements and write an article about them.

Both AutoGen and CrewAI represent a shift towards more complex, multi-agent AI systems that can tackle sophisticated tasks through collaboration and specialization. These frameworks allow developers to create AI systems that can break down complex problems, delegate subtasks to specialized agents, and synthesize results into coherent solutions.

The key difference between the two is that AutoGen focuses more on facilitating conversations between agents (including human-in-the-loop scenarios), while CrewAI emphasizes role-playing and task planning for autonomous execution.


1. Embeddings (Dimension, Tokens):

Embeddings are dense vector representations of words, phrases, or entire documents. They capture semantic meaning in a way that machines can understand and process.

- Dimension: The number of values in the vector. Higher dimensions can capture more nuanced relationships but require more computational resources.
- Tokens: The basic units of text (often words or subwords) that are converted into embeddings.

Example using sentence-transformers:

```python
from sentence_transformers import SentenceTransformer

model = SentenceTransformer('all-MiniLM-L6-v2')
sentences = ["This is an example sentence", "Each sentence is converted to a vector"]

embeddings = model.encode(sentences)
print(f"Embedding dimension: {embeddings.shape[1]}")
print(f"Number of embeddings: {embeddings.shape[0]}")
```

2. Quantization of LLM model:

Quantization is the process of reducing the precision of the model's weights, typically from 32-bit floating-point to lower bit representations (e.g., 8-bit integers). This reduces model size and increases inference speed, often with minimal impact on performance.

Example using transformers:

```python
from transformers import AutoModelForCausalLM, AutoTokenizer

model_id = "gpt2"
tokenizer = AutoTokenizer.from_pretrained(model_id)
model = AutoModelForCausalLM.from_pretrained(model_id, load_in_8bit=True)

print(f"Model size: {model.get_memory_footprint() / 1e6:.2f} MB")
```

3. LoRA (Low-Rank Adaptation):

LoRA is a technique for efficient fine-tuning of large language models. It adds small, trainable rank decomposition matrices to existing weights, allowing for adaptation with fewer parameters.

Example using PEFT:

```python
from transformers import AutoModelForCausalLM, AutoTokenizer
from peft import get_peft_model, LoraConfig, TaskType

model_id = "gpt2"
tokenizer = AutoTokenizer.from_pretrained(model_id)
model = AutoModelForCausalLM.from_pretrained(model_id)

peft_config = LoraConfig(
    task_type=TaskType.CAUSAL_LM, 
    r=8, 
    lora_alpha=32, 
    lora_dropout=0.1
)

peft_model = get_peft_model(model, peft_config)
print(f"Trainable params: {peft_model.print_trainable_parameters()}")
```

4. QLoRA (Quantized LoRA):

QLoRA combines quantization and LoRA. It quantizes the base model to 4-bit precision and uses LoRA for fine-tuning, allowing for efficient adaptation of very large models on consumer hardware.

Example (conceptual, as QLoRA often requires specific libraries):

```python
from transformers import AutoModelForCausalLM, AutoTokenizer
from peft import get_peft_model, LoraConfig, TaskType
# Assume we have a custom quantize_model function
from custom_quantization import quantize_model

model_id = "gpt2"
tokenizer = AutoTokenizer.from_pretrained(model_id)
model = AutoModelForCausalLM.from_pretrained(model_id)

# Quantize the model to 4-bit
quantized_model = quantize_model(model, bits=4)

peft_config = LoraConfig(task_type=TaskType.CAUSAL_LM, r=8, lora_alpha=32, lora_dropout=0.1)
qlora_model = get_peft_model(quantized_model, peft_config)
```

Other popular terms in Generative AI:

5. Prompt Engineering:
The practice of designing input prompts to elicit desired outputs from language models.

Example:
```python
from transformers import GPT2LMHeadModel, GPT2Tokenizer

model = GPT2LMHeadModel.from_pretrained("gpt2")
tokenizer = GPT2Tokenizer.from_pretrained("gpt2")

prompt = "Translate the following English text to French: 'Hello, how are you?'"
input_ids = tokenizer.encode(prompt, return_tensors="pt")
output = model.generate(input_ids, max_length=50)

print(tokenizer.decode(output[0], skip_special_tokens=True))
```

6. Fine-tuning:
The process of further training a pre-trained model on a specific dataset to adapt it to a particular task or domain.

7. Zero-shot Learning:
The ability of a model to perform tasks it wasn't explicitly trained on, based on its general knowledge.

8. Few-shot Learning:
The ability of a model to learn a new task from only a few examples.

9. Transformer Architecture:
The foundational architecture for many modern language models, using self-attention mechanisms to process input sequences.

10. Attention Mechanism:
A technique that allows models to focus on different parts of the input when producing output, crucial for handling long-range dependencies in text.


**Transformers:**
https://blog.gopenai.com/how-transformers-and-large-language-models-llms-work-3f20bb41c1ff
![image](https://github.com/khursheed33/interviews/assets/52867369/717e05a0-0b96-4b91-8a9f-8d3bfda4a81c)


