<div align="center">

# 🐚 minishell

**A simplified Unix shell written in C**

[![Language](https://img.shields.io/badge/Language-C-blue.svg)](https://en.wikipedia.org/wiki/C_(programming_language))
[![Shell](https://img.shields.io/badge/Based%20on-Bash-orange.svg)](#features)
[![Norm](https://img.shields.io/badge/42-Norminette-brightgreen.svg)](#)

[Leia em Português](README.pt.md)

*Built by [andrade950](https://github.com/andrade950) & [g0nca](https://github.com/g0nca)*

</div>

---

## 📌 Overview

`minishell` is a trimmed-down reimplementation of **bash** in C. It covers the full pipeline from reading user input to executing processes, including tokenization, parsing into a binary tree, environment variable expansion, redirections, pipes, and signal handling.

---

## ⚙️ Features

| Category | Details |
|----------|---------|
| **Prompt** | Custom prompt with command line reading |
| **Tokenizer** | Splits input into words, operators, pipes, quotes, and variables |
| **Expansion** | `$VAR`, `$HOME`, `$?`, and all environment variables |
| **Redirections** | Input `<`, output `>`, append `>>`, heredoc `<<` |
| **Pipes** | Chaining multiple commands with `\|` |
| **Signals** | `Ctrl-C`, `Ctrl-D`, `Ctrl-\` handled correctly |
| **External commands** | Resolved via `PATH` and executed with `execve` |
| **Error handling** | Invalid commands, syntax errors, bad redirections |
| **Memory** | Full cleanup on exit, leak prevention throughout |

### Built-ins

`cd` · `echo` · `pwd` · `export` · `unset` · `env` · `exit`

---

## 📁 Project Structure

```
minishell/
├── inc/
│   └── minishell.h
├── libs/
└── srcs/
    ├── binary_tree/      # Execution tree construction and traversal
    ├── builtins/         # Built-in command implementations
    ├── error_functions/  # Error messages and exit codes
    ├── exec/             # Command execution and process management
    ├── expand/           # Environment variable expansion
    ├── free_functions/   # Memory deallocation and cleanup
    ├── heredoc/          # Heredoc support (<<)
    ├── run/              # Built-in dispatch
    ├── signals/          # Signal handlers
    ├── syntax_error/     # Syntax validation
    ├── tokenizer/        # Input tokenization
    ├── utils/            # String and array helpers
    ├── init_shell.c      # Shell initialisation
    └── main.c            # Entry point
```

---

## 🚀 Compilation & Usage

### Clone

```bash
git clone git@github.com:andrade950/42minishell.git
cd 42minishell
```

### Build

```bash
make              # Standard build
make va           # Build with Valgrind support
```

### Run

```bash
./minishell
```

### Exit

```bash
exit
# or press Ctrl+D
```

---
