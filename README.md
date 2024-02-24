# BD_LLM_Access

** Completion **

We provide the following models:

| **OpenAI** | **Llama 2** | **Mistral.ai** |
|------------|-------------|----------------|
| gpt-3.5    | Llama-7b    | Mistral-7b     | 
| gpt-4      | Llama-70b   |                |  

* All models are provided in as chat/instruct finetuned variant.

Access these models via python:

```
{
import requests
import json

url = "https://llms.azurewebsites.net/chat/completions"

payload = json.dumps({
  "model": "MODEL_NAME (SEE TABLE)",
  "temperature": 0.5,
  "messages": [
    {
      "role": "user",
      "content": "YOUR_PROMPT"
    }
  ]
})
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Bearer YOUR_API_KEY'
}

response = requests.request("POST", url, headers=headers, data=payload)

print(response.text)
}
```

** Embedding **
Via OpenAI's text-embedding-3-small

```
{

import requests
import json

url = "https://llms.azurewebsites.net/embeddings"

payload = json.dumps({
  "model": "text-embedding-3-small",
  "input": "YOUR_TEXT_TO_EMBEDD"
})
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Bearer YOUR_API_KEY'
}

response = requests.request("POST", url, headers=headers, data=payload)

print(response.text)


}
```

Function Calling, Whisper, Vision, custom GPU power for fine tuning or more credits needed —> hit us up :)  
