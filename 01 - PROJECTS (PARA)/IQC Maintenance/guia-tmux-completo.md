---
title: "Guia Completo e Configuração do TMUX"
date: 2026-10-28
tags:
  - tmux
  - terminal
  - linux
  - wsl
  - produtividade
  - dotfiles
---

# 💻 Guia Completo e Configuração do TMUX

Este guia documenta o funcionamento, os atalhos, a resolução de problemas comuns e a persistência de sessões no **tmux** (Terminal Multiplexer) no Ubuntu / WSL. Contém também o ficheiro de configuração `~/.tmux.conf` pronto a copiar para novos computadores.

---

## 📑 Índice
1. [Conceitos Básicos e Tecla Prefixo](#1-conceitos-básicos-e-tecla-prefixo)
2. [Configuração Completa do `~/.tmux.conf`](#2-configuração-completa-do-tmuxconf)
3. [Como Instalar e Replicar num Novo Computador](#3-como-instalar-e-replicar-num-novo-computador)
4. [Gestão e Encerramento de Painéis e Janelas](#4-gestão-e-encerramento-de-painéis-e-janelas)
5. [O que é o Modo de Cópia (Copy Mode) e como Desbloquear](#5-o-que-é-o-modo-de-cópia-copy-mode-e-como-desbloquear)
6. [Persistência de Sessões: Salvar e Restaurar (Resurrect & Continuum)](#6-persistência-de-sessões-salvar-e-restaurar-resurrect--continuum)
7. [Iniciar Automaticamente o TMUX ao Abrir o WSL](#7-iniciar-automaticamente-o-tmux-ao-abrir-o-wsl)
8. [Tabela de Atalhos Rápidos](#8-tabela-de-atalhos-rápidos)

---

## 1. Conceitos Básicos e Tecla Prefixo

O tmux organiza o seu terminal em três níveis:
* **Sessão (*Session*):** Um conjunto de janelas que continua a correr em segundo plano, mesmo que feche a janela do terminal.
* **Janela (*Window*):** Abas no fundo do ecrã (como separadores de navegador).
* **Painel (*Pane*):** Divisões dentro da mesma janela (lado a lado ou cima/baixo).

> [!NOTE]
> **A Tecla Prefixo (`Ctrl + b`):**
> Quase todos os atalhos do tmux exigem que você prima a tecla prefixo antes do comando:
> 1. Prima **`Ctrl + b`** e **solte**.
> 2. Pressione a tecla do comando (ex: `x`, `|`, `-`, etc.).

---

## 2. Configuração Completa do `~/.tmux.conf`

Copie este conteúdo exatamente como está para o ficheiro `~/.tmux.conf`:

```tmux
# ==============================================================================
# CONFIGURAÇÃO PESSOAL DO TMUX
# ==============================================================================

# --- Usabilidade Geral ---
# Ativar suporte total ao rato (clicar para focar painel, redimensionar, scroll)
set -g mouse on

# Numeração de janelas e painéis a começar em 1 (em vez de 0)
set -g base-index 1
setw -g pane-base-index 1

# Renumerar automaticamente as janelas quando uma for fechada
set -g renumber-windows on

# Aumentar o limite do histórico de linhas do terminal (scrollback)
set -g history-limit 10000

# Evitar atraso (lag) ao pressionar a tecla Escape (essencial para utilizadores de Vim/Neovim)
set -sg escape-time 0

# --- Atalhos de Teclado Personalizados ---
# Recarregar as configurações facilmente com: Prefixo + r
bind r source-file ~/.tmux.conf \; display-message "Configuração recarregada com sucesso!"

# Dividir painéis usando | (vertical) e - (horizontal), abrindo na mesma pasta ativa
bind | split-window -h -c "#{pane_current_path}"
bind - split-window -v -c "#{pane_current_path}"
unbind '"'
unbind %

# Alternar rapidamente entre painéis usando Alt + Setas (sem precisar do Prefixo!)
bind -n M-Left select-pane -L
bind -n M-Right select-pane -R
bind -n M-Up select-pane -U
bind -n M-Down select-pane -D

# --- Aspeto Visual e Cores ---
# Ativar suporte a 256 cores e cores reais (TrueColor)
set -g default-terminal "xterm-256color"
set -as terminal-overrides ",xterm-256color:Tc"

# Barra de estado (Status Bar) na parte inferior
set -g status-position bottom
set -g status-style bg=default,fg=white
set -g status-left-length 40
set -g status-left "#[fg=green,bold] #S #[fg=white]| "
set -g status-right-length 80
set -g status-right "#[fg=cyan]%Y-%m-%d #[fg=white]| #[fg=yellow]%H:%M "

# Estilo dos separadores de janelas
set -g window-status-format "#[fg=gray] #I:#W "
set -g window-status-current-format "#[fg=black,bg=green,bold] #I:#W "

# Estilo das bordas das divisões (painéis)
set -g pane-border-style fg=brightblack
set -g pane-active-border-style fg=green

# Barra de mensagens internas do tmux
set -g message-style bg=yellow,fg=black,bold

# --- Plugins e Persistência de Sessões (TPM) ---
set -g @plugin 'tmux-plugins/tpm'
set -g @plugin 'tmux-plugins/tmux-resurrect'
set -g @plugin 'tmux-plugins/tmux-continuum'

# Restaurar automaticamente a última sessão salva ao iniciar o tmux
set -g @continuum-restore 'on'

# Restaurar também o conteúdo do texto dos painéis e sessões ativas do Neovim
set -g @resurrect-capture-pane-contents 'on'
set -g @resurrect-strategy-nvim 'session'

# Inicializar o Tmux Plugin Manager (ESTA LINHA DEVE SER SEMPRE A ÚLTIMA!)
run '~/.tmux/plugins/tpm/tpm'
```

---

## 3. Como Instalar e Replicar num Novo Computador

Para configurar este mesmo ambiente do zero num novo computador com Ubuntu ou WSL:

```bash
# 1. Instalar o tmux
sudo apt update
sudo apt install -y tmux git

# 2. Instalar o TPM (Tmux Plugin Manager)
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm

# 3. Criar e colar o ficheiro de configuração ~/.tmux.conf
nano ~/.tmux.conf
# (Cole o conteúdo da Secção 2 acima e grave)

# 4. Iniciar o tmux pela primeira vez
tmux

# 5. Instalar os plugins
# Dentro do tmux, prima:
# Ctrl + b   depois   Shift + i  (letra 'I' maiúscula)
```
*O TPM fará o download automático do `tmux-resurrect` e `tmux-continuum` e ativará a persistência.*

---

## 4. Gestão e Encerramento de Painéis e Janelas

### Como fechar um painel lateral:
* **Método 1 (Atalho do Tmux):**
  1. Mude o foco para o painel com as setas (`Alt + Seta`).
  2. Prima: **`Ctrl + b`** depois **`x`**.
  3. Prima **`y`** para confirmar.
* **Método 2 (O mais rápido, direto pelo Shell):**
  * Dentro do painel, escreva **`exit`** e dê Enter (ou prima o atalho **`Ctrl + d`**).
* **Método 3 (Fechar todos os outros painéis e deixar apenas o atual):**
  * Prima **`Ctrl + b`** depois **`:`** e escreva:
    ```text
    kill-pane -a
    ```

### Como gerir Janelas (Separadores):
* Criar nova janela: `Ctrl + b` depois `c`
* Fechar janela atual: `Ctrl + b` depois `&`
* Mudar para janela seguinte: `Ctrl + b` depois `n`
* Mudar para janela anterior: `Ctrl + b` depois `p`
* Ir diretamente para a janela número 1, 2, etc.: `Ctrl + b` depois `1`, `2`...

---

## 5. O que é o Modo de Cópia (Copy Mode) e como Desbloquear

### O que significa `[WARN: COPY MODE]`?
Como temos o suporte de rato ativado (`mouse on`), quando utiliza a **roda de scroll do rato** ou **clica e arrasta texto**, o tmux entra automaticamente no **Modo de Cópia (*Copy Mode*)**.

* **Porque parece bloqueado:** No modo de cópia, o tmux pausa a receção de comandos no terminal para que você possa ler o histórico e copiar texto.
* **Como sair imediatamente e desbloquear o terminal:**
  Pressione a tecla **`q`** (ou **`Ctrl + c`**). A janela volta a responder normalmente.

---

## 6. Persistência de Sessões: Salvar e Restaurar (Resurrect & Continuum)

O tmux por defeito perde todas as sessões quando o computador é desligado ou quando o WSL é encerrado. Com os plugins instalados, isso deixa de acontecer:

### 1. Funcionamento Automático
* **Guardar:** O `tmux-continuum` guarda automaticamente o estado de todas as sessões, nomes de janelas e pastas de trabalho a cada **15 minutos**.
* **Restaurar:** Ao arrancar o `tmux`, o estado guardado mais recente é restaurado sozinho.

### 2. Comandos Manuais (Recomendado antes de desligar o PC)
Para garantir que o estado exato daquele segundo fica registado antes de fechar o portátil:
* **Salvar sessão:**
  Pressione **`Ctrl + b`** e solte, e depois **`Ctrl + s`**.
* **Restaurar sessão manualmente:**
  Pressione **`Ctrl + b`** e solte, e depois **`Ctrl + r`**.

### 3. Salvar e Restaurar diretamente via Terminal (Sem atalhos)
Se preferir correr por comando direto:
```bash
# Para salvar:
~/.tmux/plugins/tmux-resurrect/scripts/save.sh

# Para restaurar:
~/.tmux/plugins/tmux-resurrect/scripts/restore.sh
```

### 4. Onde ficam os ficheiros salvos no disco?
Os ficheiros de sessão guardam o layout e o histórico em:
```text
~/.local/share/tmux/resurrect/
```
Para verificar a lista de sessões gravadas com data e hora:
```bash
ls -lt ~/.local/share/tmux/resurrect/
```
*(O link simbólico `last` aponta sempre para o ponto de restauro mais recente).*

---

## 7. Iniciar Automaticamente o TMUX ao Abrir o WSL

Para que nunca tenha de se preocupar em abrir o tmux manualmente e o seu ambiente de trabalho apareça restaurado assim que abre o terminal do Ubuntu:

Adicione este bloco ao final do seu ficheiro `~/.bashrc`:

```bash
# Iniciar ou reconectar ao tmux automaticamente ao entrar no terminal
if command -v tmux &> /dev/null && [ -z "$TMUX" ]; then
    tmux attach || tmux new -s principal
fi
```

---

## 8. Tabela de Atalhos Rápidos

| Ação | Atalho |
| :--- | :--- |
| **Prefixo (ativa comandos)** | `Ctrl + b` |
| **Dividir painel verticalmente** | `Ctrl + b` depois `\|` |
| **Dividir painel horizontalmente** | `Ctrl + b` depois `-` |
| **Mudar entre painéis** | `Alt + Seta Esquerda / Direita / Cima / Baixo` |
| **Fechar painel atual** | `Ctrl + b` depois `x` (ou digitar `exit`) |
| **Criar nova janela (aba)** | `Ctrl + b` depois `c` |
| **Mudar de janela** | `Ctrl + b` depois `n` (próxima) ou número da janela |
| **Sair do Modo de Cópia / Desbloquear ecrã** | **`q`** ou `Ctrl + c` |
| **Salvar sessão agora** | `Ctrl + b` depois `Ctrl + s` |
| **Restaurar sessão salva** | `Ctrl + b` depois `Ctrl + r` |
| **Recarregar `~/.tmux.conf`** | `Ctrl + b` depois `r` |
| **Instalar plugins do TPM** | `Ctrl + b` depois `Shift + i` (`I`) |
| **Desanexar sessão (deixar a correr no fundo)**| `Ctrl + b` depois `d` |
| **Reconectar à sessão fora do tmux** | `tmux attach` |
