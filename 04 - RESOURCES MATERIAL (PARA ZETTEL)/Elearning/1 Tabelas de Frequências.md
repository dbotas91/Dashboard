---
tags:
  - elearning
dg-publish: "true"
dg-note-icon: lackluster
noteIcon: lackluster
---

![](Dashboard/Attachments/icons_notes--sentence%203.png)

# 1. Tabelas de Frequências

|   |   |
|---|---|
|![](Dashboard/Attachments/arrow-northeast_gray%201174.svg)Subject|[![](Dashboard/Attachments/icons_graduate%203.png)2.Estatística Descritiva - Organização e interpretação de dados](../Subjects/2%20Estat%C3%ADstica%20Descritiva%20-%20Organiza%C3%A7%C3%A3o%20e%20interpret%20179774eadd644777924295c57b6ce4f5.html)|
|![](Dashboard/Attachments/calendar_gray%201237.svg)Date Created|@June 2, 2022|
|![](Dashboard/Attachments/checkmark-square_gray%20655.svg)To Review?||
|![](Dashboard/Attachments/formula_gray%20474.svg)Review Due||
|![](Dashboard/Attachments/clock_gray%20106.svg)Last Edited|@June 25, 2022 5:28 PM|

# Tabela de Frequências

Numa tabela de frequências a informação é organizada, de um modo geral, em 3 colunas:

1. Colunas dos valores ou modalidades que as variáveis podem assumir, caso sejam variáveis quantitativas ou qualitativas, respetivamente;

2. Coluna das frequências absolutas;

3. Coluna das frequências relativas

Podem, ainda, ser acrescentadas mais duas colunas, com as frequências acumuladas:

1. Frequência absoluta acumulada;

2. Frequência relativa acumulada.

- Frequência absoluta
    
    de um valor _xix_ixi​_﻿ da variável é o número de vezes que esse  
    valor foi observado. Representa-se habitualmente por _nin_ini​_﻿.
    
    - A soma das frequências absolutas é igual a dimensão da amostra (ou a dimensão da população, caso tenham sido recolhidos dados relativos a todos os indivíduos da população).
    

- Frequência relativa
    
    de um valor da variável é o quociente entre a frequência absoluta desse valor e o número _n_ de elementos da população (ou da amostra).  
    Representa-se habitualmente por _fif_ifi​_﻿.
    
    - É sempre um número entre 0 e 1.
    
    - Pode ser expressa em percentagem desde que se multiplique o número obtido por 100.
    
    - A soma das frequências relativas é igual a 1.
    

As Tabelas de Frequências constroem-se de maneira diferente, consoante o tipo de variável.

Assim temos Tabelas de Frequências para

- Variáveis Qualitativas ou Variáveis Quantitativas Discretas (com número pequeno de valores distintos)

- Variáveis Quantitativas Contínuas ou Variáveis Quantitativas discretas (com número elevado de valores distintos) - Neste caso há a necessidade de agrupar os dados em classes

## Variáveis ==**Qualitativas**== ou **==quantitativas discretas==**

|Valor da variável|Frequências Absolutas|Frequências Relativas|Frequências Absolutas Acumuladas|Frequências Relativas Acumuladas|
|---|---|---|---|---|
|_xix_ixi​_|_nin_ini​_|_fif_ifi​_|_NiN_iNi​_|_FiF_iFi​_|
|_x_1|n1|_f1_ = _n1_ / _n_|_N_1 = _n_1|_F_1 = _f_1|
|_x_2|n2|_f_2 _= n_2 / _n_|_N_2 = _n_1 + _n_2|_F_2 = _f_1 + _f_2|
|…|…|…|…|…|
|_xk_|nk|fk=nknf_k = \frac {n_k} nfk​=nnk​​|Nk=∑i=1kni=nN_k = \sum_{i = 1}^{k} n_i = nNk​=∑i=1k​ni​=n|_Fk=∑i=1kfi=1F_k = \sum_{i=1}^{k} f_i = 1Fk​=∑i=1k​fi​=1_|
|Total|∑i=1kni=n\sum_{i=1}^{k} n_{i} = n∑i=1k​ni​=n|∑i=1kfi=1\sum_{i=1}^{k} f_{i} = 1∑i=1k​fi​=1|||

Frequência absoluta (_nin_ini​_﻿) - número de observações iguais a _xix_ixi​_﻿

Frequência relativa (_fif_ifi​_﻿) - fracção do número total de observações iguais a _xix_ixi​_﻿

Frequência absoluta acumulada (_NiNiNi_﻿) - número de observações menores ou iguais a _xix_ixi​_﻿

Frequência relativa acumulada (_FiFiFi_﻿) - fração do número total de observações menores ou iguais a _xix_ixi​_﻿

## Variáveis ==quantitativas contínuas==

### (ou variáveis ==quantitativas discretas com um número elevado de valores distintos==)

- Para estes tipos de variáveis há necessidade de agrupar os dados em classes.

- Para construir classes de igual amplitude pode ser usada uma regra para determinar o número de classes: a regra de Sturges.

Para determinar, pode deduzir-se o seguinte resultado:

k=⌊1+log⁡2n⌋=⌊1+ln⁡nln⁡2⌋k = \lfloor 1 + \log_{2} n \rfloor = \lfloor 1 + \frac {\ln n} {\ln 2} \rfloork=⌊1+log2​n⌋=⌊1+ln2lnn​⌋﻿

onde _n_ é o número de dados e ⌊a⌋\lfloor a \rfloor⌊a⌋﻿ representa a parte inteira de _a_

- Para a formação das **classes**, uma estratégia possível consiste em:
    
    - determinar o máximo (max(xi)max(x_i)max(xi​)﻿) e o mínimo (min(xi)min(x_i)min(xi​)﻿) dos dados
    
    - a amplitude de cada classe é h=max(xi)−min(xi)kh = \frac {max(xi) - min(xi)} {k}h=kmax(xi)−min(xi)​﻿, desta forma todas as classes têm a mesma amplitude.
    
    - Formar as classes como intervalos semiabertos, abertos à esquerda e fechados à direita (ou vice-versa), sendo o extremo esquerdo do primeiro intervalo o mínimo dos dados.
        
        - Quando os intervalos são abertos a esquerda e fechados à direita, o primeiro  
            intervalo da tabela de frequências é fechado à esquerda e à direita.
        
        - Quando os intervalos são fechados à esquerda e abertos à direita, o último intervalo da tabela de frequências pode ser fechado à direita caso o seu valor corresponda ao máximo dos dados

|Valor da variável|Marca da classe|Frequências Absolutas|Frequências Relativas|Frequências Absolutas Acumuladas|Frequências Relativas Acumuladas|
|---|---|---|---|---|---|
|cic_ici​|x’ix’ix’i|_nin_ini​_|_fif_ifi​_|_NiN_iNi​_|_FiF_iFi​_|
|c1=[min(xi);b1]c_1 = [min(x_i); b_1]c1​=[min(xi​);b1​]﻿  <br>(com b1=min(xi)+hb_1 = min(x_i) + hb1​=min(xi​)+h﻿)|x’1=xmin+b12x’_1 = \frac {x_{min} + b_1} {2}x’1​=2xmin​+b1​​|n1|_f1=n1nf_1 = \frac{n1}{n}f1​=nn1​_|_N_1 = _n_1|_F_1 = _f_1|
|c1 = ]b1; b2]  <br>(com b2 = b1 + h)|x’2=b1+b22x’_2 = \frac {b_1 + b_2} {2}x’2​=2b1​+b2​​|n2|_f2=n2nf_2 = \frac{n2}{n}f2​=nn2​_|_N_2 = _n_1 + _n_2|_F_2 = _f_1 + _f_2|
|…|…|…|…|…|…|
|ck=]bk−1;bk]c_k = ]b_k-1; b_k] ck​=]bk​−1;bk​]﻿(com bk=bk−1+hb_k = b_{k-1} + hbk​=bk−1​+h﻿)|x’k=bk−1+bk2x’_k = \frac {b_{k-1} + b_k} {2}x’k​=2bk−1​+bk​​|nk|fk=nknf_k = \frac{n_k}{n}fk​=nnk​​|Nk=∑i=1kni=nN_k = \sum_{i = 1}^{k} n_i = nNk​=∑i=1k​ni​=n|Fk=∑i=1kfi=1F_k = \sum_{i = 1}^{k} f_i = 1Fk​=∑i=1k​fi​=1|
|Total||∑i=1kni=n\sum_{i=1}^{k} n_{i} = n∑i=1k​ni​=n|∑i=1kfi=1\sum_{i=1}^{k} f_{i} = 1∑i=1k​fi​=1|n/a|n/a|

Frequência absoluta (_nin_ini​_﻿) - número de observações que pertencem à classe cic_ici​﻿

Frequência relativa (_fif_ifi​_﻿) - fracção do número total de observações que pertencem à classe cic_ici​﻿

Frequência absoluta acumulada (_NiN_iNi​_﻿) - número de observações menores menores que o extremo superior da classe cic_ici​﻿ (menores ou iguais se for a última classe e o intervalo estiver fechado)

Frequência relativa acumulada (_FiF_iFi​_﻿) - fração do número total de observações menores que o extremo superior da classe cic_ici​﻿ (menores ou iguais se for a última classe e o intervalo estiver fechado)

---

![](Dashboard/Attachments/icons_questions%203.png)

The **Sentence Method** is a simplified way to record notes on the fly. You should revisit your note after it is complete to restructure the information for easier reviewing later.