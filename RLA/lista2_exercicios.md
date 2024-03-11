# Unifor

### Exerício 1:
Calcule a média de quatro números inteiros dados.

##### Fluxograma:

```mermaid
flowchart TD
A([Inicio]) --> B{{'Insira 4 números inteiros: '}}
B --> C[/n1, n2, n3, n4/]

C --> D{n1 % 2 == 1 or n1 % 2 == 0 and n2 % 2 == 0 or n2 % 2 == 1 and n3 % 2 == 0 or n3 % 2 == 1 and n4 % 2 == 0 or n4 % 2 == 1}
D --FALSE--> E{{'Todos os números precisam ser inteiros!'}} --> Z
D --TRUE--> F[soma = n1 + n2 + n3 + n4]
F --> G[media = soma/4]
G --> H{{'O valor da média dos 4 números inteiros são: ', media}} --> Z

Z([FIM])
```

##### Pseudocódigo:

```
ALGORITMO Media_4_notas
ESCREVA "Insira 4 números inteiros: "
DECLARE n1, n2, n3, n4: inteiro

INICIO
  LEIA n1, n2, n3, n4
  SE n1 % 2 == 1 or n1 % 2 == 0 and n2 % 2 == 0 or n2 % 2 == 1 and n3 % 2 == 0 or n3 % 2 == 1 and n4 % 2 == 0 or n4 % 2 == 1 ENTAO
    soma = n1+n2+n3+n4
    media = soma / 4
    ESCREVA "A sua média vale", media
  SENAO
    ESCREVA "Todos os números precisam ser inteiros!"
  FIM_SE
FIM
```

### Exercício 2:
Leia uma temperatura dada na escala Celsius (C) e imprima o equivalente em Fahrenheit (F). (Fórmula de conversão: F = (9/5) * C + 32)

#### Fluxograma:

```mermaid
flowchart TD
A([Inicio]) --> B{{'Digite um valor de temperatura na escala Celsius: '}}
B --> C[/temp/]

C --> D{temp < -275.15}
D --False--> E[fah = temp*9/5 + 32]
E --> F{{'O valor da temperatura em Fahrenheit vale: ', temp}} --> Z

D --TRUE--> H{{'A tempetura não pode ser menor -275.15: o zero absoluto!'}} --> Z

Z([FIM])


```

### Exercício 3:

Leia uma quantidade de chuva dada em polegadas e imprima o equivalente em milímetros (25,4 mm = 1 polegada).

#### Fluxograma:

```mermaid
flowchart TD

A([Inicio]) --> B{{'Insira um valor de volume em polegadas: '}}
B --> C[/volume_pol/]

C --> D{volume_pol < 0}
D --FALSE--> E[volume_mili = 25,4 * volume_pol]
E --> F{{'O volume de ', volume_pol, ' em militros vale: ', volume_mili}} --> Z

D --TRUE--> G{{'O valor inserido precisa ser positivo!}} --> Z

Z([Fim])
```

#### Exercício 4:

O custo ao consumidor de um carro novo é a soma do custo de fábrica com a porcentagem do distribuidor e dos impostos, ambos aplicados ao custo de fábrica. Supondo que a porcentagem do distribuidor seja de 12% e a dos impostos de 45%, prepare um algoritmo para ler o custo de fábrica do carro e imprimir o custo ao consumidor.

```mermaid
flowchart TD

A([Inicio]) --> B{{'Insira o valor de um carro no preço de fábrica: '}}
B --> C[/custoF/]
C --> D{custoF < 0}
D --FALSE--> E[custoC = custoF * 1.57]
E --> F{{'O valor para o consumidor sairá por: ', custoC}} --> Z

D --TRUE--> G{{O valor do carro não pode ser negativo!}} --> Z
Z([Fim])
```

### Exercício 5:
Calcule o quadrado de um número.

#### Fluxograma:

```mermaid
flowchart TD

A([Inicio]) --> B{{'Insira um valor: '}}
B --> C[/n1/]
C --> D[quadrado = n1**2]
D --> E{{'O valor do quadrado do número inserido vale: ', quadrado}}
E --> Z

Z([Fim])
```

### Exercício 6:
O cardápio de uma lanchonete é dado abaixo. Prepare um algoritmo que leia a quantidade de cada item que você consumiu e calcule a conta final.
a) Hambúrguer................ R$ 3,00
b) Cheeseburger.............. R$ 2,50
c) Fritas.................... R$ 2,50
d) Refrigerante ............. R$ 1,00
e) Milkshake................. R$ 3,00

#### Fluxograma:


### Exercício 20:

Receba dois números reais e um operador (vide slide 9). e efetue a operação correspondente com os valores recebidos (operandos). O algoritmo deve retornar o resultado da operação selecionada simulando todas as opeações de uma calculadora simples.

##### Fluxograma:

```mermaid
flowchart TD
A([Inicio]) --> B{{'Insira dois valores e um número correspondente a um operador: '}}
B --> BB{{'Operadores válidos são: 1 - soma, 2 - subtração, 3 - multiplicação, 4 - divisão, 5 - divisão inteira, 6 - potenciação, 7 - raiz quadrada, 8 - raiz cúbica'}}
BB--> C[/n1, n2, op/]

C --> D{op != '1'}
D -- FALSE--> E[soma = n1+n2]
E --> F{{'A soma vale: ', soma}} --> ZZ

D --TRUE--> G{op != '2'}
G --FALSE--> H[sub = n1 - n2]
H --> I{{'A subtração vale: ', sub}} --> ZZ

G --TRUE--> J{op != '3'}
J --FALSE--> K[mult = n1 * n2]
K --> L{{'A multiplicação vale: ', mult}} --> ZZ

J --TRUE--> M{op != '4'}
M --FALSE--> N[div = n1 / n2]
N --> O{{'A divisão vale: ', div}} --> ZZ

M --TRUE--> P{op != '5'}
P --FALSE--> Q[div_int = n1 // n2]
Q --> R{{'A divisão inteira entre os números vale: ', div_int}} --> ZZ

P --TRUE--> S{op != '6'}
S --FALSE--> T[pot = n1 ** n2]
T --> U{{'O primeiro valor elevado ao segundo valor vale: ', pot}} --> ZZ

S--TRUE--> V{op != '7'}
V --FALSE--> W[raiz = n1 ** 1/n2]
W --> X{{'A raiz do primeiro número com o segundo número vale: ', raiz}} --> ZZ

V--TRUE--> Z{{'Digite um operador válido!'}} --> ZZ

ZZ([FIM])

```

