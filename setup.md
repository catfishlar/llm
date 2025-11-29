
So I am running through the course on 

https://agenticengineer.com/principled-ai-coding/course  Login Github account. 

Which emphasizes Aider pair programming.  

Tools git, uv, python 3.10

Created uv based .venv in the /Users/lmurdock/src/llm

For magic values see my local Obsidian Vault "LLMs/Principalled AI Developer"

## Create the `llm` python env for the course

    (base) ➜  llm git:(main) ✗ pwd   
    /Users/lmurdock/src/llm
    (base) ➜  llm git:(main) ✗ uv python install 3.10
    Installed Python 3.10.19 in 1.21s
     + cpython-3.10.19-macos-x86_64-none (python3.10)
    warning: `/Users/lmurdock/.local/bin` is not on your PATH. To use installed Python executables, run `export PATH="/Users/lmurdock/.local/bin:$PATH"` or `uv python update-shell`.
    (base) ➜  llm git:(main) ✗ uv python update-shell
    Created configuration file: /Users/lmurdock/.zshenv
    Restart your shell to apply changes
    (base) ➜  llm git:(main) ✗ 

in a new shell 

    (base) ➜  llm git:(main) ✗ uv venv --python 3.10 .venv
    Using CPython 3.10.9 interpreter at: /Users/lmurdock/anaconda3/bin/python3
    Creating virtual environment at: .venv
    Activate with: source .venv/bin/activate
    (base) ➜  llm git:(main) ✗ source .venv/bin/activate
    (.venv) (base) ➜  llm git:(main) ✗ uv pip install aider-chat
    Resolved 119 packages in 2.22s

