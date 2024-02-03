# Demo Ollama

## What is ollama?
>Ollama is a tool that allows you to run open-source large language models (LLMs) locally on your machine.

>Ollama supports a variety of models, including Llama 2, Code Llama, and others, and it bundles model weights, configuration, and data into a single package, defined by a Modelfile.

>Ollama also supports the creation and use of custom models. You can create a model using a Modelfile, which includes passing the model file, creating various layers, writing the weights, and finally, seeing a success message.

---
## Run locally
### 1. Start the container: 
    docker-compose up -d
### 2. Stat a bash shell session:
    docker exec -it ollama bash
### 3. Run mistral: 
    ollama run mistral
---
## References
- https://github.com/ollama/ollama