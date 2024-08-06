# my-ollama
Run ollama with docker compose


## Clone repository and Run
```
start.sh
```

## Install model (only in first run)

### Enter in docker container
```
shell.sh
```

### Run in container
```
ollama pull llama3
ollama pull all-minilm
```


## If you want use Nvidia GPU with Ubuntu in 2 steps

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
 curl -fsSL https://nvidia.github.io/libnvidia-container/gpgkey | sudo gpg --dearmor -o /usr/share/keyrings/nvidia-container-toolkit-keyring.gpg \\n  && curl -s -L https://nvidia.github.io/libnvidia-container/stable/deb/nvidia-container-toolkit.list | \\n    sed 's#deb https://#deb [signed-by=/usr/share/keyrings/nvidia-container-toolkit-keyring.gpg] https://#g' | \\n    sudo tee /etc/apt/sources.list.d/nvidia-container-toolkit.list
 sudo apt-get update
 sudo apt-get install -y nvidia-container-toolkit
 sudo nvidia-ctk runtime configure --runtime=docker
 sudo systemctl restart docker
```



## Inspired by 

Code to bring up Ollama using Docker (on GPU - Optionally)

Refer the blog for more details - [https://medium.com/@srpillai/how-to-run-ollama-locally-on-gpu-with-docker-a1ebabe451e0](https://medium.com/@srpillai/how-to-run-ollama-locally-on-gpu-with-docker-a1ebabe451e0)
## References

* [https://ollama.com/](https://ollama.com/)
* [https://github.com/ollama/ollama](https://github.com/ollama/ollama)
* [https://streamlit.io/](https://streamlit.io/)
* [https://docs.docker.com/desktop/gpu/](https://docs.docker.com/desktop/gpu/)