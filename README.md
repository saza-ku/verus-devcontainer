# Verus Devcontainer

This repository contains settings for a devcontainer which is set up to use [Verus](https://github.com/verus-lang/verus/).

## Usage

### Method 1: Clone and open with Devcontainer

```bash
git clone https://github.com/saza-ku/verus-devcontainer.git
cd verus-devcontainer
code .
# In VS Code, open the Command Palette and select "Remote-Containers: Reopen in Container"
```

### Method 2: Use pre-built Devcontainer image

1. Create a `.devcontainer` folder and add a `devcontainer.json` file:

```json
{
    "name": "Verus Devcontainer",
    "image": "ghcr.io/saza-ku/verus-devcontainer:latest",
    "customizations": {
        "vscode": {
            "extensions": [
                "verus-lang.verus-analyzer"
            ]
        }
    }
}
```

2. Open the project in VS Code and select **Remote-Containers: Reopen in Container** from the Command Palette.

You can check the available versions of the image in the [GitHub Container Registry](https://github.com/saza-ku/verus-devcontainer/pkgs/container/verus-devcontainer).
