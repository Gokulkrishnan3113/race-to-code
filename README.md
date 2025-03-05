# Setup Guide for Windows

## 1. Check Python Version
Before proceeding, check if Python is already installed and verify its version.

### **Command Prompt (cmd) or PowerShell**
```sh
python --version
```

If the output shows Python **3.8.x, 3.9.x, or 3.10.x**, you can proceed. If not, follow the next step to install the correct version.

---
## 2. Install Python (If Not Installed or Wrong Version)
1. Go to the [official Python website](https://www.python.org/downloads/).
2. Download and install **Python 3.10.x** (since `rajinipp` requires **>=3.8, <3.11**).
3. During installation, check **"Add Python to PATH"**.

After installation, verify by running:
```sh
python --version
```

---
## 3. Install `pyenv`
To manage different Python versions, install `pyenv`.

1. Open PowerShell as Administrator and run:
```sh
git clone https://github.com/pyenv-win/pyenv-win.git "$HOME\.pyenv"
```

2. Add `pyenv` to the system environment variables by running:
```sh
[System.Environment]::SetEnvironmentVariable("Path", $env:Path + ";$HOME\.pyenv\pyenv-win\bin;$HOME\.pyenv\pyenv-win\shims", [System.EnvironmentVariableTarget]::User)
```

3. Restart the terminal and verify the installation:
```sh
pyenv --version
```

---
## 4. Install Python 3.10.12 Using `pyenv`
```sh
pyenv install 3.10.11
pyenv local 3.10.11
```

Verify the installation:
```sh
python --version
```

---
## 5. Create a Virtual Environment
```sh
python -m venv venv
```

### **Activate the Virtual Environment**
#### **Command Prompt**
```sh
venv\Scripts\activate
```
#### **PowerShell**
```sh
venv\Scripts\Activate.ps1
```
After activation, your terminal will show `(venv)` at the beginning of the line.

---
## 6. Install `rajinipp`
With the virtual environment activated, install `rajinipp`:
```sh
pip install rajinipp pyyaml
```

Verify the installation:
```sh
pip show rajinipp
```

---
## 7. Upgrade `pip`
Only If `pip` fails or is outdated, run:
```sh
curl -sS https://bootstrap.pypa.io/get-pip.py | python
pip install --upgrade pip setuptools wheel --trusted-host pypi.org --trusted-host pypi.python.org --trusted-host files.pythonhosted.org
```
then try installing again
```sh
pip install rajinipp pyyaml
```

---

## 8. Deactivating the Virtual Environment (Optional)
If you want to exit the virtual environment, simply run:
```sh
deactivate
```

---

## 9. Execution
Refer the execute.md file to exectute your code

---

## 10. Additional Notes
- Always activate the virtual environment before running scripts.
- If you encounter issues with `pip`, upgrade it using the steps above.
- If `rajinipp` installation fails, check if you are using a compatible Python version (`>=3.8, <3.11`).





# Setup Guide for rajinipp (macOS Only)

## 1. Check Python Version
Before proceeding, check if you already have Python installed and verify its version.

```sh
python --version
```

If the output shows Python **3.8.x, 3.9.x, or 3.10.x**, you can proceed. If not, follow the next step to install the correct version.

---
## 2. Install Python 3.10
If Python is not installed or the version is incorrect, install Python 3.10 using Homebrew:

```sh
brew install python@3.10
```

Then, update your shell configuration:
```sh
echo 'export PATH="/opt/homebrew/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

---
## 3. Install and Configure `pyenv`
Install `pyenv` to manage multiple Python versions:

```sh
curl https://pyenv.run | bash
```

Add `pyenv` to your shell configuration:
```sh
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
echo 'eval "$(pyenv init --path)"' >> ~/.zshrc
source ~/.zshrc
```

---
## 4. Install Python 3.10.12 with `pyenv`
Once `pyenv` is installed, install Python 3.10.12:
```sh
pyenv install 3.10.12
pyenv local 3.10.12
```

Verify the installed version:
```sh
python --version
```

---
## 5. Create and Activate a Virtual Environment
Create a virtual environment:
```sh
python -m venv venv
```

Activate the virtual environment:
```sh
source venv/bin/activate
```

After activation, your terminal will show `(venv)` at the beginning of the line.

---
## 6. Upgrade `pip`
If `pip` installation fails, use the following commands to install and upgrade `pip`:

```sh
curl -sS https://bootstrap.pypa.io/get-pip.py | python
pip install --upgrade pip setuptools wheel --trusted-host pypi.org --trusted-host pypi.python.org --trusted-host files.pythonhosted.org
```

---
## 7. Install `rajinipp`
With the virtual environment activated, install `rajinipp`:
```sh
pip install rajinipp
```

Verify the installation:
```sh
pip show rajinipp
```

---

## 8. Execution
Refer the execute.md file to exectute your code

---

## 9. Additional Notes
- Always activate the virtual environment before running scripts.
- If `rajinipp` installation fails, check if you are using a compatible Python version (`>=3.8, <3.11`).
- To exit the virtual environment, simply run:
  ```sh
  deactivate
  ```

