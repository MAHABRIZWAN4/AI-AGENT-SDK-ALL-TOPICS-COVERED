
# LITELLM

liteLLM hum gemini ko connect ko ya kisi bhi LLM ko easily connect kerne ke liye use kerte hein.

# Make your jupiter Notebook in Colab we use LiteLLM in Colab Now: 

### Step 1 : Installation  

```python
!pip install -Uq openai-agents  "openai-agents[litellm]"
```

### Step 2: Working Related to Gemini

```python
MODEL_NAME = "gemini/gemini-2.0-flash"
```

***Mujhe gemini use kerne ke liye gemini api key chhaiye hogi.***

1.Go the secrets tab in google colab.       
2.Click Gemini Keys > Manage.       
3.Click on Create Api keys button.      
4.Then choose the name.     
5.copy the secret key.      
6.Again open the secrets on google colab.       
7.Click on ADD NEW SECRET then name and add secret key in it

### Step 3 : import gemini key in Notebook

```python
from google.colab import userdata 

API_KEY = userdata.get("GEMINI_API_KEY")
```

### Step 4 : How to make an agent

```python
from agents import Agent,Runner
from agents.extensions.models.litellm_model import LitellmModel
import asyncio
```

```python
Assistant = Agent( # ye class hai
    name = "Assistant",  # is ko parameter bolte hein
    instructions = "You are a helpful assistant.",
    model = LitellmModel(
        model = MODEL_NAME,
        api_key = API_KEY,
    ),
    # ye mene is is liye kiya taake mera LLM Model Gemini ka use kersake is liye LitellmModel ko import karein ge agar ye bhool gai import kerne  wali itni bari line to hum documentation me se dekh lein ge ## https://openai.github.io/openai-agents-python/models/litellm/
)
```

### Step 5 : Run this Agent

```python
async def main():
  result = await Runner.run(starting_agent = Assistant,input = "Hello, How are you?") # ye ek function hai is ke under 2 cheezein pass hongi
  print(result.final_output) # agar hamin llm ka agent ka final answer he wo chahyie to wo hamein final_output me mile ga

asyncio.run(main())
```


