# Docker Execution for pan-os-upgrade

The `pan-os-upgrade` tool can be conveniently run using Docker, offering a consistent and streamlined setup process across different systems. This guide will walk you through configuring and executing the tool within a Docker container.

## Pulling the Docker Image

If you haven't already done so, start off by pulling the `pan-os-upgrade` Docker image from GitHub Packages:

```bash
docker pull ghcr.io/cdot65/pan-os-upgrade:latest
```

## Setting Up the Docker Environment

Before executing the tool, ensure your Docker environment is correctly set up.

### Directory Setup

Create `assurance` and `logs` directories in your working directory to store outputs and logs:

```bash
mkdir assurance logs
```

### Running the Docker Container

Run `pan-os-upgrade` in Docker using the following commands:

#### On macOS and Linux

```bash
docker run -v $(pwd)/assurance:/app/assurance -v $(pwd)/logs:/app/logs -it ghcr.io/cdot65/pan-os-upgrade:latest
```

This mounts your host's `assurance` and `logs` directories to the container.

#### On Windows

```bash
docker run -v %CD%/assurance:/app/assurance -v %CD%/logs:/app/logs -it ghcr.io/cdot65/pan-os-upgrade:latest
```

## Interacting with the Docker Container

The container runs interactively, prompting you for details like IP address, username, password, and target PAN-OS version.

## Output and Logs

After running the container, you'll find all necessary outputs and logs in the `assurance` and `logs` directories on your host machine.

## Next Steps

With `pan-os-upgrade` successfully executed using Docker, check the outputs and logs for insights into the upgrade process. For further assistance or troubleshooting, refer to the [Troubleshooting Guide](troubleshooting.md).