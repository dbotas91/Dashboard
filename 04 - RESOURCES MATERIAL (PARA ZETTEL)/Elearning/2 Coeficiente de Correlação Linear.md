---
tags:
  - elearning
dg-publish: "true"
dg-note-icon: lackluster
noteIcon: lackluster
---

![](Dashboard/Attachments/icons_notes--sentence%205.png)

# 2. Coeficiente de Correlação Linear

|   |   |
|---|---|
|![](Dashboard/Attachments/arrow-northeast_gray%201176.svg)Subject|[![](Dashboard/Attachments/icons_graduate%205.png)3. Regressão Linear Simples](../Subjects/3%20Regress%C3%A3o%20Linear%20Simples%209558cc6271874dbc880a7ea7990d09e0.html)|
|![](Dashboard/Attachments/calendar_gray%201239.svg)Date Created|@June 13, 2022|
|![](Dashboard/Attachments/checkmark-square_gray%20657.svg)To Review?||
|![](Dashboard/Attachments/formula_gray%20476.svg)Review Due||
|![](Dashboard/Attachments/clock_gray%20108.svg)Last Edited|@June 15, 2022 6:01 PM|

# Metodologia

Verificar a existência ou não de uma relação linear

## Coeficiente de Correlação Linear

- A análise gráfica da relação entre variáveis é importante, mas os olhos nem sempre são um bom juiz da intensidade de uma relação linear. Deve-se, então, utilizar uma medida numérica para complementar a análise gráfica.

- A medida que se utiliza com mais frequência para medir o grau da relação linear entre as variáveis XXX﻿ e YYY﻿ é o coeficiente de correlação linear, também chamado de **coeficiente de correlação linear de Pearson**.

- O coeficiente de correlação linear mede a maior ou menor intensidade com que as variáveis se associam, quer positiva, quer negativamente. Isto é, é uma medida que avalia o quanto a “nuvem de pontos” no diagrama de dispersão aproxima-se de uma reta.

- Representa-se por rxyr_{xy}rxy​﻿, é um estimador do coeficiente de correlação linear populacional, ρXY\rho_{XY}ρXY​﻿.

O coeficiente de correlação linear (também chamado de **coeficiente de correlação linear empírico** ou **amostral**) calcula-se da seguinte forma:

rxy=covaria^nciaxyvaria^nciaxvaria^nciay=sxysx2.Sy2=sxysxsy=∑i=1n(xi−x‾)(yi−y‾)(∑i=1n(xi−x‾)2×(∑i=1n(yi−y‾)2=∑i=1nxiyi−nx‾y‾(∑i=1nxi2−nx‾2)×(∑i=1nyi2−ny‾2)r_{xy} = \frac {covariância_{xy}}{\sqrt {variância_x variância_y}} = \frac {s_{xy}}{s_x^2 . S_y^2} = \frac {s_{xy}}{s_xs_y} = \frac {\sum_{i=1}^n (x_i - \overline x)(y_i - \overline y)}{\sqrt {(\sum_{i=1}^n (x_i - \overline x)^2 \times (\sum_{i=1}^n (y_i - \overline y)^2}} = \frac {\sum_{i=1}^n x_iy_i - n\overline x \overline y}{\sqrt {(\sum_{i=1}^n x_i^2 - n\overline x^2) \times (\sum_{i=1}^n y_i^2 - n\overline y^2)}}rxy​=varia^nciax​varia^nciay​​covaria^nciaxy​​=sx2​.Sy2​sxy​​=sx​sy​sxy​​=(∑i=1n​(xi​−x)2×(∑i=1n​(yi​−y​)2​∑i=1n​(xi​−x)(yi​−y​)​=(∑i=1n​xi2​−nx2)×(∑i=1n​yi2​−ny​2)​∑i=1n​xi​yi​−nxy​​﻿

- sx2=1n−1∑i=1n(xi−x‾)2=1n−1(∑i=1nxi2−nx‾2)(variaˆncia amostral da variaˊvel X);s_x^2 = \frac {1}{n-1} \sum_{i=1}^n (x_i - \overline x)^2 = \frac {1}{n-1} (\sum_{i=1}^n x_i^2 - n\overline x^2) \text {(variância amostral da variável $X$);}sx2​=n−11​∑i=1n​(xi​−x)2=n−11​(∑i=1n​xi2​−nx2)(variaˆncia amostral da variaˊvel X);﻿

- sy2=1n−1∑i=1n(yi−y‾)2=1n−1(∑i=1nyi2−ny‾2)(variaˆncia amostral da variaˊvel Y);s_y^2 = \frac {1}{n-1} \sum_{i=1}^n (y_i - \overline y)^2 = \frac {1}{n-1} (\sum_{i=1}^n y_i^2 - n\overline y^2) \text {(variância amostral da variável $Y$);}sy2​=n−11​∑i=1n​(yi​−y​)2=n−11​(∑i=1n​yi2​−ny​2)(variaˆncia amostral da variaˊvel Y);﻿

- sxy=1n−1∑i=1n(xi−x‾)(yi−y‾)=1n−1(∑i=1nxiyi−nx‾y‾)(variaˆncia amostral da variaˊvel X e Y);s_{xy} = \frac {1}{n-1} \sum_{i=1}^n (x_i - \overline x)(y_i - \overline y) = \frac {1}{n-1} (\sum_{i=1}^n x_iy_i - n\overline x\overline y) \text {(variância amostral da variável $X$ e $Y$);}sxy​=n−11​∑i=1n​(xi​−x)(yi​−y​)=n−11​(∑i=1n​xi​yi​−nxy​)(variaˆncia amostral da variaˊvel X e Y);﻿
    
    −1≤rXY≤1-1 ≤ r_{XY} ≤ 1−1≤rXY​≤1﻿
    

- rXY>0r_{XY} > 0rXY​>0﻿ → significa que a relação entre os valores de xxx﻿ e os de yyy﻿ é do mesmo sentido, isto é, a valores grandes de xxx﻿ correspondem, de um modo geral, valores grandes de yyy﻿ e vice-versa → **correlação linear positiva**.

- rXY<0r_{XY} < 0rXY​<0﻿ → a relação entre os valores de xxx﻿ e os de yyy﻿ é de sentido contrário, o que significa que a valores grandes de xxx﻿, correspondem, de um modo geral, valores pequenos de yyy﻿ e vice-versa → **correlação linear negativa**.

- rXY=0r_{XY} = 0rXY​=0﻿ → significa que não existe relação linear entre os valores de x e os de y (mas pode existir outro tipo de relação) → **não há correlação linear**.

Quanto maior for ∣rXY∣|r_{XY}|∣rXY​∣﻿, mais fore é a relação linear entre XXX﻿ e YYY﻿.

[![](Dashboard/Attachments/5B83F7D5-077B-4A90-B53F-22AC08C943F6%201.jpeg)](1%20Diagrama%20de%20Dispers%C3%A3o%20ou%20Nuvem%20de%20Pontos/5B83F7D5-077B-4A90-B53F-22AC08C943F6.jpeg)

- É possível classificar a intensidade da correlação, analisando a proximidade do coeficiente de correlação linear em relação aos valores de 111﻿ e −1-1−1﻿.

- Tabela indicativa:

[![](Dashboard/Attachments/91D155CD-AA10-4259-92AC-9952D28E3E25%201.jpeg)](1%20Diagrama%20de%20Dispers%C3%A3o%20ou%20Nuvem%20de%20Pontos/91D155CD-AA10-4259-92AC-9952D28E3E25.jpeg)

### Observação

- A “confirmação” da existência de um “bom” coeficiente de correlação linear empírico entre XXX﻿ e YYY﻿ deve ser sempre acompanhado pelo diagrama de dispersão.

- Por exemplo, no seguinte diagrama de dispersão pode-se observar que o modelo linear não é adequado, mas se calcular o coeficiente de correlação linear irá obter um valor próximo de 1.

[![](Dashboard/Attachments/00D5FE80-9EF6-4E4A-841E-C676F6C94474%201.jpeg)](1%20Diagrama%20de%20Dispers%C3%A3o%20ou%20Nuvem%20de%20Pontos/00D5FE80-9EF6-4E4A-841E-C676F6C94474.jpeg)

Exemplo 1

Um psicólogo efetuou uma pesquisa com o objetivo de analisar a forma como as crianças aprendem um determinado jogo. Das diversas variáveis observadas foram registados o número de jogos efetuados (X)(X)(X)﻿ e o número de erros realizados no jogo (Y)(Y)(Y)﻿:

[![](Dashboard/Attachments/6F6BDD64-0A79-44B3-AFA7-372CD0461904%201.jpeg)](3%20Reta%20de%20Regress%C3%A3o/6F6BDD64-0A79-44B3-AFA7-372CD0461904.jpeg)

1. Determine o coeficiente de correlação linear.

[![](Dashboard/Attachments/26F62393-C62E-431A-801A-418534CA9F7C%201.jpeg)](1%20Diagrama%20de%20Dispers%C3%A3o%20ou%20Nuvem%20de%20Pontos/26F62393-C62E-431A-801A-418534CA9F7C.jpeg)

[![](Dashboard/Attachments/27CDA7CB-463E-412C-9DF5-0805E7A0A888%201.jpeg)](1%20Diagrama%20de%20Dispers%C3%A3o%20ou%20Nuvem%20de%20Pontos/27CDA7CB-463E-412C-9DF5-0805E7A0A888.jpeg)

# Correlação

## Observação

Correlação não significa Causalidade.

A associação não deve ser interpretada como causa - efeito. Pode, eventualmente, haver outras variáveis, com que não estamos a contar, que contribuam para a associação linear observada.

![](Dashboard/Attachments/icons_questions%205.png)

The **Sentence Method** is a simplified way to record notes on the fly. You should revisit your note after it is complete to restructure the information for easier reviewing later.