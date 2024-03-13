# Unifor
**Professor:**
**Disciplina:**


### Exercício 1:
Represente, em fluxograma e pseudocódigo, um algoritmo para determinar se um número inteiro e positivo é par ou impar.

#### Fluxograma:

```mermaid
flowchart TD

A([Inicio]) --> B{{'Insira um valor inteiro e positivo: '}}
B --> C[/n1/]
C --> D{n1 % 1 != 0 OR n1 < 0}
D --TRUE--> E{{'O valor digitado não é positivo ou inteiro. Insira o valor novamente.'}}
E --> F[/n1/]

D --> G{n1 % 2 == 0}
G --FALSE--> H{{'O número é ímpar!'}} --> Z
G --TRUE--> I{{'O valor é inteiro!'}} --> Z

Z([FIM])
```

#### Pseudocódigo:

```
ALGORITMO par_impar
DECLARE n1: INTEIRO
INICIO
ESCREVA "Insira um valor inteiro e positivo: "
LEIA n1
ENQUANTO n1 != 0 and n1 < 0 FAÇA
  ESCREVA "O valor digitado precisa ser inteiro e positivo. Insira o valor novamente: "
  LEIA n1
FIM_ENQUANTO
SE n1 % 2 == 0 ENTAO
  ESCREVA "O valor é par!"

SENAO
  ESCREVA "O valor é ímpar!"

```

#### Teste de mesa


### Exercício 2:
Faça um algoritmo que exiba na tela uma contagem de 0 até 30, exibindo apenas os múltiplos de 3.

#### Fluxograma:

```mermaid
flowchart TD

A([Inicio]) --> B[i DE 0 ATÉ 30 PASSO 1]
B --> C{{'Número ', i}}
C --> B

```



