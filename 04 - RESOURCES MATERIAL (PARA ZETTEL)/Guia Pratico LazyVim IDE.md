# 🚀 Guia Definitivo: Neovim + LazyVim como IDE para Automação de Testes (Java & Python) e Git

Este guia prático e consolidado reúne todas as instruções, configurações, resolução de problemas e atalhos para usar o **Neovim (LazyVim)** como ambiente de desenvolvimento de excelência para testes automatizados com **Java (TestNG + Selenide)** e **Python (Pytest)**, com gestão de versões via **Git/Lazygit** sem depender do rato.

---

## 📌 1. Filosofia e Tecla Mestre

* **Tecla Líder (`<leader>`)**: No LazyVim é a **`<Barra de Espaço>`**.
* **Menu Interativo (*which-key*)**: Ao carregar em `<Espaço>` e aguardar meio segundo, surge uma janela no rodapé com todos os atalhos disponíveis agrupados por contexto (`f` para ficheiros, `c` para código, `t` para testes, `g` para git, etc.).
* **Regra de Ouro**: Manter as mãos no teclado. A navegação baseia-se em `h, j, k, l`, `w, b` e saltos rápidos.

---

## 🛠️ 2. Instalação e Requisitos no Ubuntu

### Dependências de Sistema e Ferramentas CLI
```bash
sudo apt update
sudo apt install -y build-essential ripgrep fd-find unzip curl git openjdk-21-jdk maven python3-venv
```

Criar o alias para o `fd`:
```bash
mkdir -p ~/.local/bin
ln -s $(which fdfind) ~/.local/bin/fd
```

### Neovim Oficial ($\ge 0.10$)
> [!IMPORTANT]
> O pacote do `apt` no Ubuntu 24.04 instala a versão 0.9.5, que é incompatível com o LazyVim atual. Usa o binário oficial mais recente:

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

## 🗂️ 3. Navegação e Gestão de Janelas (Buffers & Splits)

* `<Espaço><Espaço>` ou `<Espaço>ff`: Procura rápida de ficheiro pelo nome (*Fuzzy finder*).
* `<Espaço>/` ou `<Espaço>sg`: Pesquisa de texto em todos os ficheiros do projeto (*Live Grep*).
* `<Espaço>e`: Abre/fecha o explorador de ficheiros (Neo-tree).
  * Na árvore: `a` para criar ficheiro/pasta, `d` para apagar, `r` para renomear.
* `Shift + h` / `Shift + l`: Alternar entre abas/ficheiros abertos na barra superior.
* `<Espaço>bd`: Fechar o ficheiro (buffer) atual.
* `<Espaço>|`: Dividir a janela verticalmente.
* `<Espaço>-`: Dividir a janela horizontalmente.
* `Ctrl + h / j / k / l`: Mover o cursor entre janelas divididas.

---

## 🌿 4. Git, Lazygit e Resolução de Erros

### Operações com Lazygit
* **`<Espaço>gg`**: Abre a interface gráfica de terminal do Lazygit.
  * `Espaço`: Adiciona ou retira do stage ficheiros ou linhas selecionadas.
  * `c`: Abre o prompt para escrever a mensagem de commit.
  * `Shift + p` (`P`): Efetua `git push`.
  * `p`: Efetua `git pull`.
  * `r`: Faz rebase sobre a branch selecionada.
  * `q` ou `Esc`: Sai do Lazygit e regressa ao código.

### Passphrase de Chave SSH (`id_rsa` / `id_ed25519`)
Para evitar que o Git e o Lazygit peçam a senha constantemente ou bloqueiem:
```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
```

### Resolução de Erros de Permissão / Rebase (`Permission denied`)
Se o Git falhar ao atualizar ficheiros (ex: pasta `.idea` ou repositórios criados com `root`):
```bash
# 1. Devolver a posse da pasta ao teu utilizador habitual
sudo chown -R $USER:$USER ~/caminho/para/o/projeto

# 2. Cancelar o rebase interrompido
git rebase --abort

# 3. Executar o rebase limpo
git pull --rebase origin main
```

---

## 🧩 5. Manutenção, Diagnóstico & Plugins de IA

### Desinstalar Plugins e Extras Desnecessários
* **Pelo Menu Visual**: Escreve `:LazyExtras`, posiciona o cursor sobre o plugin ativo e prime **`x`**. Depois, corre `:Lazy` e prime **`X`** (Shift + x) para limpar os ficheiros do disco.
* **Pelo ficheiro de configuração**: Edita diretamente o [lazyvim.json](file:///home/dapb/.config/nvim/lazyvim.json) e remove as linhas dos módulos indesejados.

### Plugins de IA: `ai.copilot` vs `ai.copilot-native` vs Copilot 365
* **`ai.copilot`**: Módulo recomendado. Desenvolvido em Lua nativo (`copilot.lua`), oferece suporte a sugestões em texto fantasma (*ghost text*) e integra-se diretamente com o chat do **`ai.copilot-chat`**.
* **`ai.copilot-native`**: Plugin clássico em Vimscript mantido pelo GitHub; entra em conflito se estiver ativado junto com o `ai.copilot`.
* **Copilot 365 vs GitHub Copilot**: O Microsoft Copilot para Microsoft 365 destina-se a aplicações Office (Word, Teams, Excel) e não suporta editores de código. O Neovim integra exclusivamente com o **GitHub Copilot** (autenticação com `:Copilot auth`).
* **Alternativa Gratuita**: O extra **`ai.codeium`** fornece autocompletar gratuito para programadores individuais (ativação com `:Codeium Auth`).

---

## ☕ 6. Automação de Testes em Java (TestNG + Selenide)

### Configuração no LazyVim
Confirma que tens os seguintes módulos ativos:
* Em `:LazyExtras`: `lang.java`, `test.core` e `dap.core`.
* Em `:Mason`: `java-debug-adapter` e `java-test`.

### Atalhos Configurados no `keymaps.lua`

Os seguintes atalhos foram configurados no teu [keymaps.lua](file:///home/dapb/.config/nvim/lua/config/keymaps.lua):

| Atalho | Ação | Como funciona |
| :--- | :--- | :--- |
| **`<Espaço>tm`** | **Executar Método `@Test` Atual** | Usa o Treesitter para extrair o nome do método onde o cursor está e corre: `mvn test -Dtest=Classe#metodo` no terminal flutuante. |
| **`<Espaço>tc`** | **Executar Classe de Teste Inteira** | Corre `mvn test -Dtest=Classe` via Maven. |
| **`<Espaço>tx`** | **Executar Suite XML TestNG Atual** | Quando estás num ficheiro `.xml` (ex: `testng.xml`), corre: `mvn clean test -DsuiteXmlFile=ficheiro.xml`. |
| **`<Espaço>tr`** | **Executar Teste mais Próximo (DAP)** | Motor nativo do JDTLS sem abrir terminal externo. |
| **`<Ctrl-/>`** | **Fechar Terminal Flutuante** | Oculta/recolhe a consola de execução do Maven. |

### Configuração no `pom.xml` para Suites XML
Para suportar o parâmetro `-DsuiteXmlFile` dinâmico:
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
Por padrão, o Selenide abre o browser visualmente. Para execução silenciosa em segundo plano:
```java
import com.codeborne.selenide.Configuration;

Configuration.headless = true;
```

---

## 🐍 7. Automação de Testes em Python (Pytest)

### Configuração
O LazyVim inclui os módulos `lang.python` e `test.core` com o adaptador `neotest-python`.

### Seleção do VirtualEnv (Crítico)
* **`<Espaço>cv`** (*Code $\rightarrow$ Select VirtualEnv*): Abre a seleção automática de pastas `.venv`, Poetry ou Conda para que o LSP e o Pytest usem as dependências do projeto.

### Atalhos Neotest para Pytest
| Atalho | O que faz |
| :--- | :--- |
| **`<Espaço>tr`** | Executa todos os testes do **ficheiro atual** (*Run File*). |
| **`<Espaço>tt`** | Executa a **função/teste sob o cursor** (*Run Nearest*). |
| **`<Espaço>ts`** | Abre a barra lateral com a **árvore e sumário de testes** (*Toggle Summary*). |
| **`<Espaço>to`** | Abre janela flutuante com a **mensagem de erro e traceback** (*Output*). |
| **`<Espaço>tO`** | Abre o painel inferior com a consola completa do Pytest. |
| **`<Espaço>tw`** | **Modo Watch** (TDD): corre o teste automaticamente sempre que gravas (`:w`). |
| **`<Espaço>dPt`**| Inicia a execução do teste em modo **Debug** com breakpoints (*DAP*). |

---

## ⚡ 8. Tabela de Consulta Rápida (Cheat Sheet Geral)

```
┌──────────────────────────────────────────────────────────────┐
│                    NAVEGAÇÃO & GERAL                         │
├──────────────────────────────┬───────────────────────────────┤
│ <Espaço><Espaço>             │ Encontrar ficheiro            │
│ <Espaço>sg                   │ Pesquisar texto em ficheiros  │
│ <Espaço>e                    │ Explorador de pastas/ficheiros│
│ Shift + h / Shift + l        │ Alternar abas/buffers         │
│ Ctrl + /                     │ Abrir/fechar terminal rápido  │
├──────────────────────────────┼───────────────────────────────┤
│                        CÓDIGO (LSP)                          │
├──────────────────────────────┬───────────────────────────────┤
│ gd                           │ Ir para a definição           │
│ K                            │ Ver documentação / tooltip    │
│ <Espaço>ca                   │ Ações de código / Auto-import │
│ <Espaço>cr                   │ Renomear variável / método    │
│ <Espaço>cf                   │ Formatar código               │
├──────────────────────────────┼───────────────────────────────┤
│                     TESTES TESTNG (JAVA)                     │
├──────────────────────────────┬───────────────────────────────┤
│ <Espaço>tm                   │ Executar método @Test (Maven) │
│ <Espaço>tc                   │ Executar classe inteira(Maven)│
│ <Espaço>tx                   │ Executar suite TestNG (.xml)  │
│ <Espaço>tr                   │ Executar método nativo (DAP)  │
├──────────────────────────────┼───────────────────────────────┤
│                     TESTES PYTEST (PYTHON)                   │
├──────────────────────────────┬───────────────────────────────┤
│ <Espaço>cv                   │ Selecionar VirtualEnv (.venv) │
│ <Espaço>tt                   │ Executar função de teste      │
│ <Espaço>tr                   │ Executar ficheiro de testes   │
│ <Espaço>ts                   │ Sumário da suite (Painel)     │
│ <Espaço>to                   │ Ver traceback/erro detalhado  │
│ <Espaço>tw                   │ Modo Watch (auto-run ao salvar│
├──────────────────────────────┼───────────────────────────────┤
│                            GIT                               │
├──────────────────────────────┬───────────────────────────────┤
│ <Espaço>gg                   │ Abrir Lazygit                 │
│ <Espaço>gb                   │ Ver Git Blame da linha atual  │
│ [h  /  ]h                    │ Saltar para diff anterior/seg.│
└──────────────────────────────┴───────────────────────────────┘
```
