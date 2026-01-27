---
tags:
  - elearning
dg-publish: "true"
dg-note-icon: lackluster
noteIcon: lackluster
---

![](Dashboard/Attachments/icons_notes--sentence%2019.png)

# 5. Variáveis Aleatórias Contínuas

|   |   |
|---|---|
|![](Dashboard/Attachments/arrow-northeast_gray%201190.svg)Subject|[![](Dashboard/Attachments/icons_graduate%2019.png)4. Distribuições Teóricas](../Subjects/4%20Distribui%C3%A7%C3%B5es%20Te%C3%B3ricas%209a10eaba10f74467ae7119be5e92ac2f.html)|
|![](Dashboard/Attachments/calendar_gray%201252.svg)Date Created|@June 16, 2022|
|![](Dashboard/Attachments/checkmark-square_gray%20671.svg)To Review?||
|![](Dashboard/Attachments/formula_gray%20490.svg)Review Due||
|![](Dashboard/Attachments/clock_gray%20122.svg)Last Edited|@June 28, 2022 3:58 PM|

[Função Densidade de Probabilidade (f.d.p.)](#74fd95c3-eea3-4c8c-87f7-ed9c11f2ac1f)

[Função densidade de probabilidade = f(x)](#8b543651-8bec-46eb-a345-de13c54f5e02)

[Exemplo 18](#3a298b42-b0e6-4e06-a20f-ec3b95f35412)

[Função de Distribuição (f.d.)](#5451bb92-a8db-49df-83a4-49d7526d564d)

[Exemplo 18](#da12b035-00c5-4317-b0a6-45002a592923)

[Exemplo 18](#46a8e11e-b182-4d28-bf6e-3651967c67f2)

[Exemplo 19](#640183d8-7bf1-4480-add9-1ef130be5592)

[Valor Esperado ou Média ou Esperança Matemática](#1b565316-a284-456a-bdd8-e1f1f3d25c9f)

[Observação](#8efc5cc6-5b5e-45d3-8ae5-e3c92f30e8a7)

[Observação](#39f28dd5-3bba-4d02-8eea-0a16ec56483d)

[Propriedades](#7b31d800-2b6a-4662-9f1a-143bbba526c4)

[Exemplo 18](#251f8970-d674-407a-b378-e75b9de83bf0)

[Variância = V[ ]](#2be7e99c-5470-48e5-8db9-4f97ac8db11b)

[Observação](#f4965709-efe1-45df-9110-8774e18f7f52)

[Propriedades:](#ea3d6629-cebc-45ee-9601-b5d00bb565ae)

[Desvio Padrão](#95b737fc-359b-4bfe-8528-8465dae83040)

[Observação](#12f6baa4-b51f-404d-98ba-5b978953a8a9)

[Exemplo 18](#b0d83716-36cf-4618-88ec-6a5f5c0d56fa)

[Exemplo 19](#684fa3ec-fcb3-4d0d-91e7-8ae445aeabec)

Uma variável aleatória diz-se **Contínua** se pode assumir um número infinito não numerável de valores.

Uma variável aleatória contínua fica perfeitamente identificada através da:

- **Função densidade de probabilidade**

Ou

- **Função de distribuição**

E através dos seus parâmetros (apenas vamos considerar 3):

- **Valor esperado** ou média ou esperança matemática

- **Variância**

- **Desvio padrão**

# Função Densidade de Probabilidade (f.d.p.)

Se XXX﻿ é uma variável aleatória contínua, então existe uma função f(x)f(x)f(x)﻿ tal que

F(x)=∫−∞xf(t)dtF(x) = \int^x_{-\infty} f(t) dtF(x)=∫−∞x​f(t)dt﻿.

À função f(x) dá-se o nome de função densidade de probabilidade e pode ser representada por

f(x)={F′(x)  , caso exista0          , outros casosf(x) = \begin{cases}F'(x) \ \ \text{, caso exista} \\ \text{$0 \ \ \ \ \ \ \ \ \ \ $, outros casos} \end{cases}f(x)={F′(x)  , caso exista0          , outros casos​﻿

e satisfaz as seguintes propriedades:

1. f(x)≥0,∀xf(x) ≥ 0, \forall xf(x)≥0,∀x﻿;

2. ∫−∞+∞f(x) dx=1\int_{-\infty}^{+ \infty} f(x)\ dx = 1∫−∞+∞​f(x) dx=1﻿.

# Função densidade de probabilidade = f(x)

- Nas variáveis aleatórias **discretas** tem-se a **função de probabilidade** que permite calcular as probabilidades pontuais:
    
    f(x)=P(X=x)f(x) = P(X=x)f(x)=P(X=x)﻿
    
    Aqui o interesse não são as probabilidades pontuais mas a probabilidade de estar dentro de um intervalo: P(a≤X≤b)P(a ≤ X ≤b)P(a≤X≤b)﻿.
    

- Nas variáveis aleatórias ==contínuas== tem-se a ==função== ==densidade== ==de probabilidade==, esta função não tem como objetivo calcular probabilidades pontuais (pois aqui não têm interesse) mas descrever a probabilidade relativa de uma variável aleatória, ou seja, o seu comportamento: onde cresce, onde diminui ou onde se mantém constante.  
    Alguns gráficos de funções densidade de probabilidade:

[![](Dashboard/Attachments/Untitled%2027.png)](5%20Vari%C3%A1veis%20Aleat%C3%B3rias%20Cont%C3%ADnuas/Untitled.png)

- Nas variáveis aleatórias contínuas o interesse está na probabilidade de uma variável cair dentro de um intervalo, então essa probabilidade é dada pelo integral da função densidade nesse intervalo.

- Ou seja, a probabilidade no caso das variáveis contínuas é dada pela área compreendida entre a função densidade de probabilidade, o eixo dos xx e os limites do intervalo pretendido:
    
    P(a≤X≤b)=∫abf(x) dxP(a ≤ X ≤ b) = \int_a^b f(x) \ dxP(a≤X≤b)=∫ab​f(x) dx﻿
    
    [![](Dashboard/Attachments/Untitled%201%208.png)](5%20Vari%C3%A1veis%20Aleat%C3%B3rias%20Cont%C3%ADnuas/Untitled%201.png)
    

No entanto é necessário ter atenção que uma função f(x)f(x)f(x)﻿ só é uma **função densidade de probabilidade** se verificar as seguintes propriedades:

1. f(x)≥0,   ∀x;f(x) ≥ 0,\ \ \ \forall x;f(x)≥0,   ∀x;﻿

2. ∫−∞+∞f(x) dx=1.\int_{- \infty}^{+ \infty} f(x) \ dx = 1.∫−∞+∞​f(x) dx=1.﻿

Ou seja, a função densidade de probabilidade não pode ser negativa e a área total entre a função densidade de probabilidade e o eixo dos xx é 1.

Exemplo 18

De acordo com determinadas especificações técnicas de uma marca de aparelhos de radiologia, sabe-se que a sua duração (em anos) é uma vairável aleatória XXX﻿ com a seguinte função densidade de probabilidade:

f(x)={x4        ,0<x≤21−x4 ,2<x≤40         , caso contraˊriof(x) = \begin{cases} \frac{x}{4} \ \ \ \ \ \ \ \ , 0<x≤2 \\ 1- \frac{x}{4} \ , 2<x≤4 \\ 0 \ \ \ \ \ \ \ \ \text{ , caso contrário} \end{cases}f(x)=⎩⎨⎧​4x​        ,0<x≤21−4x​ ,2<x≤40         , caso contraˊrio​﻿

1. Mostre que fff﻿ é de facto uma função densidade de probabilidade.

f(x)f(x) f(x)﻿ é uma função de probabilidade sse

1. f(x)≥0,  ∀x;f(x) ≥ 0, \ \ \forall x;f(x)≥0,  ∀x;﻿

2. ∫−∞+∞f(x) dx=1.\int_{- \infty}^{+ \infty} f(x) \ dx = 1.∫−∞+∞​f(x) dx=1.﻿

**Propriedade 1**:

se 0<x≤2,    f(x)≥0⇔x4≥0⇔x≥00 < x ≤ 2, \ \ \ \ f(x) ≥ 0 \Harr \frac{x}{4} ≥ 0 \Harr x≥ 00<x≤2,    f(x)≥0⇔4x​≥0⇔x≥0﻿ o que é verdade pois 0<x≤20 < x≤20<x≤2﻿

se 2<x≤4,    f(x)≥0⇔1−x4≥0⇔x≤42 < x ≤ 4, \ \ \ \ f(x) ≥ 0 \Harr 1-\frac{x}{4} ≥ 0 \Harr x≤42<x≤4,    f(x)≥0⇔1−4x​≥0⇔x≤4﻿ o que é verdade pois 2<x≤42 <x≤42<x≤4﻿

se x≤0 ou x>4,    f(x)≥0⇔0≥0x ≤ 0 \ \text{ou} \ x>4, \ \ \ \ f(x) ≥ 0 \Harr 0 ≥ 0x≤0 ou x>4,    f(x)≥0⇔0≥0﻿ sempre verdade, qualquer que seja xxx﻿

**Propriedade 2**:

∫−∞+∞f(x) dx=∫−∞00dx +∫02x4dx +∫24(1−x4)dx +∫4+∞0dx=0+[x28]02+[x−x28]24+0=(228−0)+(4−428−(2−228))1\int_{- \infty}^{+ \infty} f(x) \ dx = \int_{- \infty}^{0} 0dx\ +\int_{0}^{2} \frac{x}{4}dx\ + \int_{2}^{4}(1-\frac{x}{4})dx\ +\int_{4}^{+ \infty} 0dx = 0 + [\frac{x^2}{8}]_0^2+[x-\frac{x^2}{8}]_2^4+0=(\frac{2^2}{8}-0)+(4-\frac{4^2}{8}-(2-\frac{2^2}{8})) 1∫−∞+∞​f(x) dx=∫−∞0​0dx +∫02​4x​dx +∫24​(1−4x​)dx +∫4+∞​0dx=0+[8x2​]02​+[x−8x2​]24​+0=(822​−0)+(4−842​−(2−822​))1﻿

Como verifica as duas propriedades, então é função densidade de probabilidade.

2. Calcule P(1≤X≤3)P(1≤ X ≤3)P(1≤X≤3)﻿.

P(1≤X≤3)P(1≤ X ≤3)P(1≤X≤3)﻿=∫13f(x) dx=∫12x4dx+∫23(1−x4)dx=[x28]12+[x−x28]23=(228−128)+(3−328−(2−228))=34 = \int_1^3 f(x) \ dx = \int_1^2 \frac{x}{4}dx + \int_2^3(1-\frac{x}{4})dx=[\frac{x^2}{8}]_1^2+[x-\frac{x^2}{8}]_2^3=(\frac{2^2}{8}-\frac{1^2}{8})+(3-\frac{3^2}{8}-(2-\frac{2^2}{8}))=\frac{3}{4}=∫13​f(x) dx=∫12​4x​dx+∫23​(1−4x​)dx=[8x2​]12​+[x−8x2​]23​=(822​−812​)+(3−832​−(2−822​))=43​﻿

# Função de Distribuição (f.d.)

Se XXX﻿ é uma variável aleatória contínua, então a função de distribuição é representada por F(x)F(x)F(x)﻿ e é definida por  
F(x)=P(X≤x)=∫−∞xf(t)dtF(x) = P(X ≤ x) = \int_{- \infty}^{x} f(t)dtF(x)=P(X≤x)=∫−∞x​f(t)dt﻿

e satisfaz as seguintes propriedades:

1. 0≤F(x)≤1;0 ≤ F(x) ≤ 1;0≤F(x)≤1;﻿

2. F(x)F(x)F(x)﻿ é uma função não decrescente;

3. F(x)F(x)F(x)﻿ é contínua em R\mathbb{R}R﻿;

4. lim⁡x→−∞F(X)=0   e   lim⁡x→+∞F(X)=1;\lim_{x→- \infty} F(X) = 0 \ \ \ \text{e} \ \ \ \lim_{x→+ \infty} F(X) = 1;limx→−∞​F(X)=0   e   limx→+∞​F(X)=1;﻿

5. P(X=a)=0;P(X=a) = 0;P(X=a)=0;﻿

6. P(a<X≤b)=P(a < X ≤ b) = P(a<X≤b)=﻿P(a<X<b)=P(a < X < b)=P(a<X<b)=﻿P(a≤X≤b)=P(a ≤ X ≤ b) = P(a≤X≤b)=﻿P(a≤X<b)=F(b)−F(a);P(a ≤ X < b) = F(b) - F(a);P(a≤X<b)=F(b)−F(a);﻿

- Tal como nas variáveis aleatórias discretas a função de distribuição de uma variável aleatória contínua permite calcular as probabilidades acumuladas:
    
    F(x)=P(X≤x)F(x) = P(X≤x)F(x)=P(X≤x)﻿
    

- a diferença é que, em vez de somar probabilidades pontuais, vamos somar áreas:  
    F(x)=P(X≤x)=∫−∞xf(t) dtF(x)=P(X≤x)=\int_{-\infty}^xf(t) \ dtF(x)=P(X≤x)=∫−∞x​f(t) dt﻿

- Em relação às propriedades, agora F(x)F(x)F(x)﻿ é contínua em R\mathbb{R}R﻿, o seu gráfico tem o seguinte aspeto:

[![](Dashboard/Attachments/Untitled%202%206.png)](5%20Vari%C3%A1veis%20Aleat%C3%B3rias%20Cont%C3%ADnuas/Untitled%202.png)

Exemplo 18

De acordo com determinadas especificações técnicas de uma marca de aparelhos de radiologia, sabe-se que a sua duração (em anos) é uma vairável aleatória XXX﻿ com a seguinte função densidade de probabilidade:

f(x)={x4        ,0<x≤21−x4 ,2<x≤40         , caso contraˊriof(x) = \begin{cases} \frac{x}{4} \ \ \ \ \ \ \ \ , 0<x≤2 \\ 1- \frac{x}{4} \ , 2<x≤4 \\ 0 \ \ \ \ \ \ \ \ \text{ , caso contrário} \end{cases}f(x)=⎩⎨⎧​4x​        ,0<x≤21−4x​ ,2<x≤40         , caso contraˊrio​﻿

3. Calcule a função de distribuição.

[![](Dashboard/Attachments/Untitled%203%205.png)](5%20Vari%C3%A1veis%20Aleat%C3%B3rias%20Cont%C3%ADnuas/Untitled%203.png)

[![](Dashboard/Attachments/Untitled%204%204.png)](5%20Vari%C3%A1veis%20Aleat%C3%B3rias%20Cont%C3%ADnuas/Untitled%204.png)

[![](Dashboard/Attachments/Untitled%205%204.png)](5%20Vari%C3%A1veis%20Aleat%C3%B3rias%20Cont%C3%ADnuas/Untitled%205.png)

- O cálculo da função distribuição pode dar “muito trabalho” mas compensa, pois o cálculo das probabilidades torna-se muito mais simples no caso das variáveis aleatórias contínuas.

- Como F(x)=P(X≤x)=∫−∞xf(t) dtF(x) = P(X≤x) = \int_{- \infty}^xf(t)\ dtF(x)=P(X≤x)=∫−∞x​f(t) dt﻿, então
    
    ∫abf(x) dx=F(b)−F(a)\int_a^b f(x)\ dx = F(b) - F(a)∫ab​f(x) dx=F(b)−F(a)﻿
    

- Também permite verificar que as probabilidades pontuais não têm interesse no caso das variáveis aleatórias contínuas, pois
    
    P(X=a)=∫aaf(x) dx=F(a)−F(a)=0P(X=a) = \int_a^a f(x)\ dx = F(a)-F(a)=0P(X=a)=∫aa​f(x) dx=F(a)−F(a)=0﻿
    

- Como no caso das variáveis aleatórias contínuas tem-se P(X=a)=0P(X=a) =0P(X=a)=0﻿, logo quando X é uma variável aleatória contínua tem-se:
    
    P(a<X≤b)=P(a≤X<b)=P(a≤X≤b)=P(a<X<b)P(a<X ≤ b) = P(a≤ X <b)= P(a ≤ X ≤ b) = P(a < X < b)P(a<X≤b)=P(a≤X<b)=P(a≤X≤b)=P(a<X<b)﻿
    
    e em todos os casos basta calcular:
    

- P(a<X≤b)=∫abf(x)dx=F(b)−F(a)P (a < X ≤ b) = \int_a^b f(x) dx = F(b) − F(a)P(a<X≤b)=∫ab​f(x)dx=F(b)−F(a)﻿

- P(a≤X<b)=∫abf(x)dx=F(b)−F(a)P (a ≤ X < b) = \int_a^b f(x) dx = F(b) − F(a)P(a≤X<b)=∫ab​f(x)dx=F(b)−F(a)﻿

- P(a≤X≤b)=∫abf(x)dx=F(b)−F(a)P (a ≤ X ≤ b) = \int_a^b f(x) dx = F(b) − F(a)P(a≤X≤b)=∫ab​f(x)dx=F(b)−F(a)﻿

- P(a<X<b)=∫abf(x)dx=F(b)−F(a)P (a < X < b) = \int_a^b f(x) dx = F(b) − F(a)P(a<X<b)=∫ab​f(x)dx=F(b)−F(a)﻿

Exemplo 18

De acordo com determinadas especificações técnicas de uma marca de aparelhos de radiologia, sabe-se que a sua duração (em anos) é uma vairável aleatória XXX﻿ com a seguinte função densidade de probabilidade:

f(x)={x4        ,0<x≤21−x4 ,2<x≤40         , caso contraˊriof(x) = \begin{cases} \frac{x}{4} \ \ \ \ \ \ \ \ , 0<x≤2 \\ 1- \frac{x}{4} \ , 2<x≤4 \\ 0 \ \ \ \ \ \ \ \ \text{ , caso contrário} \end{cases}f(x)=⎩⎨⎧​4x​        ,0<x≤21−4x​ ,2<x≤40         , caso contraˊrio​﻿

4. Calcule

a) P(X≤1)P (X ≤ 1)P(X≤1)﻿  
b) P(X=1)P (X = 1)P(X=1)﻿  
c) P(X<1)P(X < 1)P(X<1)﻿  
d) P(X>1)P(X > 1)P(X>1)﻿  
e) P(1≤X<3)P(1 ≤ X < 3)P(1≤X<3)﻿  
f) P(1≤X≤3)P(1 ≤ X ≤ 3)P(1≤X≤3)﻿  
g) P(1<X≤3)P (1 < X ≤ 3)P(1<X≤3)﻿  
h) P(1<X<3)P(1 < X < 3)P(1<X<3)﻿

[![](Dashboard/Attachments/Untitled%206%204.png)](5%20Vari%C3%A1veis%20Aleat%C3%B3rias%20Cont%C3%ADnuas/Untitled%206.png)

5. Sabendo que 90% dos aparelhos de radiologia duram no máximo kkk﻿ anos, determine kkk﻿.

[![](Dashboard/Attachments/Untitled%207%204.png)](5%20Vari%C3%A1veis%20Aleat%C3%B3rias%20Cont%C3%ADnuas/Untitled%207.png)

tem-se:

[![](Dashboard/Attachments/Untitled%208%203.png)](5%20Vari%C3%A1veis%20Aleat%C3%B3rias%20Cont%C3%ADnuas/Untitled%208.png)

Exemplo 19

A quantidade de álcool (em dezenas de litros) que um produtor-engarrafador vende por dia é uma variável aleatória XXX﻿ com função de distribuição definida por:

F(x)={0                     ,x<0x250                   ,0≤x<525x−x250−1   ,5≤x<101                      ,x≥10F(x)= \begin{cases} 0 \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ , x<0 \\ \frac{x^2}{50} \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ , 0≤ x<5 \\ \frac{2}{5}x - \frac{x^2}{50} -1 \ \ \ , 5≤x<10 \\ 1 \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ , x≥10 \end{cases}F(x)=⎩⎨⎧​0                     ,x<050x2​                   ,0≤x<552​x−50x2​−1   ,5≤x<101                      ,x≥10​﻿

1. Determine a probabilidade do produtor-engarrafador vender entre 40 a 80 litros de álcool, por dia.

X=X =X=﻿ quantidade de álcool (em dezenas de litros) que um produtor-engarrafador vende por dia

P(4≤X≤8)=F(8)−F(4)=(25×8−8250−1)−4250=35P(4 ≤ X ≤8) = F(8) - F(4) = (\frac{2}{5} \times 8 - \frac{8^2}{50} -1) - \frac{4^2}{50} = \frac{3}{5}P(4≤X≤8)=F(8)−F(4)=(52​×8−5082​−1)−5042​=53​﻿

2. Calcule a função densidade de probabilidade da variável aleatória XXX﻿.

A função densidade de probabilidade obtém-se a partir da derivada da função de distribuição de XXX﻿,

F(x)=F’(x)F(x) = F’(x)F(x)=F’(x)﻿

Isto é, f(x)f(x)f(x)﻿ é dada por

[![](Dashboard/Attachments/E1B31341-FB81-4F9A-92BB-14EAC9BDE098.jpeg)](5%20Vari%C3%A1veis%20Aleat%C3%B3rias%20Cont%C3%ADnuas/E1B31341-FB81-4F9A-92BB-14EAC9BDE098.jpeg)

# Valor Esperado ou Média ou Esperança Matemática

O valor esperado ou média ou esperança matemática de uma variável aleatória contínua XXX﻿ representa-se por

μ=μX=E[X]\mu = \mu_X = E[X]μ=μX​=E[X]﻿

e calcula-se  
μ=E[X]=∫−∞+∞xf(x)dx\mu = E[X] = \int_{- \infty}^{+\infty} xf(x) dxμ=E[X]=∫−∞+∞​xf(x)dx﻿.

### Observação

🧮

O valor esperado é um **parâmetro de localização**, que pretende localizar o centro da distribuição de probabilidade, ou seja, pretende identificar o “centro de gravidade” da variável aleatória.

- O cálculo do valor esperado nas variáveis aleatórias contínuas faz-se de forma idêntica à realizada nas variáveis aleatórias discretas, mas em vez do “símbolo de somatório aparece o integral”.

- Ou seja, nas variáveis aleatórias discretas o valor esperado é uma média ponderada cujos pesos são as probabilidade pontuais e nas variáveis aleatórias contínuas o valor esperado refere-se à área média.

- Todas as observações e propriedades referidas para o valor esperado no caso das variáveis aleatórias discretas continuam a ser válidas quando a variável é contínua:

### Observação

Seja g(X)g(X)g(X)﻿ uma função da variável aleatória XXX﻿. Se XXX﻿ uma variável aleatória contínua, então

E[g(X)]=∫−∞+∞g(x)f(x) dxE[g(X)] = \int_{- \infty}^{+\infty}g(x)f(x)\ dxE[g(X)]=∫−∞+∞​g(x)f(x) dx﻿

### Propriedades

Sejam XXX﻿ uma variável aleatória e aaa﻿ e bbb﻿ constantes reais.

1. Se X=aX=aX=a﻿, então E[X]=E[a]=aE[X] = E[a] = aE[X]=E[a]=a﻿;

2. E[aX+b]=aE[X]+bE[aX+b] = aE[X]+bE[aX+b]=aE[X]+b﻿;

3. Sejam g(X)g(X)g(X)﻿ e h(X)h(X)h(X)﻿ funções de XXX﻿
    
    E[g(X)+h(X)]=E[g(X)]+E[h(X)]E[g(X)+h(X)] = E[g(X)]+E[h(X)]E[g(X)+h(X)]=E[g(X)]+E[h(X)]﻿.
    

Exemplo 18

De acordo com determinadas especificações técnicas de uma marca de aparelhos de radiologia, sabe-se que a sua duração (em anos) é uma vairável aleatória XXX﻿ com a seguinte função densidade de probabilidade:

f(x)={x4        ,0<x≤21−x4 ,2<x≤40         , caso contraˊriof(x) = \begin{cases} \frac{x}{4} \ \ \ \ \ \ \ \ , 0<x≤2 \\ 1- \frac{x}{4} \ , 2<x≤4 \\ 0 \ \ \ \ \ \ \ \ \text{ , caso contrário} \end{cases}f(x)=⎩⎨⎧​4x​        ,0<x≤21−4x​ ,2<x≤40         , caso contraˊrio​﻿

6. Qual a duração média dos aparelhos de radiologia?

[![](Dashboard/Attachments/B29D3C79-24B6-4F4A-BB13-A01FA8753D57.jpeg)](5%20Vari%C3%A1veis%20Aleat%C3%B3rias%20Cont%C3%ADnuas/B29D3C79-24B6-4F4A-BB13-A01FA8753D57.jpeg)

7. Calcule E[3X−2]E[3X-2]E[3X−2]﻿.

[![](Dashboard/Attachments/D64D97E7-0455-49D4-9267-66246399ADAF.jpeg)](5%20Vari%C3%A1veis%20Aleat%C3%B3rias%20Cont%C3%ADnuas/D64D97E7-0455-49D4-9267-66246399ADAF.jpeg)

# Variância = V[ ]

A variância de uma variável aleatória contínua X representa-se por

σ2=σX2=Var[X]=V[X]=E[(X−μ)2]\sigma^2 = \sigma_X^2 = Var[X] = V[X] = E[(X - \mu)^2]σ2=σX2​=Var[X]=V[X]=E[(X−μ)2]﻿

e calcula-se

σ2=V[X]=∫−∞+∞(x−μ)2f(x) dx\sigma^2 = V[X] = \int_{- \infty}^{+ \infty} (x- \mu)^2 f(x)\ dxσ2=V[X]=∫−∞+∞​(x−μ)2f(x) dx﻿.

## Observação

==A variância é um== ==**parâmetro de dispersão**====. Mede a dispersão (ao quadrado) da variável aleatória em torno do seu valor esperado.==

- Tal como foi referido para o valor médio, o cálculo da variância nas variáveis aleatórias contínuas faz-se de forma idêntica à realizada nas variáveis aleatórias discretas, mas em vez do “símbolo de somatório, aparece o integral”.

- Todas as observações e propriedades referidas para a variância no caso das variáveis aleatórias discretas continuam a ser válidas quando a variável é contínua:

### Propriedades:

---

Sejam XXX﻿ uma variável aleatória discreta e aaa﻿ e bbb﻿ constantes reais.

1. V[X]=E[X2]−E2[X];V[X] = E[X^2] - E^2[X];V[X]=E[X2]−E2[X];﻿

2. V[X]≥0;V[X] ≥ 0;V[X]≥0;﻿

3. Se X=aX=aX=a﻿, então V[X]=V[a]=0;V[X] = V[a] = 0;V[X]=V[a]=0;﻿

4. V[aX+b]=a2V[X].V[aX+b] = a^2V[X].V[aX+b]=a2V[X].﻿

# Desvio Padrão

Como já vimos, o desvio padrão é a raiz quadrada da variância:

O desvio padrão de uma variável aleatória discreta XXX﻿ representa-se por  
σ=σX\sigma = \sigma_Xσ=σX​﻿.  
e calcula-se  
σ=σX=V[X]\sigma = \sigma_X = \sqrt{V[X]}σ=σX​=V[X]​﻿

## Observação

O desvio padrão é um **parâmetro de dispersão**, é a raiz quadrada da variância. Mede a dispersão da variável aleatória em torno do seu valor esperado na mesma unidade de medida em que a variável aleatória vem expressa.

Exemplo 18

De acordo com determinadas especificações técnicas de uma marca de aparelhos de radiologia, sabe-se que a sua duração (em anos) é uma vairável aleatória XXX﻿ com a seguinte função densidade de probabilidade:

f(x)={x4        ,0<x≤21−x4 ,2<x≤40         , caso contraˊriof(x) = \begin{cases} \frac{x}{4} \ \ \ \ \ \ \ \ , 0<x≤2 \\ 1- \frac{x}{4} \ , 2<x≤4 \\ 0 \ \ \ \ \ \ \ \ \text{ , caso contrário} \end{cases}f(x)=⎩⎨⎧​4x​        ,0<x≤21−4x​ ,2<x≤40         , caso contraˊrio​﻿

8. Calcule a variância da variável aleatória X.

[![](Dashboard/Attachments/3769AC07-BB3C-4BCA-89AE-223F55E523DC.jpeg)](5%20Vari%C3%A1veis%20Aleat%C3%B3rias%20Cont%C3%ADnuas/3769AC07-BB3C-4BCA-89AE-223F55E523DC.jpeg)

[![](Dashboard/Attachments/C78F6D83-581A-4D2E-BC73-EF4C7A44D6DA.jpeg)](5%20Vari%C3%A1veis%20Aleat%C3%B3rias%20Cont%C3%ADnuas/C78F6D83-581A-4D2E-BC73-EF4C7A44D6DA.jpeg)

9. Calcule o desvio padrão da variável aleatória XXX﻿.

Pretende-se o desvio padrão de X:

σ=V[X]=23=0.816\sigma = \sqrt{V[X]} = \sqrt{\frac{2}{3}} = 0.816σ=V[X]​=32​​=0.816﻿ anos

10. Calcule V[-3X -2].

Recorrendo à propriedade V[aX+b]=a2V[X]V[aX + b] = a^2V[X]V[aX+b]=a2V[X]﻿ tem-se

V[−3X−2]=(−32)V[X]=9×23=6V[-3X-2]= (-3^2)V[X] = 9 \times \frac{2}{3} = 6V[−3X−2]=(−32)V[X]=9×32​=6﻿Exemplo 19

A quantidade de álcool (em dezenas de litros) que um produtor-engarrafador vende por dia é uma variável aleatória XXX﻿ com função de distribuição definida por:

F(x)={0                     ,x<0x250                   ,0≤x<525x−x250−1   ,5≤x<101                      ,x≥10F(x)= \begin{cases} 0 \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ , x<0 \\ \frac{x^2}{50} \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ , 0≤ x<5 \\ \frac{2}{5}x - \frac{x^2}{50} -1 \ \ \ , 5≤x<10 \\ 1 \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ , x≥10 \end{cases}F(x)=⎩⎨⎧​0                     ,x<050x2​                   ,0≤x<552​x−50x2​−1   ,5≤x<101                      ,x≥10​﻿

3. Qual a quantidade média de álcool vendida por dia?

Para o cálculo do valor esperado é necessário conhecer-se a função densidade de probabilidade, anteriormente calculada e dada por

[![](Dashboard/Attachments/E1B31341-FB81-4F9A-92BB-14EAC9BDE098.jpeg)](5%20Vari%C3%A1veis%20Aleat%C3%B3rias%20Cont%C3%ADnuas/E1B31341-FB81-4F9A-92BB-14EAC9BDE098.jpeg)

[![](Dashboard/Attachments/70C2D471-8DFA-40C4-91DB-E277F7809452.jpeg)](5%20Vari%C3%A1veis%20Aleat%C3%B3rias%20Cont%C3%ADnuas/70C2D471-8DFA-40C4-91DB-E277F7809452.jpeg)

---

![](Dashboard/Attachments/icons_questions%2019.png)

The **Sentence Method** is a simplified way to record notes on the fly. You should revisit your note after it is complete to restructure the information for easier reviewing later.