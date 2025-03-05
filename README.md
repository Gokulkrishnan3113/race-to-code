# Setup Guide for rajinipp

## 1. Check Python Version
Before proceeding, check if you already have Python installed and verify its version.

### **Windows**
Open Command Prompt (cmd) or PowerShell and run:
```sh
python --version
```

### **macOS/Linux**
Open Terminal and run:
```sh
python3 --version
```

If the output shows Python **3.8.x, 3.9.x, or 3.10.x**, you can proceed. If not, follow the next step to install the correct version.

---
## 2. Install Python (If Not Installed or Wrong Version)

### **Windows**
1. Go to the [official Python website](https://www.python.org/downloads/).
2. Download and install **Python 3.10.x** (since `rajinipp` requires **>=3.8, <3.11**).
3. During installation, check **"Add Python to PATH"**.

### **macOS/Linux**
#### **Using Homebrew (Recommended for macOS)**
```sh
brew install python@3.10
```
To set it as default:
```sh
echo 'export PATH="/opt/homebrew/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

#### **Using `pyenv` (Recommended for version management)**
1. Install `pyenv` if not installed:
   ```sh
   curl https://pyenv.run | bash
   ```
2. Restart your terminal and install Python 3.10:
   ```sh
   pyenv install 3.10.12
   pyenv global 3.10.12
   ```

---
## 3. Create a Virtual Environment
Once you have Python 3.10 installed, create a virtual environment.

### **Windows**
```sh
python -m venv venv
```

### **macOS/Linux**
```sh
python3 -m venv venv
```

---
## 4. Activate the Virtual Environment
### **Windows (Command Prompt)**
```sh
venv\Scripts\activate
```
### **Windows (PowerShell)**
```sh
venv\Scripts\Activate.ps1
```
### **macOS/Linux**
```sh
source venv/bin/activate
```

After activation, your terminal will show `(venv)` at the beginning of the line.

---
## 5. Ensure the Correct Python Version is Used
Inside the virtual environment, check the Python version again:
```sh
python --version
```
If it still shows an incompatible version, use `pyenv` to set the correct version:
```sh
pyenv local 3.10.12
```

---
## 6. Install `rajinipp`
With the virtual environment activated, install `rajinipp`:
```sh
pip install rajinipp
```

Verify the installation:
```sh
pip show rajinipp
```

Now, you are ready to use `rajinipp`!

---
## 7. Deactivating the Virtual Environment (Optional)
If you want to exit the virtual environment, simply run:
```sh
deactivate
```

---
## 8. Additional Notes
- Always activate the virtual environment before running scripts.
- If you encounter issues with `pip`, upgrade it:
  ```sh
  pip install --upgrade pip
  ```
- If `rajinipp` installation fails, check if you are using a compatible Python version (`>=3.8, <3.11`).

