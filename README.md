# Documentação Writer Bots On The Go
### Índice
- [Objetivo](#objetivo)<br/>
- [Lógicas](#-lógicas)<br/>
- [1 - Lógica Contém](#1-lógica-contém)<br/>
- [2 - Lógica Contém Inteligente](#2-lógica-contém-inteligente)</a><br/>
- [3 - Lógica Valor de Parâmetro](#3-lógica-valor-de-parâmetro)</a><br/>
- [4 - Lógica Peso](#4-lógica-peso)</a><br/>
- [5 - Lógica Contém Opções Selecionadas nos Itens](#5-lógica-contém-opções-selecionadas-nos-itens)
- [6 - Lógica Somar Pesos](#6-lógica-somar-pesos)
- [7 - Lógica Top X Contém Texto](#7-lógica-top-x-contém-texto)
- [Painéis](#painéis)<br/>
---
<a id="objetivo"></a>
## Objetivo
Esse documento tem como objetivo descrever as possíveis lógicas em uma pesquisa On The Go.<br/><br/>
## Lógicas
---
### 1-Lógica Contém
A <b>Lógica Contém</b> verifica se na P25 (Pergunta 25), o item 1 foi selecionado.<br/> 
Caso seja verdade, o usuário é direcionado para o índice 35, caso contrário o usuário será direcionado para o índice 38.<br/>

![alt text](https://github.com/onthegosurvey/bot-docs/blob/main/images/img1.png?raw=true)

No banco de dados esta lógica é escrita da seguinte forma:

```/logic/ if has @d666@op1@```

Onde <b>d666</b> refere-se ao uid da pergunta e <b>op1</b> refere-se a opção para qual se criou a lógica. 

Tipos de perguntas compatívies: <b>Única e Múltipla Escolha</b>.<br/><br/>

---

### 2-Lógica Contém Inteligente

A <b>Lógica Contém Inteligente</b> verifica se na P2 (Pergunta 2), o texto MarcaX foi selecionado.<br/>
Caso seja verdade, o usuário é direcionado para o índice 5, caso contrário o usuário será direcionado para o índice 6.<br/>

![alt text](https://github.com/onthegosurvey/bot-docs/blob/main/images/img4.png?raw=true)

No banco de dados esta lógica é escrita da seguinte forma:

```/logic/ if @95n1@ contains[MarcaX]```

Onde <b>95n1</b> refere-se ao uid da pergunta e [MarcaX] refere-se a opção para qual se criou a lógica.

Tipos de perguntas compatívies: <b>Única e Múltipla Escolha</b>.<br/><br/>

---

### 3-Lógica Valor de Parâmetro

A <b>Lógica Valor de Parâmetro</b> verifica o parâmetro adicionando no primeiro campo possui o valor <b>offer</b><br/>
Caso seja verdade, o usuário é direcionado para o índice 61, caso contrário o usuário será direcionado para o índice 62.<br/>

![alt text](https://github.com/onthegosurvey/bot-docs/blob/main/images/img2.png?raw=true)

No banco de dados esta lógica é escrita da seguinte forma:

```/logic/ if has @param@disparador@offer@```

Compatível com qualquer parâmetro e valor.<br/><br/>

---

### 4-Lógica Peso

A <b>Lógica Peso</b> verifica se o valor somado dos itens selecionados na P2 (Pergunta 2) é Exatamente, Maior que, Menor que, Maior ou igual, Menor ou igual ao valor digitado no campo a frente, nesta imagem abaixo por exemplo o valor 5.<br/>
Caso seja verdade, o usuário é direcionado para o índice 5, caso contrário o usuário será direcionado para o índice 6.<br/>

![alt text](https://github.com/onthegosurvey/bot-docs/blob/main/images/img5.png?raw=true)

Tipos de perguntas compatívies: <b>Única e Múltipla Escolha</b>

No banco de dados esta lógica é escrita da seguinte forma:

- Exatamente: ```/logic/ if sum(@95n1@) == 5```
- Maior que ```/logic/ if sum(@95n1@) > 5```
- Menor que ```/logic/ if sum(@95n1@) < 5```
- Maior ou igual ```/logic/ if sum(@95n1@) >= 5```
- Menor ou igual ```/logic/ if sum(@95n1@) <= 5```
  <br/><br/>
---

### 5-Lógica Contém Opções Selecionadas nos Itens

A <b>Lógica Contém Opções Selecionadas nos Itens</b> verifica se no item 3 possui pelo menos uma das opções (op4 ou op5) selecionada.<br/>

![alt text](https://github.com/onthegosurvey/bot-docs/blob/main/images/img6.png?raw=true)

Essa lógica também aceita mais de um item conforme imagem abaixo:

![alt text](https://github.com/onthegosurvey/bot-docs/blob/main/images/img7.png?raw=true)

Tipo de pergunta compatível: <b>Matriz</b>

No banco de dados esta lógica é escrita da seguinte forma:

```/code/ if @aio1@it2@ containsInMatriz [op1,op2,op3,op4,op5,op6]```

Onde <b>aio1</b> refere-se ao uid da pergunta e <b>it2</b> refere-se ao(s) item(ns).<br/><br/>

---

### 6-Lógica Somar Pesos

A <b>Lógica Somar Pesos</b> soma os pesos das opções dos itens selecionados em uma matriz<br/>

![alt text](https://github.com/onthegosurvey/bot-docs/blob/main/images/img8.png?raw=true)

Tipo de pergunta compatível: <b>Matriz</b>

No banco de dados esta lógica é escrita da seguinte forma:

```/code/ if sumMatrizWeight(8vn1) >= 90```

Onde <b>8vn1</b> refere-se ao uid da matriz.<br/><br/>

---

### 7-Lógica Top X Contém Texto

A <b>Lógica Top X Contém</b> verifica se entre as Top (2) de uma múltipla contém o texto a seguir.<br/>

![alt text](https://github.com/onthegosurvey/bot-docs/blob/main/images/img9.png?raw=true)

Tipo de pergunta compatível: <b>Múltipla Escolha</b>

No banco de dados esta lógica é escrita da seguinte forma:

```/code/ if top2contains @m9h3@Carrefour Express@```

Onde 2 é a quantidade de itens que a lógica irá procurar o texto e <b>m9h3</b> refere-se ao uid da múltipla escolha.<br/><br/>

---

## Painéis
A plataforma On The Go pode se conectar a diversos paineis diferentes, mas cada um deles possui algumas especificidades. 
Observações importantes para configurar os links de painéis:<br/>

- Lembrar de colocar o %s no parâmetro do painel que deve receber o seu Id. Conforme imagem abaixo.
- Caso a pesquisa possua mais de um painel, será necessário criar uma [Lógica Valor de Parâmetro](#3-lógica-valor-de-parâmetro) para identificar de qual painel o respondente veio

![alt text](https://github.com/onthegosurvey/bot-docs/blob/main/images/img3.png?raw=true)


