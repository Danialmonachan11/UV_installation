
#  UV Installation and Virtual Environment Setup


This guide helps with installing UV [click here to download](https://docs.astral.sh/uv/getting-started/installation/#pypi) and creating/managing Python virtual environments. It serves as a personal cheatsheet and a way to practice maintaining well-structured project notes.

## 1. Setting up the Working Directory

First, create and navigate to your project directory:

```bash
mkdir hello-world
cd hello-world
```

Initialize uv in your project. This will create necessary configuration files (like pyproject.toml if it doesn't exist):

```bash
uv init
```
*This command sets up your project to be managed by uv.*

# 2. Python Installation and Virtual Environment Management

## 2.1. Creating a Virtual Environment
To create a virtual environment in the current directory (typically in a .venv folder):
```bash
uv venv
```

## 2.2. Activating the Virtual Environment (Windows PowerShell)
To activate the newly created virtual environment in PowerShell:

*Note: You might need to adjust your execution policy to allow script execution. Use with caution and understand the implications.*

```bash
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
```

Then, activate the environment:
```bash
.\.venv\Scripts\Activate.ps1
```

For other shells (like bash or zsh), the activation script is typically
```bash
 .venv/bin/activate.
 ```

## 2.3. Installing a Specific Python Version (Optional)
If you need a specific version of Python that isn't your system default, uv can install it:
```bash
uv python install 3.13
 ```

## 2.4. Creating a Virtual Environment with a Specific Python Version
You can specify the Python version when creating the virtual environment:
```bash
uv venv --python 3.13
 ```

*This ensures the virtual environment uses Python 3.11, provided uv can find or install it.*

# 3. Managing Dependencies

1. Add Dependencies: Manually edit your pyproject.toml file to list the packages your project needs under the [project.dependencies] section. For example:
```bash
[project]
name = "hello-world"
version = "0.1.0"
dependencies = [
  "requests",
  "numpy>=1.20",
]
 ```
2. Install Dependencies: After updating pyproject.toml, synchronize your environment to install the specified packages:
```bash
uv sync
 ```

*This command installs the packages listed in pyproject.toml into your virtual environment. It will also create a uv.lock file. This lockfile is human-readable (TOML format) but is managed by uv and should not be edited manually.*

# 4. Reference
For more detailed information, refer to the official uv documentation:

[Official uv Documentation](https://docs.astral.sh/uv/ "Astral uv documentation site")
