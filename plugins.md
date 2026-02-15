# DAPS Plugin Development Guide

Plugins allow you to extend DAPS functionality using pure Python. They are stored in `~/.config/daps/plugins/` and are automatically loaded when the shell starts.

---

## 1. Plugin Structure

A plugin is a standard `.py` file. For DAPS to recognize it, the file **must** contain a function named `run` that accepts a list of arguments.



### Basic Template:
```python
def run(args):
    # Your logic goes here
    print("Plugin executed!")
    
    # Return 0 for success, or any other number for an error code
    return 0
```

---

## 2. Handling Arguments

The `args` parameter is a list of strings containing everything typed after the plugin name.

**Example Plugin (`greet.py`):**
```python
def run(args):
    if not args:
        print("Usage: greet <name>")
        return 1
    
    name = args[0]
    print(f"Hello, {name}! Welcome to DAPS.")
    return 0
```

*If you run `greet Stormzady`, the `args` list becomes `['Stormzady']`.*

---

## 3. Accessing System Resources

Since plugins are pure Python, you can import any standard library (like `os`, `platform`, or `datetime`) to create powerful tools.

**System Info Plugin Example (`sysinfo.py`):**
```python
import platform
import os

def run(args):
    print(f"OS: {platform.system()} {platform.release()}")
    print(f"User: {os.getlogin()}")
    return 0
```

---

## 4. Installation & Usage

1.  Navigate to your plugins directory:  
    `cd ~/.config/daps/plugins/`
2.  Create your Python file (e.g., `mytool.py`).
3.  Restart DAPS or run the shell.
4.  Call your plugin by its filename (without the `.py`):
    ```bash
    > mytool
    ```



---

## 5. Tips for Performance
* **Error Handling:** Wrap your plugin logic in a `try/except` block to prevent a buggy plugin from crashing your entire DAPS session.
* **Return Codes:** Always return an integer. This allows the DAPS prompt to show the correct status code (red for non-zero, normal for zero).
* **Naming:** Avoid naming your plugin the same as a system command (like `ls.py`), or DAPS may prioritize the plugin over the system binary.

---