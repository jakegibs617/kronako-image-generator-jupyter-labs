
## Prerequistes:
- Python 3.11.6
- pyenv 2.5.0

zshrc
```
export PATH="/opt/homebrew/bin:$PATH"

# Alias Python to always use pyenv's selected Python version
alias python="$(pyenv which python)"

# Automatically activate the virtual environment for the flux-text2img project
function cd() {
  builtin cd "$@" || return
  # Check if current directory is the project directory
  if [[ $(pwd) == "/Users/jacobgiberson/Desktop/AI-projects/flux-text2img" ]]; then
    # Initialize pyenv
    eval "$(pyenv init -)"
    eval "$(pyenv init --path)"
    # Activate the virtual environment
    if [[ -f "venv/bin/activate" ]]; then
      source "venv/bin/activate"
    fi
  fi
}

# Ensure Jupyter finds the correct Python version and path
export JUPYTER_PATH="$(pyenv which python)"

# Add pyenv's shims to PATH for Jupyter compatibility
export PATH="$(pyenv root)/shims:$PATH"

export HUGGINGFACE_HUB_TOKEN="hf_..."
```

notebooks/sketch-generator.ipynb


(deactivate the current virtual env)
deactivate

(activate virtual env)
source {path to dir}/flux-text2img/venv/bin/activate

(run project)
jupyter lab

## Running Cells

| Shortcut                                | Action                                                   | Mode Needed     |
|-----------------------------------------|----------------------------------------------------------|-----------------|
| **Shift + Enter**                       | Run the current cell, then select the next cell         | Edit or Command |

---

## Managing Cells (Command Mode)

When in **Command mode** (press **Esc** to ensure you’re in Command mode), you can:

| Shortcut              | Action                                                   |
|-----------------------|----------------------------------------------------------|
| **A**                 | Insert a cell **Above** the current cell                |
| **B**                 | Insert a cell **Below** the current cell                |
| **M**                 | Change the current cell to **Markdown**                  |
| **Y**                 | Change the current cell to **Code**                      |
| **X**                 | Cut the selected cell                                   |

---

## Kernel Operations

| Shortcut                 | Action                                                           |
|--------------------------|------------------------------------------------------------------|
| **0, 0** (press 0 twice) | **Restart** the kernel (clears variables, restarts environment) |


## License

Copyright 2025 jgiberson. All Rights Reserved.

This software is proprietary and confidential. Unauthorized copying of this file, 
via any medium, is strictly prohibited. 
