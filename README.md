# Deploy OpenWebUI, Ollama, and Chroma Containers to a Docker Swarm

Wrote this repo out of my own research and frustrations in simplifying this process

## How to use:

Personally, I would tweak the docker-stack file to map the volumes to desired directories or proper docker volumes, and also utilize ENV variables inside a pipeline of sorts.

```
docker stack deploy -c docker-stack.yml -d super-awesome-ai

```

### Installing Open WebUI with Ollama, and ChromaDB to a Docker Swarm

This installation method utilizes a stack file to deploy 3 seperate containers as services in a Docker Swarm. It includes Chroma, Ollama, and of course OpenWebUI for a streamlined setup via a single command. Along with this, there are pre-filled `Environment` variables based on popular  deployment choices. Choose the appropriate command based on your hardware setup:


- **With GPU Support**:
  Utilize the `docker-stack.yaml` file as is
  
  ```bash
  docker stack deploy -c docker-stack.yaml -d super-awesome-ai
  ```

- **With CPU Support**:
  Modify the `docker-stack.yaml` file and remove the following lines `70-76`, then deploy with the above snippet

- **Additionally**:
  1. Enable Docker GPU support to utilize the Ollama container as is. To do this, see [Nvidia Container Toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html " on Nvidia's site.") 

  2. You need to ensure CUDA is Enabled, follow your OS and GPU instructions for that.

  3. Add: `"NVIDIA-GPU=GPU-<YOUR_GPU_NUMBER>"` in the file `/etc/docker/daemon.json`, follow the [Guide here on configuring Docker Swarm to with with your GPU](https://gist.github.com/tomlankhorst/33da3c4b9edbde5c83fc1244f010815c#configuring-docker-to-work-with-your-gpus)

  4. You need to ensure GPU Resource is enabled in the Docker `config.toml`. You can enable GPU resource advertising by uncommenting the `swarm-resource = "DOCKER_RESOURCE_GPU"` line (line 2) in `/etc/nvidia-container-runtime/config.toml` . The docker daemon must be restarted after updating these files by running `sudo service docker restart` on each node. (May require entire restart)



### Links:
- [OpenWebUI Github](https://github.com/open-webui/open-webui "User-friendly AI Interface for Ollama.").
- [ChromaDB Github](https://github.com/chroma-core/chroma "the AI-native open-source embedding database.").
- [Ollama Github](https://github.com/chroma-core/chroma "Get up and running with large language models.")


## Feel free to reach out, if any questions!

[!["Buy Me A Coffee"](https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png)](https://https://buymeacoffee.com/dompolizzi)