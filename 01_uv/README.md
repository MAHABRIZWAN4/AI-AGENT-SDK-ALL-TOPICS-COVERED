
# UV - Package  Manager : 

**UV** is a fast and modern Python package manager for installing and managing dependencies.

First install ``uv`` in system to folloe this steps:

``uv`` Install Karne ka Tarika :

🔹 If you have Python and pip installed:
Install uv via pipx (safe method):

```bash
pip install pipx
pipx ensurepath
pipx install uv
```

🔸 After this, restart your terminal (CMD or PowerShell), then try:

```bash
uv --version
```

Second Initialized ``uv`` in your project : 

```
uv init project_name
cd project_name
```

Third we acivate our virtual environment : 

```
uv venv
.venv\Scripts\activate
```

Then we add our required dependencies : 

```
uv add openai-agents python-dotenv
uv add chainlit
```



