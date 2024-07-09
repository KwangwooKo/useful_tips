# useful_tips : This is the collection of self-study for AI

1. How to use api_key of llama-70b using Groq
(reference: AI Unleashed)

https://www.youtube.com/watch?v=VmNhDUKMHd4&t=36s


## Example

### 1. llama3_70b_groq.py
```
from groq import Groq # type: ignore
from dotenv import load_dotenv
import os

# Load environment variables from .env file
load_dotenv()

# Fetching the API key from the environment variable
api_key = os.environ.get("GROQ_API_KEY")

client = Groq(api_key=api_key)

completion = client.chat.completions.create(
    model="llama3-8b-8192",
    messages=[
        {
            "role": "user",
            "content": "Explain the process of clinical trials with an example"
        }
    ],
    temperature=1,
    max_tokens=1024,
    top_p=1,
    stream=True,
    stop=None,
)

for chunk in completion:
    print(chunk.choices[0].delta.content or "", end="")
```

### 2. .env
```
GROQ_API_KEY=
```

groq.com -> groq cloud -> API Key


2. How to install open WebUI (Ollama UI)
(reference: Matthew Berman)

https://www.youtube.com/watch?v=w4ERVqyMNcI&t=15s

