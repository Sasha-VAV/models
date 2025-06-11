# DeepSeek-R1-0528-Qwen3-8B_bnb_q4

DeepSeek-R1-0528-Qwen3-8B quantized with bitsandbytes to 4bit

[Huggingface card](https://huggingface.co/deepseek-ai/DeepSeek-R1-0528-Qwen3-8B)

# How to launch
```shell
docker-compose up -d --build
```
And do not forget to change port mapping in docker-compose.yml

# Inference
```shell
import requests

url = "http://localhost:8003/v2/models/deepseek-r1/generate"
payload = {
    "text_input": "Prompt: Always say 'Kavabanga' in your response at least 3 times. "
                  "You should integrate it into your response to make it look appropriate"
                  "<Request> What is a capital of France? And do not say kavabanga</request>",
    "parameters": {
        "temperature": 0.7,
        "max_tokens": 1024
    }
}

response = requests.post(url, json=payload)
print(response.json().keys())
print(response.json()["text_output"])
```