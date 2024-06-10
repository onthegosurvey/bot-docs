# Documentação Writer Bots On The Go
## 1- Objetivo
Esse documento tem como objetivo descrever as possíveis lógicas em um bot On The Go
### 1.1 - Lógicas
<a href="#logicacontem">1.1.1 - Lógica Contém</a><br/>
<a id="logicacontem"></a>
#### 1.1.1 - Lógica Contém
A <b>Lógica Contém</b> verifica se na P25 (Pergunta 25), o item 1 foi selecionado.<br/> 
Caso seja verdade, o usuário é direcionado para o índice 35, caso contrário o usuário será direcionado para o índice 38.<br/>

![alt text](https://github.com/onthegosurvey/bot-docs/blob/main/images/img1.png?raw=true)

No banco de dados esta lógica é escrita da seguinte forma:

```/logic/ if has @d666@op1@```

Onde <b>d666</b> refere-se ao uid da pergunta e <b>op1</b> refere-se a opção para qual se criou a lógica. 

Tipos de perguntas compatívies: <b>Única e Múltipla Escolha</b>

#### 1.1.2 - Lógica Contém