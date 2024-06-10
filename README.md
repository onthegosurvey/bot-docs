# Documentação Writer Bots On The Go
### Índice
- [Objetivo](#objetivo)<br/>
- [Lógicas](#lógicas)<br/>
- [Lógica Contém](#lógica-contém)<br/>
- [Lógica Contém Inteligente](#lógica-contém-inteligente)</a><br/>
---
<a id="objetivo"></a>
## Objetivo
Esse documento tem como objetivo descrever as possíveis lógicas em um bot On The Go
### Lógicas
### Lógica Contém
A <b>Lógica Contém</b> verifica se na P25 (Pergunta 25), o item 1 foi selecionado.<br/> 
Caso seja verdade, o usuário é direcionado para o índice 35, caso contrário o usuário será direcionado para o índice 38.<br/>

![alt text](https://github.com/onthegosurvey/bot-docs/blob/main/images/img1.png?raw=true)

No banco de dados esta lógica é escrita da seguinte forma:

```/logic/ if has @d666@op1@```

Onde <b>d666</b> refere-se ao uid da pergunta e <b>op1</b> refere-se a opção para qual se criou a lógica. 

Tipos de perguntas compatívies: <b>Única e Múltipla Escolha</b>
### Lógica Contém Inteligente

A <b>Lógica Contém Inteligente</b> verifica se na P2 (Pergunta 2), o texto MarcaX foi selecionado.<br/>
Caso seja verdade, o usuário é direcionado para o índice 5, caso contrário o usuário será direcionado para o índice 6.<br/>

![alt text](https://github.com/onthegosurvey/bot-docs/blob/main/images/img4.png?raw=true)

No banco de dados esta lógica é escrita da seguinte forma:

```/logic/ if @95n1@ contains[MarcaX]```

Onde <b>95n1</b> refere-se ao uid da pergunta e [MarcaX] refere-se a opção para qual se criou a lógica.

Tipos de perguntas compatívies: <b>Única e Múltipla Escolha</b>