# my-ollama
Run ollama with docker compose


## Installation

### Clone repository and Run
```
./cmd.sh up
```

### Install model 

#### Enter in docker container
```
./cmd.sh shell
```

#### Run in container
```
ollama pull llama3
ollama pull all-minilm
ollama pull llama3.2:3b
ollama pull deepseek-r1:7b
ollama pull qwen3
ollama pull cas/llama-3.2-1b-instruct:latest
```

# Bien pour la domaotique et petite machine ?
```
ollama pull gemma3n  # Gemma 3n models are designed for efficient execution on everyday devices such as laptops, tablets or phones. 
ollama pull gemma:2b 
ollama run phi3:mini
ollama run phi3
```


# A tester 

| Modèle              | Taille / paramètres  | Ressources approx.                               | Commande `pull`              |
| ------------------- | -------------------- | ------------------------------------------------ | ---------------------------- |
| Mistral (7B)        | bon compromis        | ~4 GB+ de RAM GPU selon version                  | `ollama pull mistral:7b`     |
| Llama 2 (7B)        | bon compromis        | ~3-5 GB RAM/VRAM selon quantisation              | `ollama pull llama2:7b-chat` |
| Gemma 3 (4B)        | modéré               | ~3.3 GB pour 4B version selon doc. ([GitHub][1]) | `ollama pull gemma3:4b`      |

[1]: https://github.com/ollama/ollama?utm_source=chatgpt.com "ollama/ollama: Get up and running with OpenAI gpt-oss ... - GitHub"



### If you want use Nvidia GPU with Ubuntu in 2 steps

1. Uncomment in docker compose :

```
    deploy:
      resources:
        reservations:
          devices:
            - driver: nvidia
              count: all
              capabilities: [gpu]
```

2. Install `nvidia-container-toolkit`

https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html


## Run & Use

```
./cmd.sh up
```

UI : http://localhost:3000

API : http://localhost:11434


## Inspired by 

Code to bring up Ollama using Docker (on GPU - Optionally)

Refer the blog for more details - [https://medium.com/@srpillai/how-to-run-ollama-locally-on-gpu-with-docker-a1ebabe451e0](https://medium.com/@srpillai/how-to-run-ollama-locally-on-gpu-with-docker-a1ebabe451e0)
## References

* [https://ollama.com/](https://ollama.com/)
* [https://github.com/ollama/ollama](https://github.com/ollama/ollama)
* [https://streamlit.io/](https://streamlit.io/)
* [https://docs.docker.com/desktop/gpu/](https://docs.docker.com/desktop/gpu/)