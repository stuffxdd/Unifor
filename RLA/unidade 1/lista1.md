# Unifor:

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
C --> D{numero >= 0}
D --FALSE--> E{{O número deve ser positivo.}} --> Z
D --TRUE--> F{numero % 2 == 0}
F --FALSE--> G{{O número é ímpar.}} --> Z
F--TRUE--> H{{O número é par.}} --> Z

Z([Fim])

```
#### Pseudocódigo:

```
ALGORITMO verif_par_impar
DECLARE numero: INTEIRO
ESCREVA "Digite um número: "
INICIO
LEIA numero

SE numero == 0 ENTAO
  ESCREVA "O número deve ser positivo. O número zero não é positivo e nem negativo; é elemento neutro aditivo."


SE numero > 0 ENTAO
  SE numero % 2 == 0 ENTAO
    ESCREVA "O número é par."
  SENAO
    ESCREVA "O número é ímpar."
  FIM_SE

SENAO
  ESCREVA "O número precisa ser positivo."

FIM_SE
FIM

```

#### Teste de mesa:
| numero | numero == 0 |numero > 0 | numero % 2 == 0 | Saída |
| -- | ---  | -- | -- | ----  |
| -1 | F | F |  |"O número deve ser positivo." |
| 0  | V | F |  | "O número deve ser positivo. O 0 é elemento neutro aditivo." |
| 15 | F | V | F | "O número é ímpar." |
| 16 | F | V | V | "O número é par." |

