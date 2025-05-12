
## Session Overview
- **Duration**: 2–3 hours
- **Audience**: Developers with experience in Python, APIs, and basic LLM concepts
- **Objectives**:
  - Understand LangChain’s core components and advanced features.
  - Build modular, scalable LLM applications.
  - Explore real-world use cases like chatbots, agents, and RAG systems.
- **Topics Covered**:
  - Chains: Modular workflows
  - Agents: Decision-making pipelines
  - Memory: Contextual persistence
  - Tools: External API integrations
  - RAG: Retrieval-Augmented Generation
  - LangChain Expression Language (LCEL)
  - LangSmith for observability

## Prerequisites
- **Skills**:
  - Proficiency in Python (3.8+)
  - Familiarity with LLMs and APIs (e.g., OpenAI, Hugging Face)
  - Basic understanding of vector stores or databases is a plus
- **Tools**:
  - Python 3.8+
  - pip or conda for package management
  - Jupyter Notebook (for running examples)
  - API keys for an LLM provider (e.g., OpenAI, or use open-source models via Hugging Face)
  - Optional: Docker for deploying apps, LangSmith account for observability

## Setup Instructions
1. **Clone the Repository** (if provided):
   ```bash
   git clone <repository-url>
   cd langchain-session
   ```
2. **Create a Virtual Environment**:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```
3. **Install Dependencies**:
   ```bash
   pip install langchain langchain-openai langchain-community faiss-cpu python-dotenv
   ```
4. **Set Up Environment Variables**:
   - Create a `.env` file in the project root:
     ```bash
     touch .env
     ```
   - Add your API keys (e.g., for OpenAI):
     ```env
     OPENAI_API_KEY=your-openai-api-key
     ```
5. **Verify Setup**:
   - Run a simple Python script to test LangChain:
     ```python
     from langchain.llms import OpenAI
     llm = OpenAI(model="gpt-4")
     print(llm("Hello, LangChain!"))
     ```
   - If you see a response, your setup is ready!

## Core Concepts and Examples

### 1. Chains: Modular, Reusable Workflows
Chains combine prompts, LLMs, and processing steps into reusable pipelines.

**Example**: A simple Q&A chain using a prompt template.
```python
from langchain.prompts import PromptTemplate
from langchain.llms import OpenAI
from langchain.chains import LLMChain

llm = OpenAI(model="gpt-4")
prompt = PromptTemplate(input_variables=["question"], template="Answer this: {question}")
chain = LLMChain(llm=llm, prompt=prompt)
result = chain.run("What is the capital of France?")
print(result)  # Output: The capital of France is Paris.
```

**Key Points**:
- Use `LangChain Expression Language (LCEL)` for advanced chaining:
  ```python
  from langchain.prompts import PromptTemplate
  from langchain.llms import OpenAI

  prompt = PromptTemplate.from_template("Translate {text} to French")
  llm = OpenAI(model="gpt-4")
  chain = prompt | llm
  result = chain.invoke({"text": "Hello, world!"})  # Output: Bonjour le monde !
  ```

### 2. Agents: Decision-Making Pipelines
Agents use LLMs to decide actions, often calling external tools dynamically.

**Example**: An agent with a calculator tool.
```python
from langchain.agents import initialize_agent, Tool
from langchain.llms import OpenAI

def calculator(query: str) -> str:
    return str(eval(query))  # Simplified for example

llm = OpenAI(model="gpt-4")
tools = [Tool(name="Calculator", func=calculator, description="Perform math calculations")]
agent = initialize_agent(tools, llm, agent_type="react")
result = agent.run("What is 5 + 3 * 2?")
print(result)  # Output: 11
```

**Key Points**:
- Agents support frameworks like ReAct (Reasoning + Acting).
- Use LangSmith to trace agent decisions.

### 3. Memory: Contextual Persistence
Memory retains conversation history for coherent interactions.

**Example**: A chatbot with conversation memory.
```python
from langchain.chains import ConversationChain
from langchain.memory import ConversationBufferMemory
from langchain.llms import OpenAI

llm = OpenAI(model="gpt-4")
memory = ConversationBufferMemory()
chain = ConversationChain(llm=llm, memory=memory)
chain.run("Hi, I'm Alice.")
chain.run("What's my name?")  # Output: Your name is Alice.
```

**Key Points**:
- Use `ConversationSummaryMemory` for summarizing long conversations.
- Store long-term memory in vector stores like FAISS.

### 4. Tools: External Integrations
Tools extend LLM capabilities by connecting to APIs, databases, or functions.

**Example**: A search tool integrated with an agent.
```python
from langchain.tools import Tool
from langchain.agents import initialize_agent
from langchain.llms import OpenAI

def search(query: str) -> str:
    return f"Searching for {query}"  # Mock search function

llm = OpenAI(model="gpt-4")
tools = [Tool(name="Search", func=search, description="Search the web")]
agent = initialize_agent(tools, llm, agent_type="react")
result = agent.run("Find the latest AI news.")
print(result)
```

**Key Points**:
- Prebuilt toolkits: Zapier, Wolfram Alpha, SQL.
- Secure tools with input validation.

### 5. Retrieval-Augmented Generation (RAG)
RAG combines LLMs with external knowledge retrieval for grounded responses.

**Example**: A simple RAG pipeline with FAISS.
```python
from langchain.llms import OpenAI
from langchain.vectorstores import FAISS
from langchain.embeddings import OpenAIEmbeddings
from langchain.chains import RetrievalQA
from langchain.schema import Document

# Sample documents
docs = [Document(page_content="The capital of France is Paris.", metadata={})]
embeddings = OpenAIEmbeddings()
vector_store = FAISS.from_documents(docs, embeddings)

# Create RAG chain
llm = OpenAI(model="gpt-4")
retriever = vector_store.as_retriever()
qa_chain = RetrievalQA.from_chain_type(llm, chain_type="stuff", retriever=retriever)
result = qa_chain.run("What is the capital of France?")
print(result)  # Output: The capital of France is Paris.
```

**Key Points**:
- Use metadata filters for precise retrieval.
- Optimize with contextual compression.

### 6. LangChain Expression Language (LCEL)
LCEL simplifies complex workflows with a functional syntax.

**Example**: Chaining a prompt and LLM with LCEL.
```python
from langchain.prompts import PromptTemplate
from langchain.llms import OpenAI

prompt = PromptTemplate.from_template("Summarize this: {text}")
llm = OpenAI(model="gpt-4")
chain = prompt | llm
result = chain.invoke({"text": "LangChain is a framework for building LLM apps."})
print(result)  # Output: LangChain is a framework for developing applications with large language models.
```

**Key Points**:
- Supports async, streaming, and parallel execution.
- Easy to debug and extend.

### 7. LangSmith: Observability
LangSmith provides tracing and monitoring for LangChain apps.

**Setup**:
1. Sign up at [LangSmith](https://smith.langchain.com).
2. Set environment variables:
   ```env
   LANGSMITH_API_KEY=your-langsmith-api-key
   LANGCHAIN_TRACING_V2=true
   ```
3. Run any LangChain app to log traces.

**Key Points**:
- Visualize chain/agent execution.
- A/B test prompts and models.

## Hands-On Exercises
1. **Build a Q&A Chain**: Create a chain that answers questions using a custom prompt.
2. **Develop an Agent**: Build an agent with a calculator and search tool.
3. **Implement RAG**: Set up a RAG system with FAISS and sample documents.
4. **Add Memory**: Extend the chatbot example to summarize conversation history.

## Additional Resources
- [LangChain Documentation](https://python.langchain.com/docs)
- [LangSmith](https://smith.langchain.com) for observability
- [LangChain GitHub](https://github.com/langchain-ai/langchain)
- [Hugging Face](https://huggingface.co) for open-source models
- [xAI API](https://x.ai/api) for Grok 3 integration

## Notes
- Replace `OpenAI` with open-source models (e.g., Hugging Face’s `transformers`) for cost-effective setups.
- Ensure API keys are stored securely in `.env` files.
- For production, use LangServe to deploy chains as APIs.

Happy coding, and enjoy mastering LangChain!
