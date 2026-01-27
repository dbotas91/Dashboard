---
tags:
  - elearning
dg-publish: "true"
dg-note-icon: lackluster
noteIcon: lackluster
---
![](Dashboard/Attachments/icons_notes--sentence%207.png)

# 2. Medidas de Localização

|   |   |
|---|---|
|![](Dashboard/Attachments/arrow-northeast_gray%201178.svg)Subject|[![](Dashboard/Attachments/icons_graduate%207.png)2.Estatística Descritiva - Organização e interpretação de dados](../Subjects/2%20Estat%C3%ADstica%20Descritiva%20-%20Organiza%C3%A7%C3%A3o%20e%20interpret%20179774eadd644777924295c57b6ce4f5.html)|
|![](Dashboard/Attachments/calendar_gray%201240.svg)Date Created|@June 10, 2022|
|![](Dashboard/Attachments/checkmark-square_gray%20659.svg)To Review?||
|![](Dashboard/Attachments/formula_gray%20478.svg)Review Due||
|![](Dashboard/Attachments/clock_gray%20110.svg)Last Edited|@June 25, 2022 5:55 PM|

[Medidas de Localização](#dc68815e-475f-4785-a0bf-4e9a3c7e5204)

[Moda](#49da77ad-a27d-42f8-b8fa-79355ccb816f)

[Dados agrupados em classes (todas as classes com a mesma amplitude)](#1d1f683a-92d1-4d82-9be7-d3933a406a9b)

[Média](#29ceeb02-3b21-45da-ab0d-2278c5e9a3c2)

[Dados em tabelas de frequências - Não estão agrupados em Classes](#205d1d9c-bde4-4a9d-8044-02dc5a4bcf2f)

[Dados em tabelas de frequências - Estão agrupados em Classes](#55855737-531b-43a1-adc9-81753ae862b2)

[Quantis](#38acb7a3-1a22-4ff6-9577-af8214157ab9)

[Mediana](#e4e27917-b9f4-4df1-97a1-979a29b6d9be)

[Dados em Tabelas de Frequências - Não Estão Agrupados em Classes](#50af6526-75c8-49ab-8b11-62dc861e310b)

[Dados em Tabelas de Frequências - Estão Agrupados em Classes](#4e67880e-1a29-498f-a21d-4ac6f268dd3c)

[Quartis](#6f5f6603-8c50-4d81-a208-30d26575c31b)

# Medidas de Localização

Permitem resumir os dados calculando algumas características numéricas de modo a ter informação sobre a sua localização:

- Medidas de **localização central**:
    
    - moda,
    
    - Média,
    
    - Mediana.

- Medidas de **localização não central**:
    - quantis.

## Moda

- Habitualmente representa-se por _mo._

- Para dados não agrupados, a moda define-se como o valor mais frequente.

- Para dados agrupados em classes (todas as classes com a mesma apmlitude), a classe com maior frequência diz-se a **classe modal**.

- Um conjunto de dados pode não ter moda e diz-se **amodal**.

- Um conjunto de dados pode ter mais que uma moda. Isto acontece quando há dois ou mais valores que têm a maior frequência e diz-se
    
    - **Bimodal** se tem duas modas;
    
    - **Multimodal** ou **plurimodal** se tem mais do que duas modas.

### Dados agrupados em classes (todas as classes com a mesma amplitude)

- A classe com maior frequência diz-se a **classe modal**.

- Ao valor central da classe modal chama-se **valor modal**. O **valor modal** é um possível valor para a moda (a chamada moda bruta).

- Outra forma de calcular um valor aproximado para a moda é a chamada **moda pelo método de King**:
    
    moda≈ximin+(ximax−ximin)×fi+1fi−1+fi+1moda \approx x_i^{min}+(x_i^{max}-x_i^{min})\times \frac{f_{i+1}} {f_{i-1}+f_{i+1}}moda≈ximin​+(ximax​−ximin​)×fi−1​+fi+1​fi+1​​﻿
    

Onde ximinx_i^{min}ximin​﻿ é o limite inferior da classe modal, ximaxx_i^{max}ximax​﻿ é o limite superior da classe modal, fi−1f_{i-1}fi−1​﻿ e fi+1f_{i+1}fi+1​﻿ são as frequências relativas, respetivamente, da classe anterior e da classe posterior à classe modal.

## Média

- Representa-se por x‾\overline {x}x﻿ (quando os dados correspondem a uma amostra) ou por μ\mu μ﻿ (quando os dados correspondem à população).

- A média é a medida de localização central mais utilizada, sendo muitas vezes usada como valor “representativo” de um conjunto de dados.

- A **média** define-se como o quociente entre a soma de todos os valores observados e o número de elementos da amostra.  
    Isto é, seja {x1,x2,…,xn{x_1 , x_2, … , x_n}x1​,x2​,…,xn​﻿} um conjunto de dados com o n observações, define-se média aritmética, ou simplesmente **média**, como  
    x‾=x1+x2+…+xn=∑i=1nxin\overline {x} = x_1 + x_2 + … + x_n = \frac {\sum_{i=1}^{n} {x_i}} {n}x=x1​+x2​+…+xn​=n∑i=1n​xi​​﻿

- Não existe média quando a variável é qualitativa.

### Dados em tabelas de frequências - Não estão agrupados em Classes

x‾={n1×x1+n2×x2+...+nk×xkn=∑i=1knixin , frequeˆncias absolutasf1×x1+f2×x2+...+fk×xk=∑i=1kfixi , frequeˆncias relativas\overline {x} = \begin{cases} \text{$\frac{n_1\times x_1+n_2\times x_2+...+n_k \times x_k}{n} = \frac{\sum_{i=1}^k{n_ix_i}}{n}$ , frequências absolutas}\\ \text{$f_1 \times x_1+ f_2 \times x_2+...+ f_k \times x_k = \sum_{i=1}^k f_ix_i$ , frequências relativas}\\ \end{cases} x={nn1​×x1​+n2​×x2​+...+nk​×xk​​=n∑i=1k​ni​xi​​ , frequeˆncias absolutasf1​×x1​+f2​×x2​+...+fk​×xk​=∑i=1k​fi​xi​ , frequeˆncias relativas​﻿

### Dados em tabelas de frequências - Estão agrupados em Classes

x‾≈{n1×x1′+n2×x2′+...+nk×xk′n=∑i=1knixi′n , frequeˆncias absolutasf1×x1′+f2×x2′+...+fk×xk′=∑i=1kfixi′ , frequeˆncias relativas\overline {x} \approx \begin{cases} \text{$\frac{n_1\times x_1^{'}+n_2\times x_2^{'} +...+n_k \times x_k ^{'}}{n} = \frac{\sum_{i=1}^k{n_ix_i^{'}}}{n}$ , frequências absolutas}\\ \text{$f_1 \times x_1^{'}+ f_2 \times x_2^{'}+...+ f_k \times x_k^{'} = \sum_{i=1}^k f_ix_i^{'}$ , frequências relativas}\\ \end{cases}x≈{nn1​×x1′​+n2​×x2′​+...+nk​×xk′​​=n∑i=1k​ni​xi′​​ , frequeˆncias absolutasf1​×x1′​+f2​×x2′​+...+fk​×xk′​=∑i=1k​fi​xi′​ , frequeˆncias relativas​﻿

- Quando os dados estão agrupados em classes, o valor obtido para a média é um valor aproximado, uma vez que esta é calculada com base no representante da classe (xi‘x_i^{‘}xi‘​﻿).

- A média de uma amostra apenas dá uma ideia da ordem de grandeza dos elementos da população, pois apenas é calculada com base nos elementos que foram incluídos na amostra.

- A média é muito sensível a valores extremos (muito grandes ou muito pequenos) dizendo-se por isso que é uma medida pouco resistente. Em alguns casos, a média pode não ser “representativa” de um conjunto de dados.

## Quantis

- Representa-se por QpQ_pQp​﻿.

- Dado um número 0≤p≤10 ≤ p ≤ 10≤p≤1﻿, define-se quantil de ordem ppp﻿, QpQ_pQp​﻿, como o valor contido no intervalo de variação das observações tal que, pelo menos p×100p \times 100p×100﻿% das observações são maiores ou iguais a esse valor.

- Seja {x1,x2,…,xnx_1, x_2,…,x_nx1​,x2​,…,xn​﻿} um conjunto de dados com nnn﻿ observações e seja {x(1),x(2),…,x(n)x_{(1)},x_{(2)},…,x_{(n)}x(1)​,x(2)​,…,x(n)​﻿} o mesmo **conjunto ordenado**.

Qp={x(np)+x(np+1)2 , se np eˊ inteirox(⌊np⌋+1) , se np na˜o eˊ inteiroQ_p = \begin{cases} \text{$\frac{x_{(np)} + x_{(np+1)}}{2}$ , se $np$ é inteiro}\\ \text{$x_{(\lfloor np \rfloor +1)}$ , se $np$ não é inteiro}\\ \end{cases}Qp​={2x(np)​+x(np+1)​​ , se np eˊ inteirox(⌊np⌋+1)​ , se np na˜o eˊ inteiro​﻿

Onde ⌊a⌋\lfloor a \rfloor⌊a⌋﻿ representa a parte inteira de aaa﻿.

- Alguns quantis são muito usados e têm nomes específicos:
    
    - **Quartis** - dividem a amostra em 4 partes iguais
        
        - 1º quartil = Q1Q_1Q1​﻿ = Q0.25Q_{0.25}Q0.25​﻿
        
        - 2º quartil = Q2Q_2Q2​﻿ = Q0.50Q_{0.50}Q0.50​﻿ = mediana
        
        - 3º quartil = Q3Q_3Q3​﻿ = Q0.75Q_{0.75}Q0.75​﻿
    
    - **Decis** - dividem a amostra em 10 partes iguais
        
        - 1º decil = D1D_1D1​﻿ = Q0.10Q_{0.10}Q0.10​﻿
        
        - 2º decil = D2D_2D2​﻿ = Q0.20Q_{0.20}Q0.20​﻿
        
        - …
        
        - 8º decil = D8D_8D8​﻿ = Q0.80Q_{0.80}Q0.80​﻿
        
        - 9~º decil = D9D_9D9​﻿ = Q0.90Q_{0.90}Q0.90​﻿
    
    - **Percentis** - dividem a amostra em 100 partes iguais
        
        - 1º percentil = P1P_1P1​﻿ = Q0.01Q_{0.01}Q0.01​﻿
        
        - 2º percentil = P2P_2P2​﻿ = Q0.02Q_{0.02}Q0.02​﻿
        
        - …
        
        - 98º percentil = P98P_{98}P98​﻿ = Q0.98Q_{0.98}Q0.98​﻿
        
        - 99º percentil = P99P_{99}P99​﻿ = Q0.99Q_{0.99}Q0.99​﻿

Mediana

- Um Dos quantis mais importantes e mais utilizado em estatística é  
    2º quartil = Q2Q_2Q2​﻿ = Q0.50Q_{0.50}Q0.50​﻿ = mediana

- Habitualmente representa-se por x~\tilde xx~﻿ ou mememe﻿

- **A mediana** é o valor que ocupa a posição central quando se ordenam os dados estatísticos. Isto é, a mediana é o valor que separa as 50% das observações inferiores das 50% superiores. Por este motivo a mediana é considerada uma **medida de localização central**.

- A mediana e determinada pelo número de observações e não pelos seus valores, não sendo afetada por valores extremos. Diz-se, por isso, que é mais resistente do que a média.

- Quando nos referimos aos quantis no geral, diz-se que são medidas de **localização não central** (a única exceção é a mediana que é uma medida de localização central).

- Para determinar os quantis é necessário ordenar por ordem crescente as observações, pelo que não existem quantis quando a variável é qualitativa. No entanto há quem considere que é possível calcular quantis no caso da variável ser qualitativa ordinal.

- Os quantis são determinados pelo número de observações e não pelos seus valores, não sendo afetados por valores extremos.

### Dados em Tabelas de Frequências - Não Estão Agrupados em Classes

No caso dos **dados organizados numa tabela**, os quantis podem ser determinados a partir dos valores da frequência relativa acumulada.

- Se existir um valor com frequência relativa acumulada igual a ppp﻿, o quantil é a média aritmética entre esse valor e o seguinte.

- Se não existir nenhum valor com frequência relativa acumulada igual a ppp﻿, o quantil e o primeiro valor cuja frequência relativa acumulada ultrapassa ppp﻿.  
    Qp={xi+xi+12 , para o valor i, tal que Fi=pxi , para o menor valor i, tal que Fi>pQ_p = \begin{cases} \text{$\frac{x_{i} + x_{i+1}}{2}$ , para o valor $i$, tal que $F_i = p$}\\ \text{$x_{i}$ , para o menor valor $i$, tal que $F_i > p$}\\ \end{cases}Qp​={2xi​+xi+1​​ , para o valor i, tal que Fi​=pxi​ , para o menor valor i, tal que Fi​>p​﻿

### Dados em Tabelas de Frequências - Estão Agrupados em Classes

- A primeira classe cuja a frequência relativa acumulada seja maior ou igual a pp p﻿ diz-se a **classe do quantil de ordem** ppp﻿.

- Um valor aproximado dos quantis pode ser obtido como anteriormente, mas através dos representantes das classes:  
    Qp={xi‘+xi+1‘2 , para o valor i, tal que Fi=pxi‘ , para o menor valor i, tal que Fi>pQ_p = \begin{cases} \text{$\frac{x_{i}^{‘} + x_{i+1}^{‘}}{2}$ , para o valor $i$, tal que $F_i = p$}\\ \text{$x_{i}^{‘}$ , para o menor valor $i$, tal que $F_i > p$}\\ \end{cases}Qp​={2xi‘​+xi+1‘​​ , para o valor i, tal que Fi​=pxi‘​ , para o menor valor i, tal que Fi​>p​﻿  
    onde xi‘x_i^{‘}xi‘​﻿ é o representante da classe do quantil de ordem ppp﻿ e xi+1‘x_{i+1}^{‘}xi+1‘​﻿ é o representante da classe seguinte à classe do quantil de ordem ppp﻿.

- **Outra possibilidade** para calcular um valor aproximado para os quantis é:  
    Qp≈ximin+(ximax−ximin)×p−Fi−1fiQ_p \approx x_i^{min} + (x_i^{max} - x_i^{min}) \times \frac {p - F_{i-1}}{f_i}Qp​≈ximin​+(ximax​−ximin​)×fi​p−Fi−1​​﻿  
    onde ximinx_i^{min}ximin​﻿ é o limite inferior da classe do quantil de ordem ppp﻿, ximaxx_i^{max}ximax​﻿ é o limite superior da classe do quantil de ordem ppp﻿, Fi−1F_{i-1}Fi−1​﻿ é a frequência relativa acumulada da classe anterior à classe do quantil de ordem ppp﻿ e fif_ifi​﻿ é a frequência relativa da classe do quantil de ordem ppp﻿. (Esta fórmula só se aplica quando todas as classes têm a mesma amplitude)

### Quartis

- Há vários métodos para calcular os quartis, nem todos conducentes aos mesmos valores, mas a valores próximos.

- Um dos métodos alternativos é dividir os dados de modo a calcular apenas a mediana:
    
    - Considerar os dados todos e calcular a mediana, x~=Q2\tilde x = Q_2x~=Q2​﻿, pois como vimos esta divide o conjunto de dados em duas partes iguais;
    
    - Depois calcula-se a mediana dos dados que ficam à esquerda de x~=Q2\tilde x = Q_2x~=Q2​﻿ e obtém-se o 1º quartil;
    
    - De seguida calcula-se a mediana dos dados que ficam à direita de x~=Q2\tilde x = Q_2x~=Q2​﻿ e obtém-se o 3º quartil.
    
    - No caso da dimensão da amostra ser ímpar, a mediana coincide com um dos elementos da amostra. Este método permite duas opções:
        
        - Considerar que a mediana fica incluída nas duas metades em que fica dividida a amostra  
            ou
        
        - Considerar que a mediana não fica incluída em nenhuma das metades em que fica dividida a amostra.

---

![](Dashboard/Attachments/icons_questions%207.png)

The **Sentence Method** is a simplified way to record notes on the fly. You should revisit your note after it is complete to restructure the information for easier reviewing later.