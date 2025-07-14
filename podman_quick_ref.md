## 🔧 Key Podman Commands Used

| Command | Purpose |
|--------|---------|
| `podman run -d --name registry -p 5000:5000 -v /opt/registry/data:/var/lib/registry:z registry:2` | Run a local Docker-compatible container registry |
| `podman build -t <image-name> .` | Build a container image from a Dockerfile |
| `podman tag <image-id-or-name> <custom-registry>/<image-name>:<tag>` | Tag an image for pushing to a custom registry |
| `podman push <custom-registry>/<image-name>:<tag>` | Push the image to your private registry |
| `podman run --rm -p <host-port>:<container-port> <image-name>` | Test image locally and expose a port |
| `podman run --rm -it <image-name> bash` | Open an interactive shell inside the container for debugging |
| `podman inspect <image-id-or-name>` | Get metadata about the image (e.g., entrypoint, env variables) |
