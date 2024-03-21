# Unifor
**Nome:** Francisco Luã Lima Cruz <br>
**Disciplina:** Raciocínio Lógico Algorítmico

## Exercício 01
Atualize o algoritmo para determinar se um número inteiro e positivo é par ou ímpar, usando um laço condicional para aceitar apenas números maiores ou iguais a zero.

### Fluxograma:
```mermaid
flowchart TD
A([Inicio]) --> B{{'Digite um número inteiro e positivo: '}}
B --> BB[\n\]
BB --> C{n <= 0}
C --FALSE--> D{n % 2 == 0}
D --FALSE--> E{{'O número é ímpar!}} --> Z
D --TRUE--> F{{'O número é par!}} --> Z
C --TRUE--> G{{'O número deve ser maior que zero! Digite o valor novamente: '}}
G --> H[\n\]
H --LOOP--> C
Z([Fim])
```

### Pseudocódigo:

```
ALGORITMO DeterminaParImpar
DECLARE n: INT

INICIO
ESCREVA "Digite um número inteiro e positivo: "
LEIA n
ENQUANTO n <= 0 FAÇA
  ESCREVA "O número deve ser maior que zero! Digite o valor novamente: "
  LEIA n
FIM_ENQUANTO

SE n % 2 == 0 ENTAO
  ESCREVA "O número é par!"
SENAO
  ESCREVA "O número é ímpar!"
FIM_SE
FIM
```

### Teste de mesa:

| n | n <= 0 | it | n % 2 == 0 | Saída |
| -- | -- | -- | -- | -- |
| -1 | V | 1 | | "O número deve ser maior que zero! Digite o valor novamente: "|
| -3 | V | 2 | | "O número deve ser maior que zero! Digite o valor novamente: "|
| 5 | F | | F | "O número é ímpar!" |
| 8 | F | | F | "O número é par!" |

## Exercício 02
Faça um algoritmo que exiba na tela uma contagem de 0 até 30, exibindo apenas os múltiplos de 3.

### Fluxograma:

```mermaid
flowchart TD
A([Inicio]) --> B{{'O programa irá exibir apenas múltiplos de 3, que estão entre 0 até 30, e incluindo 0 e 30.'}}
B --> C[[i=0 ATÉ 30 passo 3]]
C --> Z
C --> D{{'Número: ',i}}
D --LOOP--> C
Z([Fim])
```

### Pseudocódigo:

```
ALGORITMO Print_Multiplos_De_3
ESCREVA "O programa irá exibir apenas múltiplos de 3, que estão entre 0 até 30, e incluindo 0 e 30."
INICIO
PARA i DE 0 ATÉ 30 PASSO 3 FAÇA
  ESCREVA "Número: ", i
FIM_PARA
FIM
```

### Teste de mesa:
| it | i | Saida |
| -- | -- | -- |
| 1 | 0 | "Número: 0" |
| 2 | 3 | "Número: 3" |
| 3 | 6 | "Número: 6" |
| 4 | 9 | "Número: 9" |
| 5 | 12 | "Número: 12" |
| 6 | 15 | "Número: 15" |
| 7 | 18 | "Número: 18" |
| 8 | 21 | "Número: 21" |
| 9 | 24 | "Número: 24" |
| 10 | 27 | "Número: 27" |
| 11 | 30 | "Número: 30" |

## Exercício 03
Dada uma sequência de números inteiros, calcular a sua soma. Por exemplo, para a sequência {12, 17, 4, -6, 8, 0}, o seu programa deve escrever o número 35.

### Fluxograma:

```mermaid
flowchart TD
A([Inicio]) --> B{{'Escreva os números que você queira somar. A quantidade de números pode ser qualquer uma.'}}
B --> C{{'Digite -1 quando finalizar sua lista de números:'}}
C --> D[flag = TRUE]
D --> E[soma = 0]
E --> F{flag}
F --FALSE--> G{{'A sua soma vale: ', soma}} --> Z
F --TRUE--> H[\n\]
H --> I{n == 'Q' OR n == 'q'}
I --FALSE--> J[soma += n]
J --LOOP--> F
I --TRUE--> K[flag = FALSE]
K --LOOP--> F
Z([Fim])
```

### Pseudocódigo:

```
ALGORITMO SomaListaNumeros
DECLARE flag: BOOL
DECLARE n, soma: FLOAT

INICIO
ESCREVA "Escreva os números que você queira somar. A quantidade de números pode ser qualquer uma."
ESCREVA "Digite Q ou q quando finalizar sua lista de números:"

flag <- TRUE 
soma <- 0
ENQUANTO flag FAÇA
  LEIA n
  SE n == '-1' ENTAO
    flag <- FALSE
  SENAO
    soma <- soma + n
  FIM_SE
FIM_ENQUANTO
ESCREVA "Sua soma vale: ", soma
FIM
```

### Teste de mesa:

| flag | it | n | soma | mudança_flag |Saída |
| -- | -- | -- | -- | -- |
| TRUE | 1 | -1 | 0 | FALSE | Sua soma vale: 0 |
| TRUE | 1 | 2 | 2 | | |
| TRUE | 2 | 5 | 7 | | |
| TRUE | 3 | 3 | 10 | | |
| TRUE | 4 | -1 | | FALSE | Sua soma vale: 10 |


## Exercício 04

Escreva um programa que leia a nota de diversos alunos, até que seja digitada uma nota negativa. Nesse momento, ele mostra a média aritmética de todas as notas lidas e quantas notas foram lidas. Ex. Foram lidas 14 notas. A média aritmética é 6.75!

### Fluxograma:

```mermaid
flowchart TD
A([Inicio]) --> B{{'Digite a nota de todos os alunos para obter a média. Quando finalizar sua lista, digite um valor negativo:'}}
B --> D[flag = TRUE]
D --> E[soma = 0]
E --> F[cont = 0]
F --> G{flag}
G --FALSE--> c{cont == 0} --FALSE--> H[media = soma / cont]
c --TRUE--> d{{'Você não digito nenhum valor!'}} --> Z
H --> I{{'A média dos alunos vale: ', media}} --> Z
G --TRUE--> J[\nota\]
J --> L{nota >= 0}
L --FALSE--> M[flag = FALSE] --LOOP--> G
b --LOOP--> G
L --TRUE--> N[soma += nota]
N --> O[cont += 1]
O --LOOP--> G

Z([Fim])
```

### Pseudocódigo:

```
ALGORITMO Calcula_Media_Diversos_Alunos
DECLARE nota, soma, media: FLOAT
DECLARE cont: INT
DECLARE flag: BOOL
INICIO
cont <- 0       // Inicializa, igual a 0, o contador de alunos.
flag <- TRUE    // Inicializa como TRUE a variável flag para controlar o loop
ESCREVA "Digite a nota de todos os alunos para obter a média. Quando finalizar sua lista, digite um valor negativo: "
ENQUANTO flag FAÇA
  LEIA nota
  SE nota >= 0 ENTAO
    soma <- soma + nota // Acumulador de notas
    cont <- cont + 1    // Incrementa 1 ao contador de alunos

  SENAO                // Quando digitar uma nota negativa sairá do loop
    flag <- FALSE      // atribui FALSE para flag saindo, assim, do loop

  FIM_SE
// Isso existe, pois há uma possibilidade da pessoa digitar uma nota negativa, fazendo cont == 0. (soma / 0) iria quebrar
SE cont == 0 ENTAO 
  ESCREVA "Você não digitou nenhuma nota!"
SENAO
  media = soma / cont
  ESCREVA "A média dos alunos vale: , media"
FIM_SE
FIM
```

### Teste de mesa:

| flag | it | cont | nota |nota >= 0 | soma | cont + 1 | mudança_flag | cont == 0 | media |Saída |
| -- | -- | -- | -- | -- | -- | -- | -- | --| -- | -- |
| TRUE | 1 | 0 | -5 | F | | | FALSE | V | | Você não digitou nenhuma nota!|
| TRUE | 1 | 0 | 0 | F | | | FALSE | V | | Você não digitou nenhuma nota!|
| TRUE | 1 | 0 | 5 | V | 5 | 1 | | | | |
| TRUE | 2 | 1 | 13 | V | 18 | 2 | | | | |
| TRUE | 3 | 2 | 7 | V | 25 | 3 | | | | |
| TRUE | 4 | 3 | -5 | F | | | FALSE | | 8.33 | A média dos alunos vale: 8.33 |
