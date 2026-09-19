## Development with Aider

These are notes on https://agenticengineer.com/principled-ai-coding a begining 
AI developmemnt course I bought.  It is pretty good. I like what he thinks matters. 



exporting your keys:

    export OPENAI_API_KEY=
    export ANTHROPIC_API_KEY=

Kicking off Aider I did:

    source ../.venv/bin/activate 

Which set up the python environment that has aider-chat installed

    export ANTHROPIC_API_KEY=
    aider

and got

    Using sonnet model with API key from environment.
    Aider v0.86.1
    Main model: anthropic/claude-sonnet-4-20250514 with diff edit format, infinite output
    Weak model: anthropic/claude-3-5-haiku-20241022
    Git repo: .git with 5 files
    Repo-map: using 4096 tokens, auto refresh


### Basic Context Commands

There is the `/add` command to add a file.   Then you can write code with things 
e
      Write a functin that has a message parameter that it prints 10 times.  
      Call that function with the message "Hello AI World".  

And it will write to the file added. 

If you've added more than one just specify which one.  

the `/undo` command backs out a commit. 

the `/drop` command takes files out of your context. 

the `/tokens` command shows the token costs and size of context window. 

the `/clear` command clears out the chat context. 

the `/run` command that runs a shell command and adds the output to your context. 

the `/ask` command lets you ask aider anything about your project. 

### Basic Prompt Keywords

Information Dense Keywords  IDK

Adding .py to a word is very dense.. LLMs will know what that means. 
Defining functions with parameter types will tell the LLM a lot. You 
don't have to be that careful, it can pick out that you intend 3 functions and that they
have the same parameters.

      CREATE output_format.py: 
        CREATE def format_as_str(transcript: `TranscriptAnalysis`) -> str, 
                   format_as_json(...), 
                   format_as_markdown(...). 
      UPDATE main.py: ADD a  cli arg for file output format DEFAULT txt, 
                      save output to file with proper extension. 

The list:
 * Create/Build
 * Update/Change - Adding to something that exists
 * Delete/Remove
 * Add - is a create but its adding to something that exists. 
 * Remove
 * Move
 * Replace
 * Save
 * Mirror - Do it like the thing being mirrored.  eg ADD format_as_yaml() MIRROR format_as_json()
 * Var
 * Function
 * Class
 * Type
 * File
 * Default

Break the prompt down into
 * Locations - eg CREATE analyze.py next to main.py
 * actions - CREATE def analyze_forest(lines: str[]) -> str
 * details - using the random_forest function in scikit-learn

Mirror says.. do it like this thing you have in your context. 


### Common Pitfalls

#### Context

Think about what files need to be changed.  These should only be the ones thatneed changed.  

Do not add to many. 

#### Prompt

Use IDK words.  Information Dense Keywords

#### Model

Dont use a weak model or a too powerful model. 

### Aider Configuration File

In the paicc-* diretories there is a `.aider.conf.yml.example`

You can configure lots of things in aider and put it in `.aider.conf.yml`

 * model:  you can set to something and when you type aider you'll see that. 
   * Find a model with /models <text>  (example `/models sonnet`)
   * Note you can set the model with /model
 * Default file:  Always add certain files.. which can ge guides and docs. 
 * read:  Read only file. used for info.   Note this can be array yaml.
   * at the command like you have /read-only to do that interactively
 * test-cmd: and auto-test:  for testing.
 * interactive check with `/settings`

Config info 

### Spec Coding

3 ideas:
 * Reasoning Models
 * Spec/Plan 
 * Aider Architect Mode
   * Prompt Chaining



