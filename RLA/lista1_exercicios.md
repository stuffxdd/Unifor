# UNIFOR
**Disciplina:** Raciocínio lógico algorítmico <br>
**Orientador:** Prof. Ricardo Carubbi

## Lista 1 de exercícios:

### Exercício 1:

Represente, em fluxograma e pseudocódigo, um algoritmo para calcular a média aritmética entre duas notas de um aluno e mostrar sua situação, que pode ser aprovado ou reprovado;

##### Fluxograma:

```mermaid
flowchart TD
A([Inicio]) --> B{{Insira  suas duas notas: }}
B --> C[/n1, n2/]
C --> D{n1 >= 0}
D --FALSE--> E{{O primeiro valor precisa ser positivo.}}
E --> M
D --TRUE--> F{n2>=0}
F --FALSE--> G{{O segundo valor precisa ser positivo.}}
G --> M
F --TRUE--> H[soma = n1 + n2]
H --> I[media = soma/2]
I --> J{media < 6}
J --FALSE--> K{{Você foi aprovado.}}
J --TRUE--> L{{Você foi reprovado.}}
L --> M([FIM])
K --> M
```
##### Pseudocódigo:

```
ALGORITMO media
DECLARE n1, n2, soma, media INTEIRO
ESCREVA "Insira suas duas notas: "
LEIA n1, n2
SE n1 >= 0 ENTAO
	SE n2 >= 0 ENTAO
		soma = n1 + n2
		media = soma / 2
		SE media < 6 ENTAO
			ESCREVA "Reprovado!"
		SENAO
			ESCREVA "Aprovado!"
	SENAO
		ESCREVA "O segundo número precisa ser positivo!"
SENAO
	ESCREVA "O primeiro número precisa ser positivo!"

FIM
```

### Exercício 2:

Represente, em fluxograma e pseudocódigo, um algoritmo para calcular o novo salário de um funcionário. Sabe-se que os funcionários que recebem atualmente salário de até R$ 500 terão aumento de 20%; os demais terão aumento de 10%.

##### Fluxograma:

```mermaid
flowchart TD
A([Inicio]) --> B{{Insira o valor de seu salário: }}
B --> C[/sal_atual/]
C --> D{0 < sal_atual}
D --FALSE--> E{{O salário inserido precisa ser positivo!}}
E --> K
D --TRUE--> F{sal_atual >=500}
F --FALSE--> G[sal_novo = sal_atual * 1,2]
G --> H{{Seu novo salário vale sal_novo}}
H --> K
F --TRUE--> I[sal_novo = sal_atual * 1,1]
I --> J{{Seu novo salário vale sal_novo}}
J --> K([FIM])

```

##### Pseudocódigo:

```
ALGORITMO aumento_salarial
DECLARE sal_atual, sal_novo FLOAT
ESCREVA "Insira o valor de seu salário: "
LEIA sal_atual
SE sal_atual > 0 ENTAO
	SE sal_atual >= 500 ENTAO
		sal_novo = sal_atual * 1,1
		ESCREVA "Seu novo salário vale: {sal_novo}!"
	SENAO
		sal_novo = sal_atual * 1,2
		ESCREVA "Seu novo salário vale: {sal_novo}!"
SENAO
	ESCREVA "O salário inserido precisa ser positivo!"

FIM
```

### Exercício 3:

Represente, em fluxograma e pseudocódigo, um algoritmo para determinar se um número **inteiro** e **positivo** é par ou impar.

##### Fluxograma:

```mermaid
flowchart TD
A([INICIO]) --> B{{Insira um numero inteiro e positivo: }}
B --> C[/n1/] 
C --> D{n1 > 0}
D --FALSE--> E{{O numero deve ser positivo!}}
E --> J
D --TRUE--> F[resto = n1 % 2]
F --> G{resto == 0}
G --FALSE--> H{{O numero inserido é impar!}}
G --TRUE--> I{{O numero inserido é par!}}
H --> J([FIM])
I --> J
```

##### Pseudocódigo:

```
ALGORITMO verifica_par_impar
DECLARE n1, resto INTEIRO
ESCREVA "Insira um numero inteiro positivo: "
LEIA n1
SE n1 > 0 ENTAO
	resto = n1 % 2
	SE resto == 0 ENTAO
		ESCREVA "O número é par!"
	SENAO
		ESCREVA "O número é impar!"
SENAO
	ESCREVA "O número deve ser positivo!"

FIM
```

### Exercício 4:

Represente, em fluxograma e pseudocódigo, um algoritmo que, a partir da idade do candidato(a), determinar se pode ou não tirar a CNH. Caso não atender a restrição de idade, calcular quantos anos faltam para o candidato estar apto.

#### Fluxograma:

```mermaid
flowchart TD
A([Inicio]) --> B{{Escreva sua idade: }}
B --> C[/idade/]
C --> D{idade > 0}
D --FALSE--> E{{O valor da idade precisa ser positivo!}}
E --> I
D --TRUE--> F{idade>=18}
F --FALSE--> G{{Você ainda não pode tirar sua CNH.}}
G --> I
F --TRUE--> H{{Você pode tirar sua CNH.}}
H --> I([FIM])
```

##### Pseudocódigo:

```
ALGORITMO CNH
DECLARE idade
ESCREVA "Digite sua idade: "
LEIA idade
SE idade > 0 ENTAO
	SE idade >= 18 ENTAO
		ESCREVA "Você está pode tirar sua CNH."
	SENAO
		ESCREVA "Você não pode tirar sua CNH."
SENAO
	ESCREVA "O valor da idade precisa ser positivo!"

FIM
```
