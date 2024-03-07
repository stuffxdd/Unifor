# UNIFOR
**Disciplina:** Raciocínio lógico algorítmico <br>
**Orientador:** Prof. Ricardo Carubbi

## Lista 1 de exercícios:

### Exercício 1:

```mermaid
flowchart TD
A([Inicio]) --> B{{Insira  suas duas notas: }}
B --> C[/n1, n2/]
C --> D[soma = n1+n2]
D --> E[media = soma/2]
E --> F{media < 6}
F --FALSE--> G{{Você foi reprovado!}}
F --TRUE--> H{{Você foi aprovado!}}
G --> I([FIM])
H --> I
```

``` ALGORITMO media
DECLARE n1, n2, soma INTEIRO
DECLARE media FLOAT
ESCREVA "Insira suas duas notas: "
LEIA n1, n2
soma = n1 + n2
media = soma / 2
SE media < 6 ENTAO
	ESCREVA "Reprovado!"

SENAO
	Escreva "Aprovado!"

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

