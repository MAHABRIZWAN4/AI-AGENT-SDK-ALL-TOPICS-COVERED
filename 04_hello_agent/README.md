# FIRST AI-AGENT

### Step 1 : Initialized UV in your project

```bash
uv init hello_agent
cd hello_agent
```

Create & acivate our virtual environment : 

```bash
uv venv
.venv\Scripts\activate
```

Then we add our required dependencies : 

```bash
uv add openai-agents python-dotenv
```

### STEP 2 : ``.env`` ke under GEMINI_API_KEY rakhein ge.

Make a file `.env` in your project.

```python
GEMINI_API_KEY = "your_gemini_api_key"
```

### Step 3 : Make a file ``main.py`` & us me apni GEMINI_API_KEY ko get karein ge:

```python
def main():
MODEL_NAME = "gemini-2.0-flash"
```

GEMINI_API_KEY laane ke liye uper **UV** ka package add kiya ``uv add dotenv`` abb load karein env load karein ge: 

```python
from dotenv import load_dotenv
load_dotenv() # ye karein ge load func call 
```

abb hamari env os me hoti he to  os import karein ge :

```python
import os
Then env se GEMINI_API_KEY get karein ge aise
GEMINI_API_KEY = os.getenv("GEMINI_API_KEY")
```

### Step 4 : External Client

Abb hum external client banyein ge jis ke liye AsyncAI package ka use karein ge or wo hamein agents SDK provide kerta he.

Ye jo hamara Lite LLM wala part hai us ko hum ne AsynopenAI(AsyncopenAI ka jo client hai external client ) se replace kiya  abb us ke through hum pura agent ko banayein ge.

```python

from agents import AsyncOpenAI

exteral_client = AsyncOpenAI(
    # Is ke under 2 Parameters aayein ge api_key And base_url 
    api_key=GEMINI_API_KEY,
    base_url="https://generativelanguage.googleapis.com/v1beta/openai/", 
    # ye url jo hum AsynOpenAI ke through hum jo client bana rahe hein wo use kare ga.. hum ye url is liye use ker rahe ke pata chle ke hum gemini use ker rahe hein 
)

```

### Step 5 : Create Model

```python

from agents import OpenAIChatCompletionsModel

model = OpenAIChatCompletionsModel(
    model=MODEL_NAME,
    openai_client=external_client
)

```

- OpenAIChatCompletionsModel ka use kiya gaya hai kyunki yeh AI model hai jo human-like text generate kar sakta hai, aur ismein Gemini 2.0 Flash model ka istemal kiya gaya hai jo fast aur efficient hai.

- Short mein: OAI-CCM use AI chat ke liye.

### Step 6 : To Remove this error : 

#### OPENAI_API_KEY is not set, skipping trace export
    
config  = RunConfig(
    model = model,
    model_provider=external_client,
    tracing_disabled=True
)

### Step 7 : How to make an Agent

```python
Assistant = Agent( # ye class hai
    name = "Assistant",  # is ko parameter bolte hein
    instructions = "You job is to assist the user with their queries. You are a helpful assistant.",
    model=model,
    )
```

### Step 8 : Abb is agent ko run karein ge With the help of Runner

```python
from agents import Runner

user_input = input("Enter your query: ")  

result = Runner.run_sync(assistant,user_input,run_config=config)

print(result.final_output)

  
if __name__ == "__main__":
    main() 

```

## ---------------------------THE END---------------------------

## Convert this Synchronous_Agent to Asynchronous_Agent 

Agar Multiple Agents ko chalana hoto synchronous work nahi karein ge Asynchronous kerna pare ga :

### STEP 1 

```python
import asyncio
```

### STEP 2

```python
result = await Runner.run(assistant,user_input, run_config=config)
```

### STEP 3

```python
asyncio.run(main()) 
```

## ---------------------------THE END---------------------------








