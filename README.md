# Atendimento do Professor

## Terças e quintas. Professor de horário parcial. Nesses 2 dias, podem contar comigo!

# Semama 05 - Transistor Como Chave e Conceito Inicial

## (1) Relação com o Projeto do Amplificador de Áudio

Antes de estudarmos o transistor isoladamente, observe que o projeto do amplificador de áudio utiliza 4 transistores para controlar o fluxo de corrente no circuito.

Neste momento da disciplina, vamos focar apenas no comportamento do transistor como chave eletrônica, isto é:

* Transistor em corte → equivalente a uma chave aberta (desligado);
* Transistor em saturação → equivalente a uma chave fechada (ligado).

O objetivo desta aula não será estudar ganho ou amplificação analógica de áudio, mas sim entender como um pequeno sinal elétrico pode ligar ou desligar cargas maiores.

## (2) O que é um Transistor?

O transistor é um componente eletrônico semicondutor usado para controlar corrente elétrica.

Ele está presente em praticamente todos os equipamentos eletrônicos.

Os modelos que aparecem no projeto do amplificador são:

* BC548 = NPN
* BC558 = PNP
* TIP30 = PNP
* TIP31 = NPN

O **transistor** é um **componente eletrônico semicondutor** usado para amplificar ou chavear sinais elétricos. 
Ele é fundamental na eletrônica moderna e está presente em 99% todos os circuitos eletrônicos.

<img src="https://github.com/agodoi/m05-semana06/blob/main/imgs/transistor.jpeg" width="600">

O que vamos usar são esses modelos:

<img src="https://github.com/agodoi/m05-semana06/blob/main/imgs/transistor-bc548.jpg" width="300">

<img src="https://github.com/agodoi/m05-semana06/blob/main/imgs/transistor-tip41.png" width="300">


**Microcontroladores não são capazes de ativar cargas elétricas, como relés, motores, lâmpadas, bobinas. Usamos o transitor no caminho para atuar como um driver de corrente.**

## (3) Onde buscar Informações?


* Sempre nos manuais dos fabricantes.
* [Datasheet](https://www.alldatasheet.com/)


## (4) Estrutura Básica

Um transistor bipolar (como o **BC548** e o **TIP41C**) possui **três terminais**:

- I)   **Base (B):** Controla o fluxo de corrente entre C e E.
- II)  **Coletor (C):** Entrada principal de corrente.
- III) **Emissor (E):** Saída da corrente.

👉 Existem dois tipos principais de transistores bipolares:
- **NPN** (mais comum).
- **PNP**

<img src="https://github.com/agodoi/m06ec-semana05/blob/main/assets/pnp_npn.png" width="400">

O **NPN** é o que usaremos como exemplo.

- N ➝ Negativo, pino Coletor (C)
- P ➝ Positivo, pino Base (B)
- N ➝ Negativo, pino Emissor (E)

## (5) Como o Transistor Funciona?

O transistor funciona como uma **chave eletrônica** ou **amplificador de corrente**.


### (5.1) Modo "Chave Liga/Desliga" (Saturação e Corte)
- Se **nenhuma corrente** fluir para a **Base (B)** ➝ O transistor fica **desligado** (isto é, **corte**).
- Se **uma pequena corrente em [mA]** fluir para a **Base (B)** ➝ O transistor liga e permite uma **corrente maior em [A]** entre **Coletor (C) e Emissor (E)** (isto é, **saturação**).

**Exemplo prático:**  
Imagine um botão pressão que ativa um motor.
- Quando o botão está solto (**Base sem corrente**), o motor está desligado.
- Quando o botão é pressionado (**Base recebe corrente**), o motor liga.

Onde:
- ( I_C ) = corrente no **Coletor**
- ( I_B ) = corrente na **Base**
- ( β ) (ou "ganho") = fator de amplificação do transistor. Todo modelo de transistor tem um β exclusivo. O β indica o quanto sensível ele é para liberar o fluxo de corrente entre C e E a partir de uma excitação de B. Valores típicos: 100 < β < 600. Precisa entrar no datasheet para saber o valore exato do seu transistor.

**Exemplo prático de hoje:**  

https://github.com/agodoi/m06ec-semana05/blob/main/assets/circuito_transistor_chave_esquematico.png


### (5.2) Onde o Conceito Aparece no Amplificador? [PRÓXIMA AULA]

No amplificador de áudio, os transistores BC548, BC558, TIP31 e TIP32 controlam o fluxo de corrente em diferentes regiões do circuito.

* Um pequeno sinal aplicado na Base (B) controla uma corrente maior entre Coletor (C) e Emissor (E);
* Sem corrente suficiente na Base, o transistor permanece em corte;
* Com corrente suficiente na Base, o transistor entra em saturação.

## (6) Prática

### 🎯 Objetivo: acender um LED + Relé controlado por um transistor NPN (BC548).

### 🛠️ Componentes:
- **1 Transistor BC548**
- **1 Resistor de 1kΩ** (usar de divisor de tensão com o seu corpo)
- **1 LED**
- **1 Relé**
- **1 Resistor de 330Ω** (limita a corrente do LED)
- **1 Fonte de 12V** (pode ser uma pilha ou um Arduino)

### 🔧 (6.1) Monte o Circuito no [Tinkercad](https://tinkercad.com/)

<img src="https://github.com/agodoi/m06ec-semana05/blob/main/assets/circuito_transistor_chave_esquematico.png" width="300">

### 🔄 (6.2) Responda este [relatório](https://docs.google.com/document/d/1MhNQvE0AqLZDRvCRriLvltmjjLheclWTTmsVgltsQO0/edit?usp=sharing)


### (7) 📌 Conclusão

Nesta aula prática, conseguimos visualizar como a tensão na **Base** afeta a corrente no **Coletor** do transistor. Isso nos permitiu demonstrar o funcionamento do **transistor BC548** como um **interruptor eletrônico**.

✅ **Demonstração clara de 2 estados de operação do transistor!**  
✅ **Interatividade com controle de um LED e relé!**  
