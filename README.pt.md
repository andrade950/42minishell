<div align="center">

# 🐚 minishell

**Uma shell Unix simplificada escrita em C**

[![Linguagem](https://img.shields.io/badge/Linguagem-C-blue.svg)](https://en.wikipedia.org/wiki/C_(programming_language))
[![Shell](https://img.shields.io/badge/Baseado%20em-Bash-orange.svg)](#funcionalidades)
[![Norm](https://img.shields.io/badge/42-Norminette-brightgreen.svg)](#)

[Read in English](README.md)

*Desenvolvido por [andrade950](https://github.com/andrade950) & [g0nca](https://github.com/g0nca)*

</div>

---

## 📌 Visão Geral

`minishell` é uma reimplementação simplificada do **bash** em C. Cobre todo o pipeline desde a leitura do input do utilizador até à execução de processos, incluindo tokenização, parsing numa árvore binária, expansão de variáveis de ambiente, redirecionamentos, pipes e tratamento de sinais.

---

## ⚙️ Funcionalidades

| Categoria | Detalhes |
|-----------|---------|
| **Prompt** | Prompt customizado com leitura de linha de comando |
| **Tokenizador** | Divide o input em palavras, operadores, pipes, aspas e variáveis |
| **Expansão** | `$VAR`, `$HOME`, `$?` e todas as variáveis de ambiente |
| **Redirecionamentos** | Entrada `<`, saída `>`, append `>>`, heredoc `<<` |
| **Pipes** | Encadeamento de múltiplos comandos com `\|` |
| **Sinais** | `Ctrl-C`, `Ctrl-D`, `Ctrl-\` tratados corretamente |
| **Comandos externos** | Resolvidos via `PATH` e executados com `execve` |
| **Gestão de erros** | Comandos inválidos, erros de sintaxe, redirecionamentos incorretos |
| **Memória** | Limpeza total ao sair, prevenção de leaks ao longo de toda a execução |

### Built-ins

`cd` · `echo` · `pwd` · `export` · `unset` · `env` · `exit`

---

## 📁 Estrutura do Projeto

```
minishell/
├── inc/
│   └── minishell.h
├── libs/
└── srcs/
    ├── binary_tree/      # Construção e travessia da árvore de execução
    ├── builtins/         # Implementação dos comandos built-in
    ├── error_functions/  # Mensagens de erro e códigos de saída
    ├── exec/             # Execução de comandos e gestão de processos
    ├── expand/           # Expansão de variáveis de ambiente
    ├── free_functions/   # Libertação de memória e limpeza
    ├── heredoc/          # Suporte a heredoc (<<)
    ├── run/              # Despacho de built-ins
    ├── signals/          # Handlers de sinais
    ├── syntax_error/     # Validação de sintaxe
    ├── tokenizer/        # Tokenização do input
    ├── utils/            # Auxiliares de strings e arrays
    ├── init_shell.c      # Inicialização do shell
    └── main.c            # Ponto de entrada
```

---

## 🚀 Compilação e Execução

### Clonar

```bash
git clone git@github.com:andrade950/42minishell.git
cd 42minishell
```

### Compilar

```bash
make              # Build normal
make va           # Build com suporte a Valgrind
```

### Executar

```bash
./minishell
```

### Sair

```bash
exit
# ou pressiona Ctrl+D
```

---
