# Documentação Writer Bots On The Go
### Índice
<a href="#logicacontem">1- Objetivo</a><br/>
<a href="#logicas">1.1 - Lógicas</a><br/>
<a href="#logicacontem">1.1.1 - Lógica Contém</a><br/>
<a href="#logicainteligente">1.1.2 - Lógica Contém Inteligente</a><br/>
---
<a id="objetivo"></a>
## 1- Objetivo
Esse documento tem como objetivo descrever as possíveis lógicas em um bot On The Go
<a id="logicas"></a>
### 1.1 - Lógicas
<a id="logicacontem"></a>
#### 1.1.1 - Lógica Contém
A <b>Lógica Contém</b> verifica se na P25 (Pergunta 25), o item 1 foi selecionado.<br/> 
Caso seja verdade, o usuário é direcionado para o índice 35, caso contrário o usuário será direcionado para o índice 38.<br/>

![alt text](https://github.com/onthegosurvey/bot-docs/blob/main/images/img1.png?raw=true)

No banco de dados esta lógica é escrita da seguinte forma:

```/logic/ if has @d666@op1@```

Onde <b>d666</b> refere-se ao uid da pergunta e <b>op1</b> refere-se a opção para qual se criou a lógica. 

Tipos de perguntas compatívies: <b>Única e Múltipla Escolha</b>
<a id="logicainteligente"></a>
#### 1.1.2 - Lógica Contém Inteligente

A <b>Lógica Contém Inteligente</b> verifica se na P2 (Pergunta 2), o texto MarcaX foi selecionado.<br/>
Caso seja verdade, o usuário é direcionado para o índice 5, caso contrário o usuário será direcionado para o índice 6.<br/>

![alt text](https://github.com/onthegosurvey/bot-docs/blob/main/images/img4.png?raw=true)

No banco de dados esta lógica é escrita da seguinte forma:

```/logic/ if @95n1@ contains[MarcaX]```

Onde <b>95n1</b> refere-se ao uid da pergunta e [MarcaX] refere-se a opção para qual se criou a lógica.

Tipos de perguntas compatívies: <b>Única e Múltipla Escolha</b>