# Deploy OpenWebUI, Ollama, and Chroma Containers to a Docker Swarm

Wrote this repo out of my own research and frustrations in simplifying this process

## How to use:

Personally, I would tweak the docker-stack file to map the volumes to desired directories or proper docker volumes, and also utilize ENV variables inside a pipeline of sorts.

```
docker stack deploy -c docker-stack.yml -d super-awesome-ai

```

## Special Heads up:
If using as is, you will need to do the following:

1. Enable Docker GPU support in order to utilize the Ollama container as is. To do this, see [Nvidia Container Toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html " on Nvidia's site.") 

2. You need to ensure CUDA is Enabled, follow your OS and GPU instructions for that.

Otherwise, you should follow OpenWebUI's guide [here and use it with a CPU instead of GPU](https://docs.openwebui.com/getting-started/#installing-open-webui-with-bundled-ollama-support )



### Links:
- [OpenWebUI Github](https://github.com/open-webui/open-webui "User-friendly AI Interface for Ollama.").
- [ChromaDB Github](https://github.com/chroma-core/chroma "the AI-native open-source embedding database.").
- [Ollama Github](https://github.com/chroma-core/chroma "Get up and running with large language models.")


## Feel free to reach out, if any questions!

[!["Buy Me A Coffee"](https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png)](https://https://buymeacoffee.com/dompolizzi)