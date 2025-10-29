# 🐚 Minishell

[Read in English](README.md)

## 🧩 1. Visão Geral

Este projeto consiste em desenvolver uma versão simplificada de um **shell** (linha de comando) — uma espécie de “pequeno bash” — para explorar temas como:  
- Leitura de input  
- Parsing  
- Execução de comandos  
- Tratamento de variáveis de ambiente  
- Pipes  
- Redirecionamentos  
- Sinais  

O objetivo foi implementar as principais funcionalidades de um shell, mantendo um nível de complexidade adequado ao âmbito académico e técnico.

---

## ⚙️ 2. Funcionalidades Implementadas

- Leitura de linha de comando do utilizador, com **prompt customizado**.  
- **Tokenização** da linha de comando (dividir em palavras, redireções, pipes, variáveis, aspas, etc).  
- **Expansão de variáveis de ambiente** (`$HOME`, `$?`, etc).  
- Suporte a **redirecionamentos** de entrada (`<`), saída (`>`), e append (`>>`).  
- Suporte a **pipes (`|`)** para encadear múltiplos comandos.  
- Implementação de **built-ins essenciais**:
  - `cd`
  - `echo`
  - `pwd`
  - `export`
  - `unset`
  - `env`
  - `exit`
- Execução de **comandos externos** via `execve`, procurando no `PATH`.  
- **Tratamento de sinais** (Ctrl-C, Ctrl-D, Ctrl-\).  
- **Gestão de erros** (comandos inválidos, sintaxe incorreta, etc).  
- **Libertação correta de memória** e prevenção de leaks sempre que possível.

---

## 📁 3. Estrutura do Código

A estrutura do projeto está organizada da seguinte forma:
```
MINISHELL/
│
├── inc/
│    └── minishell.h
│
├── libs/
│
├── srcs/
│     ├── binary_tree/      # Construção e execução da árvore de execução
│     ├── builtins/         # Implementação dos comandos built-in
│     ├── error_functions/  # Gestão de mensagens e códigos de erro
│     ├── exec/             # Execução de comandos e gestão de processos
│     ├── expand/           # Expansão de variáveis de ambiente
│     ├── free_functions/   # Libertação de memória e limpeza
│     ├── heredoc/          # Implementação do heredoc (<<)
│     ├── run/              # Run Builtins
│     ├── signals/          # Tratamento de sinais
│     ├── syntax_error/     # Verificação e tratamento de erros de sintaxe
│     ├── tokenizer/        # Tokenização da linha de comandos
│     ├── utils/            # Funções auxiliares (strings, arrays, etc)
|     |
│     └── init_shell.c      # Inicialização do shell
│     └── main.c            # Ponto de entrada do programa
|
└── Makefile # Compilação do projeto
```

---

## 🧱 4. Compilação e Execução

1. **Clonar o repositório:**
   ```bash
   git clone git@github.com:andrade950/42minishell.git
   cd 42minishell
2. **Compilar o projeto**
   ```bash
   make
3. **Compilar o projeto com Valgrind:**
   ```bash
   make va
4. **Executar o minishell:**
   ```bash
   ./minishell
5. **Para sair do minishell, use:**
   ```bash
   exit
    ou pressione Ctrl + D.
  
