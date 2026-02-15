# DAPS

DAPS is a high-performance shell written in pure Python. It’s designed to be lightweight, customizable, and extensible through Python plugins.

---

## Installation

1. Go to **Releases** and get the newest version of DAPS.  
   - Releases come as `.zip` files. Pre-releases may be `.zip` or single files. 
   - Stable versions (marked as **Release**) are recommended.

2. Once downloaded, extract it to a folder of your choice.

3. Open the `installer` folder and run:

```bash
sh install.sh
```

4. After installation, run:

```bash
daps
```

---

## Usage

Basic shell commands work, like `cd` or `ls`. DAPS features **Tab-Completion** for commands, aliases, and plugins.

### Built-in Commands:

- `clear` – Clears everything on screen.  
- `clearhist` – Clears shell history. After running this, the shell cannot record history until restarted.
- `exit` – Exits the shell.  
- `update` – Updates DAPS by cloning the repository into a temp folder and copying it into `/usr/bin`.
- `cd [path]` – Change directory (supports `~` for home).

---

## Configuration

The shell creates a file named `config.json` in the `~/.config/daps/` directory.

### `"aliases"` (with Argument Support)
You can now pass arguments into aliases using `$1`, `$2`, etc., or `$*` for all arguments.

```json
{
  "aliases": {
    "list": "ls -la $1",
    "commit": "git commit -m '$*'"
  }
}
```
*Example:* Typing `list /tmp` executes `ls -la /tmp`.

### `"greeter"`
The `"greeter"` option runs a command every time the shell starts:

```json
{
  "greeter": "fastfetch"
}
```

### `"cleargreet"`
Specifies whether the greeter should run when using the `clear` command:

```json
{
  "cleargreet": "yes"
}
```

---

## Plugin System

DAPS allows you to write custom shell commands in pure Python.

### Adding Plugins:
1. Create a `.py` file in `~/.config/daps/plugins/`.
2. Define a `run(args)` function that returns an exit code.

**Example Plugin (`hello.py`):**
```python
def run(args):
    name = args[0] if args else "User"
    print(f"Hello {name} from a DAPS plugin!")
    return 0
```
*Usage:* Type `hello Stormzady` in DAPS to execute.

---

## Advanced Features

* **Auto-Suggestions:** Hit `Tab` to autocomplete commands based on your path, aliases, and plugins.
* **Persistent History:** Your command history is saved in `~/.daps.history` and persists across sessions.
* **Smart Prompt:** The prompt changes color to indicate the last command's exit status. Red `[code]` indicates an error.

---

## More Information

- DAPS is protected by the **GNU license**, meaning any contributions or derivatives of the program **must be fully open source**.  

---

**© 2026, Nytrix Labs**