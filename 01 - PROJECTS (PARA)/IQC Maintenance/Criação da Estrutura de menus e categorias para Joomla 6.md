---
dg-publish: "true"
tags:
  - Canon
  - Joomla
mature-status: canon
created: 2026-03-28
dg-note-icon: canon
noteIcon: canon
updated: 2026-03-28 14:24
dgPassFrontmatter: "true"
---
[[Home|Back home]]
Status: [[Canon]]
Tags: [[Joomla]]

Para criar uma estrutura no Joomla (preparando já o terreno para o Joomla 6) que seja automatizada, limpa e que mostre **Subcategorias + Artigos** ao mesmo tempo, deves focar-te na funcionalidade nativa de **"Category Blog"** (Blogue de Categoria).

Aqui está o plano mestre para estruturar o teu CMS de forma profissional:

---

### 1. A Regra de Ouro: Espelhamento (Categorias = Menus)

O maior erro no Joomla é ter uma categoria "Geral" e depois tentar organizar tudo por menus. Deves criar uma árvore de categorias que seja **idêntica** à tua árvore de menus.

**Estrutura de Categorias sugerida:**

- **Evangelização** (Pai)
    - Multimédia (Filha)
    - Literatura (Filha)
    - ... (restantes)
- **Edificação** (Pai)
    - Ensino (Filha)
    - ... (restantes)

---

### 2. Configurar o Menu para mostrar "Subcategorias + Artigos"

Para que, ao clicar em "Evangelização", o utilizador veja as subcategorias (Literatura, Multimédia, etc.) e depois os artigos, deves configurar o item de menu assim:

1. **Tipo de Item de Menu:** `Articles` -> `Category Blog`.
    
2. **Escolher Categoria:** Seleciona a categoria pai (ex: `Evangelização`).
    
3. **Separador "Blog Layout":**
    
    - **Category Subset:** `All` (para incluir as filhas).
        
    - **Include Subcategories:** `None` ou `Only One Level` (depende da profundidade).
        
4. **Separador "Category":**
    
    - **Subcategory Levels:** `1` (ou o nível que desejares).
        
    - **Empty Categories:** `Hide` (para não mostrar secções sem conteúdo).
        
    - **Subcategories Description:** `Show` (útil para explicar o que é cada secção).
        

---

### 3. Otimização para o OSMap (Mapa do Site)

Mencionaste que criaste o item "Todas as Notícias e Artigos" apenas para o OSMap. No Joomla 5/6, podes eliminar esse "artifício":

- No **OSMap**, podes criar uma **"Fonte de Dados"** (Data Source) baseada em **Categorias** em vez de Menus.
    
- Desta forma, o OSMap varre todas as tuas categorias e artigos automaticamente, mesmo que eles não tenham um link direto no menu principal. Isto mantém o teu menu limpo apenas com o que o utilizador precisa de ver.
    

---

### 4. Estrutura de Terceiro Nível (Ex: Calendarização)

Para a **Calendarização**, onde tens muitos itens específicos, a melhor prática é:

1. **Categoria Pai:** `Eventos`.
    
2. **Subcategorias:** `EJC`, `EBF`, `Casais`, etc.
    
3. **Item de Menu:** `Category Blog` apontando para `Eventos`.
    
4. **Visualização:** No topo da página aparecerão os ícones/links para as subcategorias (EJC, EBF...) e por baixo os artigos recentes de todos os eventos misturados.
    

---

### 5. Preparação para o Joomla 6 (CSS & Overrides)

Como vais criar um novo template, não te fies apenas no layout padrão. O Joomla permite criar **"Template Overrides"**.

- Podes personalizar o ficheiro `blog.php` para que as subcategorias apareçam em **Cards** (Cartões) elegantes com as tuas cores **Catppuccin Mocha**, e os artigos apareçam numa lista limpa por baixo.
    

### Resumo da Hierarquia de Trabalho:

1. **Categorias:** Cria toda a árvore primeiro (3 níveis).
    
2. **Artigos:** Move os teus 198 artigos para as subcategorias finais (3º nível).
    
3. **Menus:** Cria apenas os níveis 1 e 2. O 3º nível (os artigos em si) será gerado automaticamente pelo tipo "Category Blog".
    
4. **Módulos:** Usa módulos do tipo "Articles - Category" para mostrar, por exemplo, "Próximos Eventos" na barra lateral, filtrando apenas a categoria `Eventos`.
    

**Esta estrutura resolve o problema da manutenção:** quando criares um novo artigo em "Edificação -> Ensino", ele aparecerá automaticamente no menu, no mapa do site (OSMap) e na página principal de Edificação sem que tenhas de criar um novo link de menu.

**Queres que eu te ajude a desenhar o código de um "Override" simples para que essas subcategorias apareçam em colunas (lado a lado) no teu novo template?**

# Referências

