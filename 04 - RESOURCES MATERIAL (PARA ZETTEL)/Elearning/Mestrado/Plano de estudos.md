Esta unidade curricular é **Análise e Visualização de Dados** (idUC: 16032) do **Mestrado em Engenharia de Software**do IPS.

Abaixo, tens o plano completo de estudos, estruturado para que consigas dominar todos os tópicos da disciplina.

## 📊 Visão Geral e Estrutura da UC

- **Regime de Ensino:** B-learning (aulas presenciais, síncronas e assíncronas no Moodle).
    
- **Método de Avaliação:**
    
    - **30% - Atividades Assíncronas:** Fóruns, questionários e tarefas no Moodle.
        
    - **40% - Projeto Prático:** Desenvolvido em grupo.
        
    - **30% - Teste / Exame:** Componente de avaliação individual.
        

## 🗓️ Cronograma de Estudos e Conteúdos

Este plano está dividido em **4 grandes blocos** que cobrem todo o programa oficial.

### Bloco 1: Metodologias e Ciclo de Vida de Projetos de Dados

- **Teoria:** Frameworks de desenvolvimento de projetos de análise de dados (ex: CRISP-DM). Compreensão das etapas de um projeto (de engenharia de dados até à entrega do painel informativo).
    
- **Exercício Recomendado:** Desenha o fluxo de trabalho de um cenário de negócio real (ex: análise de faturação de uma e-commerce), identificando os requisitos, as fontes de dados e os utilizadores finais.
    
- **Atividade Moodle (30%):** Responder aos fóruns de discussão sobre o alinhamento de objetivos de negócio com o desenvolvimento de dashboards.
    

### Bloco 2: Modelação Dimensional e Desenho Físico

- **Teoria:** Conceitos de modelação dimensional. Tabelas de factos (_Fact tables_) e tabelas de dimensões (_Dimension tables_). Esquemas em Estrela (_Star Schema_) vs. Esquemas em Floco de Neve (_Snowflake Schema_). Desenho físico de estruturas de dados e técnicas de otimização de consultas.
    
- **Exercício Recomendado:** Desenhar um modelo dimensional em estrela no papel ou ferramenta de diagramas (ex: draw.io) para uma base de dados transacional de vendas.
    
- **Atividade Moodle (30%):** Questionário conceitual sobre normalização vs. desnormalização em armazéns de dados.
    

### Bloco 3: Engenharia de Dados (O Processo ETL)

- **Teoria:** O processo ETL (Extração, Transformação e Carregamento): requisitos específicos, etapas e as ferramentas populares do mercado (como SQL Server Integration Services, Talend ou o próprio Power Query integrado no Power BI). Implementação de operações de limpeza e transformação de dados para garantir a qualidade da análise.
    
- **Exercício Recomendado:** Criar um script ou usar uma ferramenta de preparação de dados para limpar dados duplicados, tratar valores nulos e unificar tabelas de vendas distintas.
    
- **Atividade Moodle (30%):** Exercício prático assíncrono para validação de integridade de dados após carga.
    

### Bloco 4: Visualização e Storytelling de Dados

- **Teoria:** Design e boas práticas de representação visual de dados. Escolha do gráfico ideal de acordo com os dados.Construção de dashboards interativos integrando filtros, hierarquias e navegação fluida.
    
- **Exercício Recomendado:** Construir as visualizações fundamentais para responder às perguntas do Bloco 1 de forma visualmente apelativa e clara.
    

## 🎯 Projeto Prático (40% da Nota)

O projeto final deve ser construído simulando uma solução de ponta a ponta para um cenário de negócio.

**1.Fase 1: Levantamento e Requisitos:**Semana 1.

Identifica as necessidades de negócio, as fontes de dados iniciais e define as principais perguntas que o dashboard deve responder.

**2.Fase 2: ETL e Preparação:**Semana 2.

Carrega os dados e aplica as transformações necessárias para limpar imperfeições, gerir nulos e garantir a qualidade estrutural.

**3.Fase 3: Modelação Dimensional:**Semana 3.

Desenha o teu modelo dimensional (de preferência um Star Schema) interligando as chaves primárias e estrangeiras.

**4.Fase 4: Visualização e Teste:**Semana 4.

Desenha o painel em Power BI, Tableau ou similar. Adiciona interatividade (filtros transversais, botões) e valida se as métricas estão corretas.

## 📝 Simulação de Teste Teórico (30% da Nota)

Prepara-te para a componente de avaliação escrita com estas questões de estudo baseadas no programa oficial:

1. **(Modelação)** Explique a diferença entre tabelas de dimensão e tabelas de factos e dê um exemplo prático de cada uma num contexto de saúde hospitalar.
    
2. **(ETL)** Qual a importância da fase de "Transformação" no pipeline ETL no que toca à promoção da qualidade da análise final?
    
3. **(Visualização)** Se o seu objetivo é comparar a evolução trimestral da margem de lucro de três categorias de produtos nos últimos dois anos, qual o gráfico mais adequado e porquê?


Para pores em prática tudo o que vais aprender na UC de **Análise e Visualização de Dados** do IPS, o ideal é trabalhares com ferramentas e bases de dados que reflitam o mercado real, mas que sejam **100% gratuitas**.

Abaixo, tens os ambientes e recursos recomendados para cada etapa do teu plano de estudos:

## 🛠️ 1. Ferramentas de ETL e Visualização (As Estrelas do Programa)

Como a UC aborda desde a preparação até ao dashboard final, estas duas ferramentas cobrem todo o espectro de forma gratuita:

- **Microsoft Power BI Desktop:**
    
    - **O que é:** A ferramenta de Business Intelligence (BI) líder de mercado.
        
    - **Por que usar:** É **totalmente gratuita** para criar relatórios localmente no teu computador. Inclui o **Power Query** (que vais usar para fazer toda a parte de ETL/limpeza de dados do Bloco 3) e o motor de modelação para criar o teu _Star Schema_ (Bloco 2).
        
- **Tableau Public:**
    
    - **O que é:** A versão gratuita e baseada na web do Tableau.
        
    - **Por que usar:** Excelente para treinar o Bloco 4 (Design e Storytelling). Permite publicar os teus trabalhos num portfólio online (ideal para mostrares em entrevistas de emprego), embora te obrigue a guardar os dados na nuvem pública da Tableau.
        

## 💾 2. Bases de Dados de Teste (Dados Reais para Praticar)

Não precisas de inventar dados no Excel. Podes descarregar bases de dados relacionais e dimensionais completas e profissionais:

- **Bases de Dados Oficiais da Microsoft (Formato SQL Server / .bak):**
    
    - **AdventureWorksDW:** O clássico dos clássicos. É um armazém de dados (_Data Warehouse_) já estruturado em modelação dimensional (com tabelas `FactInternetSales`, `DimCustomer`, `DimProduct`, etc.). É perfeita para começares logo a praticar a criação de relatórios no Power BI sem teres de fazer grandes limpezas.
        
    - **WideWorldImportersDW:** Uma alternativa mais moderna ao AdventureWorks, que simula uma empresa importadora e distribuidora de produtos em tempo real.
        
- **Kaggle (Dataset Hub):**
    
    - **O que é:** Se preferires trabalhar com ficheiros CSV ou Excel para treinar a fase de **ETL** (limpar dados sujos, tratar nulos), o Kaggle tem milhões de datasets gratuitos sobre qualquer tema (desde dados do Spotify a estatísticas de futebol ou vendas de retalho).
        

## 💻 3. Onde alojar e gerir bases de dados locais?

Se o teu projeto exigir que cries ou consultes bases de dados via SQL antes de as pores no Power BI:

- **SQL Server Developer Edition:** Uma versão gratuita e completa do SQL Server para fins de desenvolvimento e aprendizagem.
    
- **DBeaver Community / pgAdmin:** Ferramentas gratuitas e intuitivas para gerires e fazeres consultas (queries) SQL a qualquer base de dados.
    

## 🎓 Como estruturar o teu laboratório de prática?

Para aproveitares ao máximo estes recursos, segue este fluxo de trabalho básico no teu computador:

```
[Base de Dados do Kaggle (CSV) ou AdventureWorksDW] 
                     │
                     ▼
  [Power BI Desktop (Power Query para ETL)] 
                     │
                     ▼
  [Modelação de Relações (Esquema em Estrela)] 
                     │
                     ▼
[Desenho de Dashboard Interativo com KPIs reais]
```

Se precisares de ajuda para descarregar o _AdventureWorksDW_ ou para dar os primeiros passos no Power Query do Power BI, diz-me por onde queres começar!


O **Power Query** é o "motor" por trás do Power BI responsável por todo o processo de **ETL** (Extração, Transformação e Carregamento). É nele que vais limpar dados desalinhados, remover duplicados, filtrar colunas e preparar a informação para que a tua modelação dimensional (o teu _Star Schema_) funcione na perfeição.

A grande vantagem? O Power Query regista todos os passos de limpeza que fazes. Da próxima vez que atualizares os teus dados, ele repete tudo automaticamente com um só clique!

Abaixo, tens um guia visual e prático para dares os teus primeiros passos.

## 🧭 O Ambiente do Power Query

Quando clicas em **"Transformar Dados"** (Transform Data) no menu principal do Power BI Desktop, abre-se uma nova janela. Este é o editor do Power Query.

A interface está dividida em 4 áreas fundamentais:

1. **Friso Superior (Ribbon):** Onde encontras os botões para as transformações mais comuns (Dividir Colunas, Filtrar, Agrupar, etc.).
    
2. **Painel de Consultas (Queries - Esquerda):** Mostra todas as tabelas ou fontes de dados que importaste.
    
3. **Painel de Pré-visualização (Centro):** Uma amostra das primeiras 1000 linhas dos teus dados para veres o impacto das tuas transformações.
    
4. **Etapas Aplicadas (Applied Steps - Direita):** **A funcionalidade mais importante!** Funciona como um histórico. Cada ação que fazes (ex: remover uma coluna) adiciona uma etapa à lista. Podes clicar no "X" ao lado de qualquer etapa para a apagar e desfazer o erro.
    

## 🛠️ As 5 Transformações Essenciais (O Teu Primeiro Laboratório)

Para começares a praticar, descarrega qualquer ficheiro Excel ou CSV simples (por exemplo, dados de vendas do Kaggle) e experimenta fazer estas 5 operações básicas:

### 1. Corrigir os Tipos de Dados

O Power Query tenta adivinhar o tipo de dado de cada coluna (Número, Texto, Data), mas às vezes erra (ex: ler códigos postais ou IDs como números em vez de texto).

- **Como fazer:** Clica no pequeno ícone ao lado do nome da coluna (ex: `1.2` para decimais, `ABC` para texto) e escolhe o tipo correto.
    

### 2. Promover a Primeira Linha a Cabeçalho

Muitas vezes, ao importar ficheiros Excel, os nomes das colunas aparecem na primeira linha de dados e os cabeçalhos ficam genéricos como "Coluna 1", "Coluna 2".

- **Como fazer:** No friso inicial, clica no botão **"Usar Primeira Linha como Cabeçalho"** (Use First Row as Headers).
    

### 3. Dividir Colunas (Split Column)

Imagina que tens uma coluna chamada "Nome Completo" e queres separar em "Primeiro Nome" e "Último Nome", ou tens uma coluna "Data-Hora" e queres apenas a data.

- **Como fazer:** Clica com o botão direito no topo da coluna -> **Dividir Coluna** -> **Por Delimitador** (ex: espaço, vírgula, hífen).
    

### 4. Remover Colunas Desnecessárias e Filtrar Linhas

Ter colunas vazias ou dados que não interessam para a análise (ex: transações antigas ou com erro) torna o teu relatório pesado.

- **Como fazer:** * Seleciona as colunas que não precisas, clica com o botão direito e escolhe **Remover** (ou seleciona as que queres manter e escolhe _Remover Outras Colunas_).
    
    - Usa as setas de filtro no cabeçalho das colunas para retirar linhas vazias (_Nulls_) ou valores indesejados.
        

### 5. Substituir Valores (Replace Values)

Muito útil para limpar erros de digitação (ex: substituir "Pt" por "Portugal") ou para preencher células em branco.

- **Como fazer:** Clica com o botão direito na coluna -> **Substituir Valores** -> Introduz o valor a localizar e o novo valor.
    

## 🚀 O Teu Primeiro Exercício Prático

Experimenta simular este cenário para treinares a lógica de **Engenharia de Dados (ETL)**:

1. Cria um ficheiro Excel no teu computador com uma tabela de clientes fictícios (de propósito, escreve alguns nomes com espaços a mais, deixa algumas idades em branco e escreve "M" e "Masculino" na coluna de género).
    
2. Abre o Power BI, clica em **Obter Dados (Get Data) -> Excel** e seleciona o teu ficheiro.
    
3. Clica em **Transformar Dados** (não em Carregar!).
    
4. No Power Query, tenta:
    
    - **Limpar espaços em branco** no início e fim dos nomes (Clica na coluna de Texto -> Separador _Transformar_ -> _Formatar_ -> _Aparar / Trim_).
        
    - **Substituir valores** para uniformizar a coluna de género (deixar tudo como "Masculino" ou "Feminino").
        
    - **Filtrar as linhas** onde a idade está em branco (_null_).
        
5. Quando terminares, clica em **Fechar e Aplicar** (Close & Apply) no canto superior esquerdo. Os teus dados limpos estão agora prontos para serem usados nos teus gráficos!