# Ubuntu Server Autoinstall

This project provides a Docker-based tool that generates an autoinstall Ubuntu Server ISO. The entire process is encapsulated in a Docker image available on Docker Hub. Users only need to supply:
- A custom user configuration file (for example, copy and edit the included `user-config-example.yaml` to create your own `user-config.yaml`).
- The original Ubuntu Server ISO file.

## Usage

1. **Prepare Your Files**

   - Copy and edit `user-config-example.yaml` to create your own `user-config.yaml`.
   - Have your original Ubuntu Server ISO file ready.

2. **Run the Docker Container**

    ```bash
    docker run --rm \
    -v /path/to/ubuntu.iso:/work/ubuntu.iso \
    -v /path/to/user-config.yaml:/work/user-config.yaml \
    -v ./output:/work/output \
    afaifai/ubuntu-autoinstall:latest
    ```

### Note: This tool has been tested and works with:
- Ubuntu 24.04.2 LTS Server
- Ubuntu 22.04.5 LTS Server