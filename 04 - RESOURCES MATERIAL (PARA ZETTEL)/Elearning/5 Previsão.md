---
tags:
  - elearning
dg-publish: "true"
dg-note-icon: lackluster
noteIcon: lackluster
---

![](Dashboard/Attachments/icons_notes--sentence%2017.png)

# 5. Previsão

|   |   |
|---|---|
|![](Dashboard/Attachments/arrow-northeast_gray%201188.svg)Subject|[![](Dashboard/Attachments/icons_graduate%2017.png)3. Regressão Linear Simples](../Subjects/3%20Regress%C3%A3o%20Linear%20Simples%209558cc6271874dbc880a7ea7990d09e0.html)|
|![](Dashboard/Attachments/calendar_gray%201250.svg)Date Created|@June 13, 2022|
|![](Dashboard/Attachments/checkmark-square_gray%20669.svg)To Review?||
|![](Dashboard/Attachments/formula_gray%20488.svg)Review Due||
|![](Dashboard/Attachments/clock_gray%20120.svg)Last Edited|@June 27, 2022 12:57 PM|

# Metodologia

4. Previsão

- Depois de encontrado o modelo de regressão linear que se adapta aos dados,
    
    y^=a+bx\widehat y = a + bxy​=a+bx﻿,
    
    é possível efetuar **previsões** para **yyy**﻿ com base em valores de xxx﻿.
    

- Só deve ser feita previsão para y com base em valores de x dentro do intervalo analisado ou para valores muito próximos do intervalo analisado. Quando nos afastamos muito, não sabemos se a relação linear ainda se mantém, logo a previsão pode ser absurda.

Exemplo 1

Um psicólogo efetuou uma pesquisa com o objetivo de analisar a forma como as crianças aprendem um determinado jogo. Das diversas variáveis observadas foram registados o número de jogos efetuados (X)(X)(X)﻿ e o número de erros realizados no jogo (Y)(Y)(Y)﻿:

[![](Dashboard/Attachments/DED494C8-F291-41C6-B0CA-A57B00E496F1%201.jpeg)](5%20Previs%C3%A3o/DED494C8-F291-41C6-B0CA-A57B00E496F1.jpeg)

6. Obtenha estimativas para o número de erros que uma criança comete quando joga 5 vezes o jogo e quando joga 50 vezes o jogo.

Uma estimativa para o nu ́mero de erros que uma crian ̧ca comete quando

1. joga 5 vezes o jogo:  
    y^(5)=8.2489−0.5326×5=5.586≈6 erros\widehat y(5) = 8.2489 − 0.5326 × 5 = 5.586 ≈ 6 \ \text{erros}y​(5)=8.2489−0.5326×5=5.586≈6 erros﻿

2. joga 50 vezes o jogo: ==valor muito afastado dos valores observados==  
    y^(50)=8.2489−0.5326×50=−18.381\widehat y (50) = 8.2489 − 0.5326 × 50 = −18.381y​(50)=8.2489−0.5326×50=−18.381﻿ ==ABSURDO!==

Mesmo que a estimativa para 50 jogos tivesse dado um valor válido, continuaríamos a não ter qualquer confiança nessa previsão, pois o valor 50 encontra-se muito afastado dos valores observados, [1, 11]. Embora o modelo tenha sido considerado adequado (diagrama de de dispersão, coeficiente de correlação linear e resíduos, todos levaram a considerar o modelo adequado), nada nos garante que a reta obtida se mant ́em para valores afastado dos observados.

### Observação

Suponha que calculou o seguinte modelo de regressão

y^=a+bx\widehat y = a + bxy​=a+bx﻿,

e pretende efetuar previsões para xxx﻿ com base em valores de yyy﻿.

Com a reta de regressão anterior apenas faz sentido estimar valores de yyy﻿. Como agora pretende estimar valores de xxx﻿, então significa que ==XXX==﻿ passa a ser a ==variável dependente== e ==YYY==﻿ a ==variável independente==, sendo necessário calcular a reta de regressão correspondente. Ou seja, ir a todas as fórmulas apresentadas anteriormente e onde está xxx﻿ colocar yyy﻿ e onde está yyy﻿ colocar xxx﻿ e assim obtém

x^=a∗+b∗y\widehat x = a^* + b^*yx=a∗+b∗y﻿

Com a∗=x‾−b∗y‾    e    b∗=rXY×sxsya^* = \overline x - b^* \overline y \ \ \ \ \text{e} \ \ \ \ b^* = r_{XY} \times \frac {s_x}{s_y}a∗=x−b∗y​    e    b∗=rXY​×sy​sx​​﻿

Exemplo 1

Um psicólogo efetuou uma pesquisa com o objetivo de analisar a forma como as crianças aprendem um determinado jogo. Das diversas variáveis observadas foram registados o número de jogos efetuados (X)(X)(X)﻿ e o número de erros realizados no jogo (Y)(Y)(Y)﻿:

[![](Dashboard/Attachments/DED494C8-F291-41C6-B0CA-A57B00E496F1%201.jpeg)](5%20Previs%C3%A3o/DED494C8-F291-41C6-B0CA-A57B00E496F1.jpeg)

7. Suponha que a criança errou apenas 1 vez e pretende obter uma estimativa do número de jogos que a criança fez. Como deve fazer?

Como agora pretende-se estimar valores de xxx﻿, então significa que ==XXX==﻿ (número de jogos) passa a ser a ==variável dependente== e ==YYY==﻿ (número de erros) a ==variável independente==, sendo necessário calcular a reta de regressão correspondente: x^=a∗+b∗y\widehat x = a^∗ + b^∗yx=a∗+b∗y﻿.

Ou seja, ir a todas as fórmulas apresentadas anteriormente e onde está x colocar y e onde está y colocar x:

b∗=∑i=1n(yi−y‾)(xi−x‾)∑i=1n(yi−y‾)2    e    a∗=x‾−b∗y‾b^* = \frac {\sum_{i=1}^n (y_i - \overline y)(x_i - \overline x)}{\sum_{i=1}^n(y_i - \overline y)^2} \ \ \ \ \text{e} \ \ \ \ a^* = \overline x - b^*\overline yb∗=∑i=1n​(yi​−y​)2∑i=1n​(yi​−y​)(xi​−x)​    e    a∗=x−b∗y​﻿ (uma possibilidade)

b∗=∑i=110(yi−5)(xi−6.1)∑i=1010(yi−5)2=−5846=−1.2609b^* = \frac {\sum_{i=1}^10(y_i - 5)(x_i - 6.1)}{\sum_{i=10}^10(y_i - 5)^2} = \frac {-58}{46} = -1.2609b∗=∑i=101​0(yi​−5)2∑i=11​0(yi​−5)(xi​−6.1)​=46−58​=−1.2609﻿

a∗=6.1−(−1.2609)×5=12.4045a^* = 6.1 - (-1.2609) \times 5 = 12.4045a∗=6.1−(−1.2609)×5=12.4045﻿

Assim obtém-se a reta de regressão

x^=12.4045−1.2609y\widehat x = 12.4045 - 1.2609yx=12.4045−1.2609y﻿.

Voltando à questão:

x^(1)=12.4045−1.2609×1=11.144≈11\widehat x(1) = 12.4045 - 1.2609 \times 1 = 11.144 \approx 11x(1)=12.4045−1.2609×1=11.144≈11﻿ jogos

![](Dashboard/Attachments/icons_questions%2017.png)

The **Sentence Method** is a simplified way to record notes on the fly. You should revisit your note after it is complete to restructure the information for easier reviewing later.