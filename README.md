## Design and Implementation of LangChain Expression Language (LCEL) Expressions

### AIM:
To design and implement a LangChain Expression Language (LCEL) expression that utilizes at least two prompt parameters and three key components (prompt, model, and output parser), and to evaluate its functionality by analyzing relevant examples of its application in real-world scenarios.

### PROBLEM STATEMENT:
To create a versatile tool for an e-commerce platform that can automatically generate engaging and concise marketing descriptions for new products. The tool must take the product's name and a list of its key features as input and produce a ready-to-use description as a simple string output.

### DESIGN STEPS:

#### STEP 1:
 Design a Multi-Parameter Prompt Template

#### STEP 2:
Select the Core Components (Model and Parser). Here, my model is ChatOpenAI() and parser is StrOutputParser()

#### STEP 3:
Construct the LCEL Chain using pipeline (|) where this would connect the components together which are (prompt| model | output parser) 

### PROGRAM:
```
import os
import openai

from dotenv import load_dotenv, find_dotenv
_ = load_dotenv(find_dotenv()) # read local .env file
openai.api_key = os.environ['OPENAI_API_KEY']

from langchain.prompts import ChatPromptTemplate
from langchain.chat_models import ChatOpenAI
from langchain.schema.output_parser import StrOutputParser

prompt = ChatPromptTemplate.from_template(
   "Tell me about {topic} in the style of {style}"
)
model = ChatOpenAI()
output_parser = StrOutputParser()
model = ChatOpenAI()
output_parser = StrOutputParser()

chain = prompt | model | output_parser

chain.invoke({ "topic": "the moon",
    "style": "a short poem"})
```

### OUTPUT:
<img width="1250" height="112" alt="image" src="https://github.com/user-attachments/assets/9c2d5603-64f0-4532-8d90-c7410954fb23" />


### RESULT:
The LangChain Expression Language (LCEL) chain was successfully designed and implemented. The program effectively utilized a ChatPromptTemplate with two parameters (topic and style), a ChatOpenAI model, and a StrOutputParser. 
