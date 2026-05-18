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

O que vamos usar são esses possíveis modelos:

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

O **NPN** é o que usaremos como exemplo.

- N ➝ Negativo, pino Coletor (C)
- P ➝ Positivo, pino Base (B)
- N ➝ Negativo, pino Emissor (E)

## (6) Como o Transistor Funciona?

O transistor funciona como uma **chave eletrônica** ou **amplificador de corrente**.


### 🏷️ 1. Modo "Chave Liga/Desliga" (Saturação e Corte)
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

**Exemplo prático:**  

https://github.com/agodoi/m06ec-semana05/blob/main/assets/circuito_transistor_chave_esquematico.png


## (7) Onde o Conceito Aparece no Amplificador? [PRÓXIMA AULA]

No amplificador de áudio, os transistores BC548, BC558, TIP31 e TIP32 controlam o fluxo de corrente em diferentes regiões do circuito.

* Um pequeno sinal aplicado na Base (B) controla uma corrente maior entre Coletor (C) e Emissor (E);
* Sem corrente suficiente na Base, o transistor permanece em corte;
* Com corrente suficiente na Base, o transistor entra em saturação.

Esse mesmo princípio é utilizado em:

- acionamento de LEDs;
- controle de relés;
- buzzers;
- motores;
- módulos eletrônicos;
- estágios internos do amplificador de áudio.

## Prática (1)

### 🎯 Objetivo: acender um LED + Relé controlado por um transistor NPN (BC548).

### 🛠️ Componentes:
- **1 Transistor BC548**
- **1 Resistor de 1kΩ** (usar de divisor de tensão com o seu corpo)
- **1 LED**
- **1 Relé**
- **1 Resistor de 330Ω** (limita a corrente do LED)
- **1 Fonte de 12V** (pode ser uma pilha ou um Arduino)

### 🔧 Como Montar: siga exatamente o circuito da imagem

<img src="https://github.com/agodoi/m05-semana06/blob/main/imgs/pratica1v5.png" width="1000">


### 🔄 Funcionamento:
- Quando você tocar no nó que une pino (B) e R de 1MΩ e o **fio azul**, o seu corpo liberará uma pequena corrente na entrada da **Base**.
- O transistor **liga** e permite uma corrente maior fluir do **Coletor para o Emissor**.
- O **LED acende!**
- Quando você remove o seu dedo, desativa o sinal (0V), a corrente para e o LED **apaga**.
- **Caso o LED não acenda** com o seu toque, segure com a outra mão, **o POSITIVO do Arduino**.

## 📌 Resumo Final
✅ O transistor **controla** o fluxo de corrente.  
✅ Funciona como uma **chave eletrônica** ou **amplificador**.  
✅ Pequenas correntes na **Base** podem ativar **grandes correntes no Coletor**.  
✅ É essencial para **sensores, motores, amplificadores, LEDs e circuitos digitais**.

---

## Prática (2)

### (2.1) 🎯 Objetivo: usar o Monitor Plotter do Arduino IDE e observar o comportamento do BC548 como liga/desliga.

### (2.2) 🛠️ Materiais Necessários:
- 1 **Arduino Uno**
- 1 **Transistor BC548**
- 1 **Resistor de 1MΩ** (para a base do transistor)
- 1 **Resistor de 330Ω** (para limitar corrente do LED)
- 1 **LED**
- 1 **Potenciômetro de 1MΩ** (para controlar a corrente na Base)
- **Fios jumper**
- **Protoboard**

### (2.3) 🔧 Como Montar: siga exatamente o circuito da imagem

As medições você fará após a montagem. Por enquanto, concentre-se apenas nos componentes.

<img src="https://github.com/agodoi/m05-semana06/blob/main/imgs/pratica2v5.png" width="1000"> 

### (2.4) 🎛️ Como Funciona?
1. **O Potenciômetro** ajusta a corrente que entra na **Base do transistor**.
2. O **Arduino lê a tensão da Base** (pino A0).
3. O transistor controla a corrente no **Coletor → Emissor**, acendendo ou apagando o LED.
4. O **Monitor Plotter** exibe a relação entre a tensão na **Base** e no **Coletor**.
5. Conforme giramos o **potenciômetro**, podemos visualizar a **zona de corte**, **saturação** e o **modo linear** do transistor.

### (2.5) 💻 Código para o Arduino: copie e cole esse código no seu Arduino IDE e grave no Arduino Uno

```
#define BASE_PIN A0  // Pino do potenciômetro (Base do transistor)
#define COLETOR_PIN A1 // Pino conectado ao Coletor
#define LED_PIN 2  // Pino PWM para o LED (pode simular a corrente no coletor)

void setup() {
    Serial.begin(9600);
    pinMode(LED_PIN, OUTPUT);
}

void loop() {
    int baseVoltage = analogRead(BASE_PIN);  // Lê a tensão na Base
    int coletorVoltage = analogRead(COLETOR_PIN);  // Lê a tensão no Coletor

    // Converte para volts (Arduino opera de 0 a 5V com resolução de 1024 bits)
    float vBase = baseVoltage * (5.0 / 1023.0);
    float vColetor = coletorVoltage * (5.0 / 1023.0);

    // Controla o brilho do LED com a leitura da Base (simulando corrente no Coletor)
    analogWrite(LED_PIN, map(baseVoltage, 0, 1023, 0, 255));

    // Envia valores para o Monitor Plotter do Arduino
    Serial.print("Base: ");
    Serial.print(vBase);
    Serial.print("V  ");

    Serial.print("Coletor: ");
    Serial.print(vColetor);
    Serial.println("V");

    delay(100);
}
```

### (2.6) 📊 O que esperar no Monitor Plotter?
- Quando giramos o **potenciômetro**, vemos a tensão na **Base** aumentando ou diminuindo.
- A tensão no **Coletor** muda conforme a Base é polarizada.
- No **modo de corte** (Base ≈ 0V), o LED **fica apagado**.
- No **modo de saturação** (Base > 0.7V), o LED **acende totalmente**.
- No **modo ativo** (entre 0.2V e 0.7V), o LED **varia o brilho** proporcionalmente.




## Resumo:

**(a)** Transistor possui 3 pinos: Coletor (C), Base (B) e Emissor (E). 
**(b)** Existe 2 tipos de transistor: **NPN** e PNP.
**(c)** Todo transistor possui dois modos de trabalho: **Chave Liga-desliga** e Amplificador

---



### (2.7) 📌 Conclusão

Nesta aula prática, conseguimos visualizar no **Monitor Plotter** do Arduino como a tensão na **Base** afeta a corrente no **Coletor** do transistor. Isso nos permitiu demonstrar o funcionamento do **transistor BC548** como um **interruptor eletrônico** ou um **amplificador de sinal**.

✅ **Demonstração clara dos estados de operação do transistor!**  
✅ **Interatividade com controle de um LED!**  
✅ **Monitor Plotter ajuda a visualizar a relação entre Base e Coletor!**  

---

## (3) Ponderada - Relatório

Faça o download desse [RELATÓRIO AQUI](https://docs.google.com/document/d/1g1GO6JVUERXNDGacWIwJQ2FXL0V0NEEO7IFBBUc65ZY/edit?usp=sharing), faça o seu preenchimento. Quando tiver finalizado, trave-o em PDF, salve no seu Drive e compartilhe o link publicamente na Adalove até essa sexta-feira, dia 14/março às 23h59.
