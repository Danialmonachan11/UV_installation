# UV_installation

Helps you to Install UV and create VENV 

I use this as a self note and to create a practice of having a better project Structure.

## Working Directory
mkdir hello-world
cd hello-world
uv init

This will create some Files for the Working Directory


## Installation Python(If needed) and Venv

Creating Venv
uv venv

*sometimes to activate the venv you have to bypass the execution policy to activate the venv*
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
then:
 .\.venv\Scripts\Activate.ps1

*If you need the specific installation*
uv python install 3.13  
*A Python version can be requested, e.g., to create a virtual environment with Python 3.13*
uv venv --python 3.11

Modify TOML file to add and dependencies.

Finally do
uv sync

it should create uv.lock file which is a human-readable TOML file but is managed by uv and should not be edited manually.


##Reference
*https://docs.astral.sh/uv/*

