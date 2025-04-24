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

```
 curl -fsSL https://nvidia.github.io/libnvidia-container/gpgkey | sudo gpg --dearmor -o /usr/share/keyrings/nvidia-container-toolkit-keyring.gpg && curl -s -L https://nvidia.github.io/libnvidia-container/stable/deb/nvidia-container-toolkit.list | sed 's#deb https://#deb [signed-by=/usr/share/keyrings/nvidia-container-toolkit-keyring.gpg] https://#g' | sudo tee /etc/apt/sources.list.d/nvidia-container-toolkit.list
 sudo apt-get update
 sudo apt-get install -y nvidia-container-toolkit
 sudo nvidia-ctk runtime configure --runtime=docker
 sudo systemctl restart docker
```


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