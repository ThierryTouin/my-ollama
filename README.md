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
exit
```


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