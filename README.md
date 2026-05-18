# Atendimento do Professor

## Terças e quintas. Professor de horário parcial. Nesses 2 dias, podem contar comigo!

# Semama 05 - Transistor Como Chave e Conceito Inicial

## (1) Relação com o Projeto do Amplificador de Áudio

Antes de estudarmos o transistor isoladamente, observe que o projeto do amplificador de áudio utiliza 4 transistores para controlar o fluxo de corrente no circuito.

Neste momento da disciplina, vamos focar apenas no comportamento do transistor como chave eletrônica, isto é:

* Transistor em corte → equivalente a uma chave aberta (desligado);
* Transistor em saturação → equivalente a uma chave fechada (ligado).

O objetivo desta aula não será estudar ganho ou amplificação analógica de áudio, mas sim entender como um pequeno sinal elétrico pode ligar ou desligar cargas maiores.

## (3) O que é um Transistor?

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

## (4) Onde buscar Informações?


* Sempre nos manuais dos fabricantes.
* [Datasheet](https://www.alldatasheet.com/)


### (5) Estrutura Básica

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

## (6) Como o Transistor Funciona?

O transistor funciona como uma **chave eletrônica** ou **amplificador de corrente**.


### (6.1) Modo "Chave Liga/Desliga" (Saturação e Corte)
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


### (6.2) Onde o Conceito Aparece no Amplificador? [PRÓXIMA AULA]

No amplificador de áudio, os transistores BC548, BC558, TIP31 e TIP32 controlam o fluxo de corrente em diferentes regiões do circuito.

* Um pequeno sinal aplicado na Base (B) controla uma corrente maior entre Coletor (C) e Emissor (E);
* Sem corrente suficiente na Base, o transistor permanece em corte;
* Com corrente suficiente na Base, o transistor entra em saturação.

## (7) Prática

### 🎯 Objetivo: acender um LED + Relé controlado por um transistor NPN (BC548).

### 🛠️ Componentes:
- **1 Transistor BC548**
- **1 Resistor de 1kΩ** (usar de divisor de tensão com o seu corpo)
- **1 LED**
- **1 Relé**
- **1 Resistor de 330Ω** (limita a corrente do LED)
- **1 Fonte de 12V** (pode ser uma pilha ou um Arduino)

### 🔧 (7.1) Monte o Circuito no Tinkercad

<img src="https://github.com/agodoi/m06ec-semana05/blob/main/assets/circuito_transistor_chave_esquematico.png" width="300">

<img src="https://github.com/agodoi/m06ec-semana05/blob/main/assets/circuito%20transistor%20chave.png" width="700">


### 🔄 (7.2) Responda este [relatório](https://docs.google.com/document/d/1MhNQvE0AqLZDRvCRriLvltmjjLheclWTTmsVgltsQO0/edit?usp=sharing)

#### 🛠️ (A) Com o push bottom solto, tome nota num bloco de notas:

- A corrente na base I_B.
- A corrente no coletor I_C.
- A corrente no emissor I_E.
- A tensão V_BC.
- A tensão V_CE.
- A tensão V_BE.

* Lembrando que: **medir corrente, multímetro em série**, **medir tensão, multímetro em paralelo**.

#### 🛠️ (B) Com o push bottom pressionado, tome nota num bloco de notas:

- A corrente na base I_B.
- A corrente no coletor I_C.
- A corrente no emissor I_E.
- A tensão V_BC.
- A tensão V_CE.
- A tensão V_BE.

#### 🔎 (C) Análise do circuito com o push button SOLTO

- O LED permaneceu aceso ou apagado? O que isso indica sobre o estado do transistor?
- A corrente na Base foi alta, baixa ou praticamente nula? O que isso significa?
- Existe corrente significativa circulando entre Coletor e Emissor quando a Base não recebe corrente?
- Comparando I_B, I_C, e I_E, o que acontece com todas as correntes quando o transistor entra em corte?
- A tensão V_CE ficou mais próxima de 0V ou de 12V? O que isso revela sobre o transistor?
- A tensão V_BE ficou abaixo ou acima de aproximadamente 0,7V?
- Podemos afirmar que o transistor se comporta como uma chave aberta nesta condição?

#### 🔎 (D) Análise do circuito com o push button PRESSIONADO

- O que aconteceu com o LED quando a Base recebeu corrente?
- A corrente no Coletor aumentou mesmo com uma corrente pequena na Base?
- Compare os valores de I_B e I_C. O transistor permitiu controlar uma corrente maior usando uma corrente menor?
- O valor de V_BE aproximou-se de 0,7V quando o transistor conduziu?
- A tensão V_CE diminuiu quando o transistor saturou? O que isso indica?
- O transistor passou a se comportar mais como:
-     uma chave aberta
-     ou uma chave fechada?
- O LED acendeu porque a corrente conseguiu circular entre quais terminais do transistor?



### (8) 📌 Conclusão

Nesta aula prática, conseguimos visualizar como a tensão na **Base** afeta a corrente no **Coletor** do transistor. Isso nos permitiu demonstrar o funcionamento do **transistor BC548** como um **interruptor eletrônico**.

✅ **Demonstração clara de 2 estados de operação do transistor!**  
✅ **Interatividade com controle de um LED e relé!**  
