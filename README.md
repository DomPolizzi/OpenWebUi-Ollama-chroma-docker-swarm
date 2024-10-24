# Deploy OpenWebUI, with Docker and Chroma to a Docker Swarm


## How to use:
```
docker stack deploy -c docker-stack.yml -d super-awesome-ai

```

## Special Heads up:
If using as is, you will need to do the following:

1.You need to enable Docker GPU support in order to utilize the Ollama as is. to do this, see [Nvidia Container Toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html " on Nvidia's site.") 

2. You need to ensure CUDA is Enabled, follow your OS and GPU instructions for that.

Otherwise, you should follow the guid [here](https://docs.openwebui.com/getting-started/#installing-open-webui-with-bundled-ollama-support "and use it without a gpu!")



### Links:
[OpenWebUI](https://github.com/open-webui/open-webui "User-friendly AI Interface for Ollama.").
[ChromaDB](https://github.com/chroma-core/chroma "the AI-native open-source embedding database.").
[Ollama](https://github.com/chroma-core/chroma "Get up and running with large language models.")