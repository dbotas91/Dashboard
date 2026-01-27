---
tags:
  - elearning
dg-publish: "true"
dg-note-icon: lackluster
noteIcon: lackluster
---

![](Dashboard/Attachments/icons_notes--sentence%2010.png)

# 3. Medidas de Dispersão

|   |   |
|---|---|
|![](Dashboard/Attachments/arrow-northeast_gray%201181.svg)Subject|[![](Dashboard/Attachments/icons_graduate%2010.png)2.Estatística Descritiva - Organização e interpretação de dados](../Subjects/2%20Estat%C3%ADstica%20Descritiva%20-%20Organiza%C3%A7%C3%A3o%20e%20interpret%20179774eadd644777924295c57b6ce4f5.html)|
|![](Dashboard/Attachments/calendar_gray%201243.svg)Date Created|@June 13, 2022|
|![](Dashboard/Attachments/checkmark-square_gray%20662.svg)To Review?||
|![](Dashboard/Attachments/formula_gray%20481.svg)Review Due||
|![](Dashboard/Attachments/clock_gray%20113.svg)Last Edited|@June 15, 2022 6:05 PM|

# Medidas de Dispersão

Permitem resumir os dados calculando algumas características numéricas de modo a ter informação sobre a sua variabilidade ou dispersão:

- Medidas de dispersão absoluta (depende da unidade em que se exprime a variável):
    
    - Amplitude: amplitude total e amplitude interquartis,
    
    - Variância e desvio padrão.

- Medidas de dispersão relativa (não depende da unidade em que se exprime a variável):
    - Coeficiente de variação.

## Amplitude Total

- Habitualmente representa-se por **A**.

- A **Amplitude Total** é a medida mais simples para medir a variabilidade dos dados.

- Para dados não agrupados, a amplitude total define-se como a diferença entre o maior e o menor valor do conjunto de dados (diferença entre os extremos). Isto é, seja {x1,x2,…,xnx_1,x_2,…,x_nx1​,x2​,…,xn​﻿} um conjunto de dados com nnn﻿ observações,  
    A=max(xi)−min(xi)A = max(x_i) - min(x_i)A=max(xi​)−min(xi​)﻿.

- Para dados agrupados em classes, a amplitude total é a diferença entre o limite superior da última classe e o limite inferior da primeira classe.

- É uma medida não negativa e será tanto maior quanto maior for a variabilidade dos dados.

- Observações
    
    - A amplitude É uma fraca medida de dispersão. Exemplo de distribuições com a mesma amplitude, mas com uma dispersão muito diferente:  
        
    
    - Desvantagem da amplitude enquanto medida de dispersão:
        
        - É insensível às alterações dos valores intermédios (nela só intervêm os extremos).
        
        - Não diz nada sobre o que se passa no intervalo entre os extremos. Em certas distribuições os valores extremos correspondem a casos excecionais e portanto pouco significativos.
    

## Amplitude interquartis

- Habitualmente representa-se por AIQAIQAIQ﻿.

- A amplitude interquartis define-se como a diferença entre o 3º quartil e o 1º quartil:  
    AIQ=Q3−Q1=Q0.75−Q0,25AIQ = Q_3 - Q_1 = Q_{0.75} - Q_{0,25}AIQ=Q3​−Q1​=Q0.75​−Q0,25​﻿

- É uma medida não negativa e será tanto maior quanto maior for a variabilidade dos dados.

- Amplitude interquartis indica a amplitude do intervalo onde se situa a metade central dos dados, sendo pouco sensível aos valores extremos.

- Uma Amplitude Interquartis nula não significa que os dados não apresentem variabilidade.

- Desvantagem desta medida de dispersão:
    - É insensível às alterações dos valores que se encontram antes do 1º quartil e depois do 3º quartil.

---

## Medidas de Dispersão

- Como vimos, embora a amplitude (total ou interquartil) seja uma possibilidade importante para analisar a variabilidade dos dados, tem limitações.

- Outra possibilidade para analisar a variabilidade dos dados consiste em comparar os dados com uma medida de localização central: a média.

- A dispersão dos dados em torno da sua média permite caracterizar um conjunto de dados, pois dados com a mesma média podem ter uma dispersão muito diferente:

- No entanto não é possível caracterizar a variabilidade somando os desvios em relação à média. A soma dos desvios é sempre zero.

- Deve-se considerar uma medida não leve em conta o sinal dos desvios (o que importa é a magnitude do desvio). Assim, se considerarmos valor absoluto (módulo) dos desvios temos o **Desvio absoluto médio**, mas se considerarmos o quadrado dos desvios temos a **Variância**.

## Variância

Representa-se por s2s^2s2﻿ (quando os dados correspondem a uma amostra) ou por σ2\sigma^2σ2﻿ (quando os dados correspondem à população).

A variância mede o afastamento dos dados em relação à média.

A variância é a média dos quadrados dos desvios relativamente à média. Isto é, seja {x1,x2,…,xnx_1,x_2,…,x_nx1​,x2​,…,xn​﻿} um conjunto de dados com nnn﻿ observações, define-se variância como  
s2=(x1−x‾)2+(x2−x‾)2+…+(xn−x‾)2n−1=∑i=1n(xi−x‾)2n−1=∑i=1nxi2−nx‾2n−1s^2 = \frac {(x_1-\overline {x})^2+(x_2-\overline {x})^2+…+(x_n-\overline {x})^2}{n-1} = \frac {\sum_{i=1}^n (x_i - \overline {x})^2}{n-1}=\frac{\sum_{i=1}^n x_i^2 - n \overline{x}^2}{n-1}s2=n−1(x1​−x)2+(x2​−x)2+…+(xn​−x)2​=n−1∑i=1n​(xi​−x)2​=n−1∑i=1n​xi2​−nx2​﻿

### Dados em Tabelas de Frequências - Não estão agrupados em Classes

- Com as frequências absolutas:  
    s2=n1(x1−x‾)2+n2(x2−x‾)2+…+nk(xk−x‾)2n−1=∑i=1kni(xi−x‾)2n−1=∑i=1knixi2−nx‾2n−1s^2 = \frac{n_1(x_1-\overline x)^2+n_2(x_2-\overline x)^2 + … + n_k (x_k - \overline x)^2}{n-1} = \frac{\sum_{i=1}^kn_i(x_i- \overline x)^2}{n-1} = \frac {\sum_{i=1}^k{n_ix_i^2} - n\overline x^2}{n-1}s2=n−1n1​(x1​−x)2+n2​(x2​−x)2+…+nk​(xk​−x)2​=n−1∑i=1k​ni​(xi​−x)2​=n−1∑i=1k​ni​xi2​−nx2​﻿

- Com frequências relativas:  
    s2=n×(f1(x1−x‾)2+f2(x2−x‾)2+…+fk(xk−x‾)2)n−1=n×(∑i=1kfi(xi−x‾)2)n−1=n×(∑i=1kfixi2−x‾2)n−1s^2 = \frac{n \times(f_1(x_1-\overline x)^2+f_2(x_2-\overline x)^2 + … + f_k (x_k - \overline x)^2)}{n-1} = \frac{n \times(\sum_{i=1}^k f_i(x_i- \overline x)^2)}{n-1} = \frac {n \times(\sum_{i=1}^k{f_ix_i^2}-\overline x^2)}{n-1}s2=n−1n×(f1​(x1​−x)2+f2​(x2​−x)2+…+fk​(xk​−x)2)​=n−1n×(∑i=1k​fi​(xi​−x)2)​=n−1n×(∑i=1k​fi​xi2​−x2)​﻿

### Dados em Tabelas de Frequências - Estão Agrupados em Classes

- Com as frequências absolutas:  
    s2≈n1(x1′−x‾)2+n2(x2′−x‾)2+…+nk(xk′−x‾)2n−1=∑i=1kni(xi′−x‾)2n−1=∑i=1knixi′2−nx‾2n−1s^2 \approx \frac{n_1(x_1^{'}-\overline x)^2+n_2(x_2^{'}-\overline x)^2 + … + n_k (x_k^{'} - \overline x)^2}{n-1} = \frac{\sum_{i=1}^kn_i(x_i^{'}- \overline x)^2}{n-1} = \frac {\sum_{i=1}^k{n_ix_i^{'2}} - n\overline x^2}{n-1}s2≈n−1n1​(x1′​−x)2+n2​(x2′​−x)2+…+nk​(xk′​−x)2​=n−1∑i=1k​ni​(xi′​−x)2​=n−1∑i=1k​ni​xi′2​−nx2​﻿

- Com frequências relativas:  
    s2≈n×(f1(x1′−x‾)2+f2(x2′−x‾)2+…+fk(xk′−x‾)2)n−1=n×(∑i=1kfi(xi′−x‾)2)n−1=n×(∑i=1kfixi′2−x‾2)n−1s^2 \approx \frac{n \times(f_1(x_1^{'}-\overline x)^2+f_2(x_2^{'}-\overline x)^2 + … + f_k (x_k^{'} - \overline x)^2)}{n-1} = \frac{n \times(\sum_{i=1}^k f_i(x_i^{'}- \overline x)^2)}{n-1} = \frac {n \times(\sum_{i=1}^k{f_ix_i^{'2}}-\overline x^2)}{n-1}s2≈n−1n×(f1​(x1′​−x)2+f2​(x2′​−x)2+…+fk​(xk′​−x)2)​=n−1n×(∑i=1k​fi​(xi′​−x)2)​=n−1n×(∑i=1k​fi​xi′2​−x2)​﻿

### Observações

- Note-se que a **Variância** envolve a soma de quadrados, e por isso a unidade medida em que se exprime não é a mesma que a dos dados, a **unidade de medida** fica **ao quadrado**.

- Vantagem da variância como medida de dispersão:
    - No seu cálculo entram todas as observações

- Desvantagem da variância como medida de dispersão:
    
    - Não é fácil de interpretar, uma vez que é expressa em unidades da variável ao quadrado;
    
    - Facilmente assume valores muito elevados;
    
    - É uma medida pouco resistente a valores extremos (muito grande ou muito pequenos).

- Em todas as definições anteriores de variância assumiu-se sempre que se estava a trabalhar com amostras (e não com todos os dados da população). Por isso representou-se a variância por s2s^2s2﻿.

- Quando se calcula a variância de dados que correspondem a toda a população (e não a uma amostra), tem-se  
    σ2=(x1−μ)2+(x2−μ)2+…+(xN−μ)2N=∑i=1N(xi−μ)2N\sigma ^2 = \frac {(x_1-\mu)^2+(x_2-\mu)^2+…+(x_N-\mu)^2}{N}=\frac{\sum_{i=1}^N(x_i-\mu)^2}{N}σ2=N(x1​−μ)2+(x2​−μ)2+…+(xN​−μ)2​=N∑i=1N​(xi​−μ)2​﻿  
    onde NNN﻿ é a dimensão da população e μ\muμ﻿ é a média da população.  
    (A média da população calcula-se do mesmo modo que vimos anteriormente, apenas se usa uma letra diferente para a representar.)

## Desvio Padrão

- Representa-se po sss﻿ (quando os dados correspondem a uma amostra) ou por σ\sigmaσ﻿ (quando os dados correspondem à população).

- O desvio padrão é a raiz quadrada da variância  
    s=s2s = \sqrt{s^2} s=s2​﻿

- O desvio padrão é sempre maior ou igual a zero.

- É a medida de dispersão mais utilizada uma vez que vem expressa na mesma unidade em que estão expressos os dados da amostra.

- O desvio padrão informa sobre o afastamento dos dados em relação à média.  
    Quanto maior for o desvio padrão, maior é o afastamento dos dados em relação à média.

- O Desvio Padrão, assim como a média, é muito sensível a valores extremos, portanto é a medida pouco resistente.

## Coeficiente de Variação

- O desvio padrão por si só não traz muita informação. Ou seja, um desvio padrão de 2 unidades pode ser considerado pequeno para um conjunto de valores cuja média é 200, mas já pode ser considerado grande se a média for de 20.

- Como o desvio padrão vem na mesma unidade de medida dos dados, não se deve usar esta medida de dispersão para comparar conjuntos de dados com ==**unidades de medida diferentes**== ou que ==**diferem consideravelmente em grandeza**==. Neste caso deve-se recorrer ao **Coeficiente de Variação**.

- O coeficiente de variação representa-se por CVCVCV﻿.

- O coeficiente de variação e uma medida de dispersão relativa e corresponde ao quociente entre o desvio padrão (medida de dispersão) e a média (medida de localização):
    
    - Quando os dados correspondem a uma **amostra**:  
        CV=sx‾×100CV = \frac {s}{\overline x} \times 100CV=xs​×100﻿%
    
    - Quando os dados correspondem à **população**:  
        CV=σμ×100CV = \frac {\sigma}{\mu} \times 100CV=μσ​×100﻿%

- O coeficiente de variação pode ser interpretado como a fração da dispersão pela qual a localização é responsável. Isto é, o coeficiente de variação indica a magnitude relativa do desvio padrão quando comparado com a média do conjunto de valores.

- Quanto maior for o coeficiente de variação, maior é a dispersão dos dados.

- O coeficiente de variação é independente da unidade de medida utilizada, sendo útil para comparar conjuntos de dados.

- Esta medida só deve ser usada quando a variável toma valores de um só sinal, isto é, todos os dados são positivos ou todos os dados são negativos.

![](Dashboard/Attachments/icons_questions%2010.png)

The **Sentence Method** is a simplified way to record notes on the fly. You should revisit your note after it is complete to restructure the information for easier reviewing later.