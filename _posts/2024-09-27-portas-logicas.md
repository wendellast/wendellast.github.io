---
title: Portas Lógicas
date: 2024-09-27 15:33:00 -03:00
categories: [estudo, sistemas computacionais, porta lógica]
tags: [estudo, sistemas computacionais, portas lógicas, somador, binário, subtrator]
---

# Neste post, vamos aprender sobre as portas lógicas
## O que são portas lógicas?
As portas lógicas são componentes essenciais da eletrônica digital, responsáveis por realizar operações básicas sobre valores binários. Sua principal função é processar sinais de entrada e gerar uma saída com base em regras lógicas específicas, sendo fundamentais para o funcionamento de circuitos e sistemas digitais.

## Tipos de Portas Lógicas
Existem várias portas lógicas, cada uma com uma função específica. Aqui estão algumas das mais usadas:
- [**Porta NOT (Não)**](#porta-not-não)
- [**Porta AND (E)**](#porta-and-e)
- [**Porta OR (Ou)**](#porta-or-ou)
- [**Porta XOR (Ou Diferente)**](#porta-xor-ou-diferente)
- [**Porta NAND (Não E)**](#porta-nand-não-e)
- [**Porta NOR (Não Ou)**](#porta-nor-não-ou)

### Porta NOT (Não)
A porta NOT, também conhecida como inverter, é uma porta lógica que inverte o valor de entrada. Se a entrada for 0, a saída será 1, e vice-versa.

- **Fórmula:** `A'`
- **Tabela de Verdade:**

| Entrada | Saída |
|---------|-------|
|   1     |   0   |
|   0     |   1   |

- **Representação**
<br/>
<img alt="not" src="/assets/img/2024-09-27-portas-logicas/notGate.png" />

### Porta AND (E)
A porta AND, ou porta lógica E, é uma porta que produz 1 apenas se todas as entradas forem 1.

- **Fórmula:** `A * B`
- **Tabela de Verdade:**

| Entrada A | Entrada B | Saída |
|-----------|-----------|-------|
|     1     |     1     |   1   |
|     1     |     0     |   0   |
|     0     |     1     |   0   |
|     0     |     0     |   0   |

- **Representação**
<br/>
<img alt='and' src="/assets/img/2024-09-27-portas-logicas/andGate.png" />

### Porta OR (Ou)
A porta OR, ou porta lógica OU, é uma porta que produz 1 se pelo menos uma das entradas for 1.

- **Fórmula:** `A + B`
- **Tabela de Verdade:**

| Entrada A | Entrada B | Saída |
|-----------|-----------|-------|
|     1     |     1     |   1   |
|     1     |     0     |   1   |
|     0     |     1     |   1   |
|     0     |     0     |   0   |

- **Representação**
<br/>
<img alt='or' src="/assets/img/2024-09-27-portas-logicas/orGate.png" />

### Porta XOR (Ou Diferente)
A porta XOR, ou porta lógica OU Diferente, é uma porta que produz
1 apenas se uma das entradas for 1 e a outra for 0, ela e composta por duas
portas nao and e uma porta ou.

- **Fórmula:** `(A * B') + (A' * B) ou A ⊕ B`
- **Tabela de Verdade:**

| Entrada A | Entrada B | Saída |
|-----------|-----------|-------|
|     1     |     1     |   0   |
|     1     |     0     |   1   |
|     0     |     1     |   1   |
|     0     |     0     |   0   |

- **Representação**
<br/>
<img alt='xor' src="/assets/img/2024-09-27-portas-logicas/xorGate.png" />

### Porta NAND (Não E)
A porta NAND é uma combinação da porta AND seguida de uma porta NOT. Ela produz 0 apenas se todas as entradas forem 1.

- **Fórmula:** `A * B'`
- **Tabela de Verdade:**

| Entrada A | Entrada B | Saída |
|-----------|-----------|-------|
|     1     |     1     |   0   |
|     1     |     0     |   1   |
|     0     |     1     |   1   |
|     0     |     0     |   1   |

- **Representação**
<br/>
<img alt='nand' src="/assets/img/2024-09-27-portas-logicas/nandGate.png" />


### Porta NOR (Não Ou)
A porta NOR é uma combinação da porta OR seguida de uma porta NOT. Ela produz 1 apenas se todas as entradas forem 0.

- **Fórmula:** `A + B'`
- **Tabela de Verdade:**

| Entrada A | Entrada B | Saída |
|-----------|-----------|-------|
|     1     |     1     |   0   |
|     1     |     0     |   0   |
|     0     |     1     |   0   |
|     0     |     0     |   1   |

- **Representação**
<br/>
<img alt='nor' src="/assets/img/2024-09-27-portas-logicas/norGate.png" />

<hr/>
## Diagrama
Caso queira um diagrama com todas as portas lógicas, baixe este arquivo que é um Canva do Obsidian.

<a href="{{ '/assets/img/2024-09-27-portas-logicas/LogicalGates.canvas' |
relative_url }}" download>
  Baixar Canva
</a>
