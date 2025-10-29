# 🐚 Minishell

## 🧩 1. Overview

This project consists of developing a simplified version of a **shell** (command line) — a kind of "mini bash" — to explore topics such as:
- Input reading
- Parsing
- Command execution
- Environment variable handling  
- Pipes  
- Redirections  
- Signals  

The goal was to implement the main functionalities of a shell, maintaining an appropriate level of complexity for the academic and technical scope.

---

## ⚙️ 2. Implemented Features

- Reading command line from the user, with **custom prompt**.  
- **Tokenization** of the command line (splitting into words, redirections, pipes, variables, quotes, etc).
- **Environment variable expansion** (`$HOME`, `$?`, etc).  
- Support for input **redirections** input (`<`), output (`>`), and append (`>>`).  
- Support for **pipes (`|`)** to chain multiple commands. 
- Implementation of **essential built-ins**:
  - `cd`
  - `echo`
  - `pwd`
  - `export`
  - `unset`
  - `env`
  - `exit`
- Execution of **external commands** via  `execve`, searching in `PATH`.  
- **Signal handling** (Ctrl-C, Ctrl-D, Ctrl-\).
- **Error management** (invalid commands, incorrect syntax, etc).
- **Proper memory deallocation** and leak prevention whenever possible.

---

## 📁 3. Code Structure

The project structure is organized as follows:
```
MINISHELL/
│
├── inc/
│    └── minishell.h
│
├── libs/
│
├── srcs/
│     ├── binary_tree/      # Construction and execution of the execution tree
│     ├── builtins/         # Implementation of built-in commands
│     ├── error_functions/  # Error message and code management
│     ├── exec/             # Command execution and process management
│     ├── expand/           # Environment variable expansion
│     ├── free_functions/   # Memory deallocation and cleanup
│     ├── heredoc/          # Heredoc implementation (<<)
│     ├── run/              # Main execution loop management
│     ├── signals/          # Signal handling
│     ├── syntax_error/     # Syntax error checking and handling
│     ├── tokenizer/        # Command line tokenization
│     ├── utils/            # Auxiliary functions (strings, arrays, etc)
│     │
│     ├── init_shell.c      # Shell initialization
│     └── main.c            # Program entry point
│
└── Makefile                # Project compilation
```

---

## 🧱 4. Compilation and Execution

1. **Clone the repository:**
   ```bash
   git clone https://github.com/andrade950/42minishell.git
   cd 42minishell
2. **Compile the project:**
   ```bash
   make
3. **Compile the project with Valgrind:**
   ```bash
   make va
4. **Run the minishell:**
   ```bash
   ./minishell
5. **To exit the minishell, use:**
   ```bash
   exit
    or press Ctrl + D.
  
