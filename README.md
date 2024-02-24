# How to access LLMs? 

*Space for a cool header*

## Completion Models

For BCX'24 Bosch Digital_ provides access to these completion models: 

| **OpenAI** | **Llama 2** | **Mistral.ai** |
|------------|-------------|----------------|
| gpt-3.5    | Llama-7b    | Mistral-7b     | 
| gpt-4      | Llama-70b   |                |  


 *All models are provided as chat/instruct finetuned variant. For OpenAIs Quota Limites apply.* 

To access these models via *python*:

```
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
```

## Embedding Models
... are provided via OpenAI's *text-embedding-3-small*. How to embedd you input via *python*:

```

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

```

## 🚨 You need more? 

>  Function Calling, Whisper, Vision, custom GPU power for fine tuning or more credits needed —> hit us up :)  
