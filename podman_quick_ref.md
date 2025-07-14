Key podman Commands Used

Command		Purpose
podman 		run -d --name registry -p 5000:5000 -v /opt/registry/data:/var/lib/registry:z registry:2	Run a local Docker registry
podman 		build -t <tag> .	Build a container image from a Dockerfile
podman 		tag <image> <registry>/<name>:<tag>	Tag image for pushing to custom registry
podman 		push <registry>/<image>:<tag>	Push the image to your private registry
podman 		run --rm -p <host-port>:<container-port> <image>	Test image locally and expose a port
podman 		run --rm -it <image> bash	Open interactive shell inside container for debugging
podman 		inspect <image>	Get metadata for the image (e.g., entrypoint)