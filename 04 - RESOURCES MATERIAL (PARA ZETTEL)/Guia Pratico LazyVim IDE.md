# 🚀 Guia Mestre: Neovim + LazyVim como IDE para Automação de Testes (Java & Python) e Git

Este é o teu manual de referência completo e centralizado para utilizar o **Neovim (LazyVim)** como ambiente de trabalho principal para automação de testes (**Java com TestNG + Selenide** e **Python com Pytest**), com gestão de versões via **Git/Lazygit** sem depender do rato.

---

## 📌 1. Filosofia de Utilização e Tecla Mestre

* **Tecla Líder (`<leader>`)**: No LazyVim é a **`<Barra de Espaço>`**.
* **Menu Dinâmico (*which-key*)**:
  * Ao carregar numa tecla introdutória (como `<Espaço>` ou `g`), abre-se uma janela inferior com as opções.
  * **Como funciona:** Não se navega com setas nem com `Enter`. Carrega-se **diretamente na letra da opção desejada**.
  * **Mudar de página:** Se houver várias páginas de atalhos, usa **`<Ctrl-d>`** (descer) e **`<Ctrl-u>`** (subir).
  * **Cancelar/Sair:** Prime **`<Esc>`**.
* **Regra de Ouro:** Evitar o rato. Toda a navegação é feita pelo teclado com `h, j, k, l`, `w, b` e saltos inteligentes.

---

## 🛠️ 2. Instalação e Requisitos no Ubuntu

### Ferramentas de Sistema e Compiladores
```bash
sudo apt update
sudo apt install -y build-essential ripgrep fd-find unzip curl git maven python3-venv
```

Criar o alias para o comando `fd`:
```bash
mkdir -p ~/.local/bin
ln -s $(which fdfind) ~/.local/bin/fd
```

### Versões do Java (JDTLS & OpenJDK)
> [!IMPORTANT]
> O servidor de linguagem Java do Mason (`jdtls`) mais recente exige o **Java 25** para executar o seu contentor OSGi/Eclipse sem erros de arranque (*Exit code 13*):

```bash
# Instalar o OpenJDK 25 (ou 21 para compilação retrocompatível)
sudo apt update
sudo apt install -y openjdk-25-jdk
```

### Neovim Oficial ($\ge 0.10$)
```bash
curl -LO https://github.com/neovim/neovim/releases/latest/download/nvim-linux-x86_64.tar.gz
sudo rm -rf /opt/nvim-linux-x86_64
sudo tar -C /opt -xzf nvim-linux-x86_64.tar.gz
rm nvim-linux-x86_64.tar.gz
sudo ln -sf /opt/nvim-linux-x86_64/bin/nvim /usr/local/bin/nvim
```

### Nerd Font (Ícones de Pastas e Ficheiros)
```bash
mkdir -p ~/.local/share/fonts
curl -fLo ~/.local/share/fonts/JetBrainsMono.tar.xz \
  https://github.com/ryanoasis/nerd-fonts/releases/latest/download/JetBrainsMono.tar.xz
tar -xf ~/.local/share/fonts/JetBrainsMono.tar.xz -C ~/.local/share/fonts/
fc-cache -fv
```
*Configura o teu terminal (Gnome Terminal, Kitty, Ghostty, Alacritty) para usar a fonte "JetBrainsMono Nerd Font".*

---

## 🗂️ 3. Navegação, Janelas e Gestão de Código

### Ficheiros e Pesquisa Rápida
* `<Espaço><Espaço>` ou `<Espaço>ff`: Localizar ficheiro por nome (*Fuzzy finder*).
* `<Espaço>/` ou `<Espaço>sg`: Pesquisar texto em todos os ficheiros do projeto (*Live Grep*).
* `<Espaço>e`: Alternar a barra lateral com a árvore de diretórios (Neo-tree).
  * Dentro da árvore: `a` cria ficheiro/pasta, `d` apaga, `r` renomeia.

### Janelas (Splits) e Abas (Buffers)
* `Shift + h` / `Shift + l`: Alternar entre ficheiros abertos na barra superior (esquerda/direita).
* `<Espaço>bd`: Fechar o buffer (ficheiro) atual.
* `<Espaço>|`: Dividir o ecrã na vertical.
* `<Espaço>-`: Dividir o ecrã na horizontal.
* `Ctrl + h / j / k / l`: Mover o cursor entre janelas divididas.

---

## 🔍 4. Navegação no Código com LSP (Variáveis, Métodos e Classes)

> [!NOTE]
> Os atalhos iniciados por `g` só aparecem e ficam ativos se o servidor de linguagem estiver conectado ao ficheiro. Abre sempre o Neovim **na pasta raiz do projeto** (onde está o `pom.xml`, `build.gradle` ou `.git`) e verifica com `:LspInfo`.

```mermaid
flowchart TD
    Cursor["Cursor no Código"]
    Cursor -->|"gd"| MethodDef["Entrar na Definição do Método / Variável"]
    Cursor -->|"gy"| TypeDef["Saltar para a Classe/Tipo da Variável"]
    Cursor -->|"gI"| ImplDef["Ir para a Implementação Concreta (Interface)"]
    Cursor -->|"K"| HoverDoc["Pré-visualizar Documentação (Popup)"]
    Cursor -->|"gr"| References["Listar todas as Referências no Projeto"]
    MethodDef -.->|"Ctrl + o"| ReturnBack["Voltar Atrás (Histórico de Saltos)"]
    TypeDef -.->|"Ctrl + o"| ReturnBack
```

### Atalhos de Salto
* **`gd`** (*Go to Definition*): Salta diretamente para o código onde o método sob o cursor foi implementado.
* **`gy`** (*Go to Type Definition*): Estando sobre uma variável (ex: `loginPage`), salta diretamente para o ficheiro da **Classe dessa variável** (`LoginPage.java`).
* **`gI`** (*Go to Implementation*): Salta para a implementação concreta quando se trata de um método de interface.
* **`K`** (Shift + k): Abre um balão flutuante com a assinatura, parâmetros e JavaDoc/Docstring sem mudar de ficheiro.
* **`gr`**: Lista todas as referências no projeto onde esse método/variável é utilizado.

### Como Voltar Atrás (Histórico de Saltos)
* **`Ctrl + o`**: Volta para a posição anterior de onde fizeste o salto (*Jump list back*).
* **`Ctrl + i`**: Avança novamente para a frente (*Jump list forward*).

---

## ☕ 5. Testes em Java: TestNG + Selenide

### Configuração de Módulos
* Em `:LazyExtras`: `lang.java`, `test.core` e `dap.core`.
* Em `:Mason`: `java-debug-adapter` e `java-test`.

### Atalhos Configurados no `keymaps.lua`

Os atalhos abaixo estão configurados em `~/.config/nvim/lua/config/keymaps.lua` com `{ auto_close = false }` (a janela **não fecha sozinha** no fim do teste):

| Atalho | O que executa | Como funciona |
| :--- | :--- | :--- |
| **`<Espaço>tm`** | **Método `@Test` sob o cursor** | Deteta o método atual via Treesitter e corre: `mvn test -Dtest=Classe#metodo`. |
| **`<Espaço>tc`** | **Classe de teste inteira** | Corre `mvn test -Dtest=Classe` via Maven. |
| **`<Espaço>tx`** | **Ficheiro Suite XML atual** | Estando num `.xml` (ex: `testng.xml`), corre: `mvn clean test -DsuiteXmlFile=ficheiro.xml`. |
| **`<Espaço>tr`** | **Método nativo (DAP)** | Execução interna do JDTLS sem abrir terminal externo. |
| **`<Ctrl-/>`** | **Alternar Terminal de Logs** | Abre ou recolhe a janela flutuante com o log completo. |

### Como Visualizar e Navegar no Output dos Testes
1. O terminal mantém-se aberto no ecrã após a execução para leitura dos relatórios do Selenide/Surefire.
2. **Navegar no log:** Usa **`Ctrl + u`** (subir) e **`Ctrl + d`** (descer), ou `j`/`k`.
3. **Pesquisar erros:** Escreve `/FAILURE` ou `/Exception` e prime `Enter`.
4. **Fechar a janela:** Prime **`q`** ou **`<Ctrl-/>`**.
5. **Reabrir mais tarde:** Prime **`<Ctrl-/>`** para trazer o histórico de volta.

### Suporte a XML no `pom.xml`
Garante que o `maven-surefire-plugin` suporta a passagem da suite por parâmetro:
```xml
<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-surefire-plugin</artifactId>
    <version>3.2.5</version>
    <configuration>
        <suiteXmlFiles>
            <suiteXmlFile>${suiteXmlFile}</suiteXmlFile>
        </suiteXmlFiles>
    </configuration>
</plugin>
```

### Selenide no Linux
Para alternar entre modo visual e silencioso (*headless*):
```java
import com.codeborne.selenide.Configuration;

Configuration.headless = true; // corre sem abrir janelas gráficas
```

---

## 🐍 6. Testes em Python: Pytest

### Configuração
O LazyVim inclui `lang.python` com o adaptador `neotest-python`.

### Seleção de VirtualEnv
* **`<Espaço>cv`** (*Select VirtualEnv*): Deteta e ativa as pastas `.venv`, Poetry ou Conda para que o Pytest corra com as bibliotecas certas.

### Atalhos Neotest
| Atalho | Ação |
| :--- | :--- |
| **`<Espaço>tr`** | Executa todos os testes do **ficheiro atual** (*Run File*). |
| **`<Espaço>tt`** | Executa o **teste/função sob o cursor** (*Run Nearest*). |
| **`<Espaço>to`** | Abre janela flutuante com a mensagem de erro e traceback (*Test Output*). |
| **`<Espaço>tO`** | Abre painel inferior fixo com a consola completa do Pytest. |
| **`<Espaço>ts`** | Abre a barra lateral com o sumário e árvore de testes (*Toggle Summary*). |
| **`<Espaço>tw`** | **Modo Watch** (TDD): corre o teste automaticamente sempre que gravas (`:w`). |
| **`<Espaço>dPt`**| Inicia depuração passo a passo com breakpoints (*Debug Python Test*). |

---

## 🌿 7. Controlo de Versões com Git & Lazygit

### Operações Diárias no Lazygit (`<Espaço>gg`)
* `Espaço`: Adiciona ou retira do stage ficheiros ou linhas selecionadas.
* `c`: Abre o prompt para escrever a mensagem de commit.
* `Shift + p` (`P`): Efetua `git push`.
* `p`: Efetua `git pull`.
* `r`: Rebase sobre o ramo selecionado.
* `q` ou `Esc`: Sai do Lazygit e volta ao editor.

### Passphrase de Chave SSH (`id_rsa` / `id_ed25519`)
Para evitar prompts repetidos de senha:
```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
```

### Erros de Permissão / Rebase Bloqueado (`Permission denied`)
Se ficheiros do repositório tiverem ficado bloqueados como `root`:
```bash
# 1. Recuperar posse dos ficheiros
sudo chown -R $USER:$USER ~/caminho/para/o/projeto

# 2. Cancelar o rebase que ficou a meio
git rebase --abort

# 3. Atualizar normalmente
git pull --rebase origin main
```

---

## 🔧 8. Diagnóstico de Erros & Resolução de Problemas

### 1. `jdtls requires at least Java 21` ou `Exit code 13`
* **Causa:** O Mason instala a versão de ponta do `jdtls`, que exige Java 21/25 para o ambiente OSGi do Eclipse.
* **Solução:**
  ```bash
  sudo apt install -y openjdk-25-jdk
  rm -rf ~/.cache/nvim/jdtls
  ```

### 2. Conflito entre Plugins de IA
* **Problema:** Ter `ai.copilot` e `ai.copilot-native` ao mesmo tempo gera erros de arranque.
* **Solução:** Manter apenas o **`ai.copilot`** (nativo em Lua) e remover o `ai.copilot-native` em `lazyvim.json`.
* **Copilot 365 vs GitHub Copilot:** O Neovim integra exclusivamente com o **GitHub Copilot** (`:Copilot auth`). O Copilot do Office 365 não suporta editores de código. Se não tiveres subscrição paga do GitHub Copilot, podes usar a alternativa gratuita **`ai.codeium`** (`:Codeium Auth`).

### 3. Como Desinstalar Plugins Desnecessários
* Pelo menu visual: `:LazyExtras`, seleciona o módulo e carrega em **`x`**. Depois corre `:Lazy` e prime **`X`** (limpar ficheiros).
* Pelo ficheiro: Remove a linha do módulo em [lazyvim.json](file:///home/dapb/.config/nvim/lazyvim.json).

---

## ⚡ 9. Tabela Consolidada de Atalhos (Cheat Sheet)

```
┌──────────────────────────────────────────────────────────────┐
│                    NAVEGAÇÃO & GERAL                         │
├──────────────────────────────┬───────────────────────────────┤
│ <Espaço><Espaço>             │ Encontrar ficheiro            │
│ <Espaço>sg                   │ Pesquisar texto em ficheiros  │
│ <Espaço>e                    │ Explorador de pastas (Neo-tree│
│ Shift + h / Shift + l        │ Alternar abas/buffers         │
│ Ctrl + /                     │ Abrir/fechar terminal de logs │
├──────────────────────────────┼───────────────────────────────┤
│                  CÓDIGO & NAVEGAÇÃO LSP                      │
├──────────────────────────────┬───────────────────────────────┤
│ gd                           │ Entrar na definição do método │
│ gy                           │ Entrar na Classe da variável  │
│ gI                           │ Entrar na implementação (intf)│
│ Ctrl + o / Ctrl + i          │ Voltar atrás / avançar salto  │
│ K                            │ Ver documentação / tooltip    │
│ <Espaço>ca                   │ Ações de código / Auto-import │
│ <Espaço>cr                   │ Renomear símbolo / variável   │
├──────────────────────────────┼───────────────────────────────┤
│                     TESTES TESTNG (JAVA)                     │
├──────────────────────────────┬───────────────────────────────┤
│ <Espaço>tm                   │ Executar método @Test (Maven) │
│ <Espaço>tc                   │ Executar classe inteira(Maven)│
│ <Espaço>tx                   │ Executar suite TestNG (.xml)  │
│ <Espaço>tr                   │ Executar método nativo (DAP)  │
│ <Espaço>du                   │ Abrir DAP UI / Consola JVM    │
├──────────────────────────────┼───────────────────────────────┤
│                     TESTES PYTEST (PYTHON)                   │
├──────────────────────────────┬───────────────────────────────┤
│ <Espaço>cv                   │ Selecionar VirtualEnv (.venv) │
│ <Espaço>tt                   │ Executar teste sob o cursor   │
│ <Espaço>tr                   │ Executar ficheiro de testes   │
│ <Espaço>to                   │ Ver erro / traceback do teste │
│ <Espaço>tO                   │ Ver consola completa de testes│
│ <Espaço>tw                   │ Modo Watch (auto-run ao salvar│
├──────────────────────────────┼───────────────────────────────┤
│                            GIT                               │
├──────────────────────────────┬───────────────────────────────┤
│ <Espaço>gg                   │ Abrir Lazygit                 │
│ <Espaço>gb                   │ Ver Git Blame da linha atual  │
│ [h  /  ]h                    │ Saltar para diff anterior/seg.│
└──────────────────────────────┴───────────────────────────────┘
```
