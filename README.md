# Documentação Writer Bots On The Go
### Índice
- [Objetivo](#objetivo)<br/>
- [Lógicas](#lógicas)<br/>
- [1 - Lógica Contém](#1-lógica-contém)<br/>
- [2 - Lógica Contém Inteligente](#2-lógica-contém-inteligente)</a><br/>
- [3 - Lógica Valor de Parâmetro](#3-lógica-valor-de-parâmetro)</a><br/>
- [4 - Lógica Peso](#4-lógica-peso)</a><br/>
- [Painéis](#painéis)<br/>
---
<a id="objetivo"></a>
## Objetivo
Esse documento tem como objetivo descrever as possíveis lógicas em um bot On The Go
## Lógicas

---

### 1-Lógica Contém
A <b>Lógica Contém</b> verifica se na P25 (Pergunta 25), o item 1 foi selecionado.<br/> 
Caso seja verdade, o usuário é direcionado para o índice 35, caso contrário o usuário será direcionado para o índice 38.<br/>

![alt text](https://github.com/onthegosurvey/bot-docs/blob/main/images/img1.png?raw=true)

No banco de dados esta lógica é escrita da seguinte forma:

```/logic/ if has @d666@op1@```

Onde <b>d666</b> refere-se ao uid da pergunta e <b>op1</b> refere-se a opção para qual se criou a lógica. 

Tipos de perguntas compatívies: <b>Única e Múltipla Escolha</b>

---

### 2-Lógica Contém Inteligente

A <b>Lógica Contém Inteligente</b> verifica se na P2 (Pergunta 2), o texto MarcaX foi selecionado.<br/>
Caso seja verdade, o usuário é direcionado para o índice 5, caso contrário o usuário será direcionado para o índice 6.<br/>

![alt text](https://github.com/onthegosurvey/bot-docs/blob/main/images/img4.png?raw=true)

No banco de dados esta lógica é escrita da seguinte forma:

```/logic/ if @95n1@ contains[MarcaX]```

Onde <b>95n1</b> refere-se ao uid da pergunta e [MarcaX] refere-se a opção para qual se criou a lógica.

Tipos de perguntas compatívies: <b>Única e Múltipla Escolha</b>

---

### 3-Lógica Valor de Parâmetro

A <b>Lógica Valor de Parâmetro</b> verifica o parâmetro adicionando no primeiro campo possui o valor <b>offer</b><br/>
Caso seja verdade, o usuário é direcionado para o índice 61, caso contrário o usuário será direcionado para o índice 62.<br/>

![alt text](https://github.com/onthegosurvey/bot-docs/blob/main/images/img2.png?raw=true)

No banco de dados esta lógica é escrita da seguinte forma:

```/logic/ if has @param@disparador@offer@```

Compatível com qualquer parâmetro e valor.

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

## Painéis
A plataforma On The Go pode se conectar a diversos paineis diferentes, mas cada um deles possui algumas especificidades. 
Observações importantes para configurar os links de painéis:<br/>

- Lembrar de colocar o %s no parâmetro do painel que deve receber o seu Id. Conforme imagem abaixo.
- Caso a pesquisa possua mais de um painel, será necessário criar uma [Lógica Valor de Parâmetro](#3-lógica-valor-de-parâmetro) para identificar de qual painel o respondente veio

![alt text](https://github.com/onthegosurvey/bot-docs/blob/main/images/img3.png?raw=true)


