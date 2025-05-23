# IIC OSIC Tools - Devcontainer Template

This repository provides a template to quickly set up a development environment for the [IIC OSIC Tools](https://github.com/iic-jku/iic-osic-tools) using VS Code Dev Containers.

It provides access to a pre-configured Docker container with common open-source EDA (Electronic Design Automation) tools.

## Prerequisites

*   [Docker Desktop](https://www.docker.com/products/docker-desktop/) or Docker Engine installed and running.
*   [Visual Studio Code](https://code.visualstudio.com/).
*   [Dev Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) installed in VS Code.

## How to Use

1.  **Clone this repository:**
    ```bash
    git clone [URL_OF_THIS_TEMPLATE_REPO] my-eda-project
    cd my-eda-project
    ```
2.  **Designs Directory:**
    A `designs/` directory is included in this template. This directory will be mounted into `/foss/designs` inside the dev container. Place your personal EDA design projects within this `designs/` folder on your host machine.
3.  **Open in VS Code:**
    Open the cloned `my-eda-project` folder in VS Code.
    ```bash
    code .
    ```
4.  **Reopen in Container:**
    VS Code should detect the `.devcontainer/devcontainer.json` file and prompt you with a message like: "Folder contains a Dev Container configuration file. Reopen folder to develop in a container."
    Click on **"Reopen in Container"**.

VS Code will now build (the first time) and start the dev container. Your terminal and workspace will be connected to this containerized environment.

## Included Tools & Access

The dev container comes with a suite of open-source EDA tools, including (but not limited to):
*   Magic, KLayout, xschem
*   Yosys, OpenSTA
*   Icarus Verilog, Verilator, GTKWave
*   ngspice
*   Python, Perl, Tcl

**Accessing Services:**

*   **Terminal:** New terminals opened in VS Code will start in the `/foss/designs` directory within the container.
*   **Web VNC (noVNC):**
    *   Access via: `http://localhost:8080/` (if host port 8080 is free).
    *   The VNC password is `abc123` (as set in `devcontainer.json`).
    *   If port 8080 is busy on your host, VS Code will forward to a different host port. Check the "Ports" tab in VS Code for the correct URL.
*   **Direct VNC Client:**
    *   Connect to: `localhost:5901` (if host port 5901 is free).
    *   Password: `abc123`.
    *   If port 5901 is busy on your host, VS Code will forward to a different host port. Check the "Ports" tab for the correct host port to use.
*   **X11 Forwarding:**
    *   If you have an X server (like XQuartz on macOS or an X server on Linux) running on your host and configured to accept network connections, GUI applications launched from the container terminal (e.g., `xschem`, `magic`) should display on your host.

## Customization

*   You can modify `.devcontainer/devcontainer.json` to change settings, install more VS Code extensions, or add more tools.
*   Place your design files in the `designs/` directory.

## License

This devcontainer template setup is provided under the Apache License 2.0. The tools included within the Docker image `hpretl/iic-osic-tools:latest` are subject to their own respective licenses. 