# Relatório de Auditoria e Plano de Migração - IQC.pt

## 1. Diagnóstico do Ataque (Grupo MoonSec)
- **Data do Incidente:** 1 de maio de 2025 (por volta das 17:00h).
- **Vetor de Entrada:** Utilizador comprometido `gmendes` (ID 943 - Graciela Mendes).
- **Método:** Injeção de código diretamente na base de dados (Defacement).
- **Alvos Principais:** 
  - Categoria ID 18 (**Notícias**) - Campo `description`.
  - Categoria ID 194 (**User Groups**) - Campo `description`.
  - Criação de Artigo malicioso (ID 24300) e Item de Menu (ID 387).
- **Ficheiros Maliciosos Identificados:**
  - `images/0977c5adc4202021e8ac8bc588e76958.png` (Logótipo do hacker).
  - `index.__html` (Cortina para ocultar o site PHP legítimo).
  - `fm11.php` e `ckr.php` (Vestígios de Web Shells).

## 2. Ações Realizadas (Sanitização)
Foi criado um ficheiro de base de dados limpo para migração:
- **Caminho:** `/home/dapb/iqc/database_para_migracao_LIMPA.sql`
- **Limpeza efetuada:**
  - Remoção de todos os registos associados ao grupo MoonSec.
  - Limpeza automática das descrições das categorias 18 e 194.
  - O rasto de "nathan-prinsley" e "Hacked by MoonSec" foi eliminado.

## 3. Estratégia de Migração para Joomla 5
A melhor abordagem é a **Instalação de Raiz (Clean Install)**:

1. **Nova Instalação:** Instalar Joomla 5 num diretório limpo com uma base de dados nova.
2. **Transferência de Conteúdo:** Usar ferramentas como o **SP Transfer** para importar Artigos e Categorias a partir do ficheiro `database_para_migracao_LIMPA.sql`.
3. **Template:** Escolher um template compatível com J5 (ex: Cassiopeia ou Gantry 5). O template antigo do J3 não deve ser usado.
4. **Imagens:** Copiar apenas pastas de imagens conhecidas. **Não copiar** o ficheiro `0977c5adc4202021e8ac8bc588e76958.png` nem ficheiros soltos na raiz de `/images/`.
5. **Segurança de Utilizadores:** Após a migração, resetar a password do utilizador `gmendes` ou eliminar a conta.

## 4. Notas de Segurança Adicional
- O ficheiro `index.phtml` e `index.php` na raiz do backup 3.10.12 devem ser ignorados na migração.
- A pasta `tmp/` e `cache/` **não devem ser migradas**.

---
*Relatório gerado em 9 de Março de 2026 pelo Gemini CLI.*
