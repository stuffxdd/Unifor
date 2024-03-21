# Unifor

**Nome:** Francisco Luã <br>
**Disciplina:** Raciocínio lógico algorítmico

## Lista de exercícios 01

### Exercício 01
Represente, em fluxograma e pseudocódigo, um algoritmo para determinar se um número inteiro e positivo é par ou impar.

##### Fluxograma:


```mermaid
flowchart TD
A([Inicio]) --> B{{Digite um número positivo: }}
B --> C[\numero\]
C --> D{numero <= 0}
D --FALSE--> E{numero % 2 == 0}
E --FALSE--> F{{'O número é ímpar!'}} --> Z
E --TRUE--> G{{'O número é par!'}} --> Z
D --TRUE--> H{{'O número precisa positivo e maior que zero. Zero é elemento neutro aditivo. }} --> Z
Z([Fim])

```

#### Pseudocódigo:

```
ALGORITMO verif_par_impar
DECLARE numero: INTEIRO
INICIO
ESCREVA "Digite um número: "
LEIA numero

SE numero <= 0 ENTAO
  ESCREVA "O número precisa ser positivo e maior que zero (zero é elemento neutro aditivo)."

SENAO
  SE numero % 2 == 0 ENTAO
    ESCREVA "O número é par."
  SENAO
    ESCREVA "O número é ímpar."
    FIM_SE
FIM_SE
FIM

```

#### Teste de mesa:
| numero | numero <= 0 | numero % 2 == 0 | Saída |
| -- | ---  | -- | -- | 
| -1 | V |  | "O número precisa ser positivo e maior que zero (zero é elemento neutro aditivo)." |
| 0  | V |  | "O número precisa ser positivo e maior que zero (zero é elemento neutro aditivo)." |
| 15 | F | F | "O número é ímpar." |
| 16 | F | V | "O número é par." |

### Exercício 02

Represente, em fluxograma e pseudocódigo, um algoritmo para calcular o novo salário de um funcionário. Sabe-se que os funcionários que recebem atualmente salário de até R$ 500 terão um aumento de 20%; os demais terão aumento de 10%.

##### Fluxograma:

```mermaid
flowchart TD
A([Inicio]) --> B{{Digite seu salário: }}
B --> C[\sal\]
C --> D{sal < 0}
D --FALSE--> E{sal <= 500}
E --FALSE--> G[nov_sal = sal * 1,1] --> a{{'O seu novo salário vale: ', nov_sal}} --> Z
E --TRUE--> F[nov_sal = sal * 1,2] --> b{{'O seu novo salário vale: ', nov_sal}} --> Z
D --TRUE--> H{{O valor precisa ser positivo.}} --> Z

Z([Fim])

```

#### Pseudocódigo:

```
ALGORITMO calcula_novo_salario
DECLARE sal, nov_sal: FLOAT
ESCREVA "Digite seu salário"
INICIO
LEIA sal
SE sal < 0 ENTAO
  ESCREVA "Seu salário deve ser positivo"

SENAO
  SE sal <= 500 ENTAO
    nov_sal = sal * 1,2
    ESCREVA "O seu novo salário vale: ", nov_sal

  SENAO
    nov_sal = sal * 1,1
  FIM_SE
FIM_SE
FIM
```

#### Teste de mesa:

| sal | sal < 0 | sal <= 500 | Saída |
| -- | -- | -- | -- |
| -5 | V | | "O valor precisa ser positivo."|
| 100 | F | V | "O seu novo salário vale: 120" |
| 1000 | F | F | "O seu novo salário vale: 1100" |

### Exercício 03

Represente, em fluxograma e pseudocódigo, um algoritmo para calcular a média aritmética entre duas notas de um aluno e mostrar sua situação, que poe ser aprovado ou reprovado.

#### Fluxograma:

```mermaid
flowchart TD
A([Inicio]) --> B{{Digite a primeira nota: }}
B --> C[\n1\]
C --> D{n1 >= 0}
D --FALSE--> E{{'O valor precisa ser positivo.'}} --> Z
D --TRUE--> F{{'Digite a segunda nota: '}}
F --> G[\n2\]
G --> H{n2 >= 0}
H --FALSE--> I{{'O valor precisa ser positivo.'}} --> Z
H --TRUE--> J[soma = n1 + n2]
J --> K{soma / 2 < 7}
K --FALSE--> L{{'Aprovado!'}}
K --TRUE--> M{{'Reprovado!'}} 

Z([Fim])
```

#### Pseudocódigo:

```
ALGORITMO aprovado_reprovado
DECLARE n1, n2, soma: FLOAT
INICIO
ESCREVA "Insira sua primeira nota: "
LEIA n1
SE n1 >= 0 ENTAO
  ESCREVA "Insira sua segunda nota: "
  LEIA n2
  SE n2 >= 0 ENTAO
    soma = n1 + n2
    SE soma / 2 < 7 ENTAO
      ESCREVA "Aprovado!"

    SENAO
      ESREVA "Reprovado!"
    FIM_SE
  SENAO
    ESCREVA "A segunda nota precisa ser maior ou igual a zero!"
  FIM_SE

SENAO
  ESCREVA "A primeira nota precisa ser maior o igual a zero!"
FIM_SE
FIM  
```

#### Teste de mesa:

| n1 | n1 > 0 | n2 | n2 > 0 | soma | soma / 2 < 7 | Saída |
| -- | -- | -- | -- | -- | -- | -- |
| -1 | F | | | | | "A primeira nota precisa ser maior ou igual a zero!"|
| 5 | V | -2 | F | | | "A segunda nota precisa ser maior ou igual a zero!"|
| 5 | V | 6 | V | 11 | 5.5 | "Reprovado!" |
| 10 | V | 10 | V | 20 | 10 | "Aprovado!" |

### Exercício 04
Represente, em fluxograma e pseudocódigo, um algoritmo que, a partir da idade da(o) candidata(o), determinar se pode ou não tirar a CNH. Caso não atender a restrição de idade, calcular quantos anos faltam para a(o) candidata(o) estar apta(o).

##### Fluxograma:

```mermaid
flowchart TD
A([Inicio]) --> B{{'Insira sua idade: '}}
B --> C[\idade\]
C --> D{idade < 0}
D --FALSE--> E{idade < 18}
E --FALSE--> F{{'Você já está apto para retirar sua CNH.'}} --> Z
E --TRUE--> G[faltam = 18 - idade]
G --> H{{'Faltam ', faltam ' anos para que você possa retirar sua CNH.'}} --> Z
D --TRUE--> I{{'A idade deve ser positiva!'}} --> Z
Z([Fim])
```

#### Pseudocódigo:

```
ALGORITMO Calcula_idade_CNH
DECLARE idade, faltam: INTEIRO
INICIO
ESCREVA "Insira sua idade: "
LEIA idade
SE idade < 0 ENTAO
  ESCREVA "A idade deve ser positiva!"

SENAO
  SE idade < 18 ENTAO
    faltam = 18 - idade
    ESCREVA "Faltam ", faltam, " anos para que você possa retirar sua CNH."
  SENAO
    ESCREVA "Você já está apto para retirar sua CNH."
  FIM_SE
FIM_SE
```

#### Teste de mesa:

| idade | idade < 0 | idade < 18 | faltam | Saída |
| --- | --- | --- | --- | --- |
| -5 | V | | | "A idade deve ser positiva" |
| 2 | F | V | 18 - 2 = 16 | "Faltam 16 anos para que você possa retirar sua CNH." |
| 18 | F | F | | "Você já está apto a retirar sua CNH."|




