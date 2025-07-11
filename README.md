# ComedouroPet
O projeto visa desenvolver um sistema de automação de alimentação para animais domésticos utilizando um controlador **ATmega328** com linguagem **C**. O acesso aos pinos será realizado diretamente por meio de **registradores**, garantindo maior controle sobre as operações do microcontrolador.

Com base nos requisitos estabelecidos, o sistema será simulado no ambiente **Tinkercad**, permitindo a observação do funcionamento. A abordagem busca compreender a interação entre **sensores**, **atuadores** e **registradores**, analisando seu comportamento e eficiência na automação da alimentação.

Além disso, o projeto explora conceitos como:

- Conversão **A/D**
- Uso de **interrupções**
- Controle por **PWM**
- Interface com o **usuário**

Com isso, pretende-se oferecer uma solução prática e eficiente para os **tutores** e promover o **bem-estar dos animais**.

## 1. INTRODUÇÃO

Com o avanço da tecnologia e sua crescente integração à internet e aos objetos do nosso cotidiano, torna-se cada vez mais difícil imaginar um mundo sem soluções inteligentes. Nesse cenário, os sistemas embarcados têm desempenhado um papel fundamental ao viabilizar automações e mecanismos que executam tarefas do dia a dia com maior eficiência. Pensando nisso, este relatório apresenta o desenvolvimento de uma solução aplicada a um sistema embarcado voltado para o controle automatizado da alimentação de animais domésticos. A implementação foi realizada na plataforma Tinkercad, utilizando o microcontrolador ATmega328.

O projeto foi concebido para oferecer uma solução prática tanto automatizada quanto manual, voltada a tutores que nem sempre conseguem dedicar a atenção necessária aos seus pets. O sistema conta com um mecanismo de liberação de ração controlado por tempo e ângulo, além de realizar a supervisão contínua do nível de alimento disponível. Para isso, foram integrados sensores analógicos e digitais, atuadores com controle PWM e uma interface de interação com o usuário por meio de um display LCD. A robustez da aplicação é garantida por uma máquina de estados bem estruturada e pelo uso de interrupções via Timer1, assegurando monitoramento periódico e resposta imediata a situações críticas.

A programação do sistema foi desenvolvida em linguagem C pura pensando na programação do arduino Uno, ele teve acesso direto aos registradores do microcontrolador, o que permitiu um maior controle sobre os periféricos e a lógica de operação. Além disso, neste relatório, iremos detalhar os requisitos técnicos, a escolha dos componentes, a estrutura de funcionamento e os resultados obtidos com a simulação do sistema.

## 2. DESENVOLVIMENTO

### 2.1 Requisitos Técnicos

- Sensores: 
2 sensores analógicos com conversão A/D (potenciômetros); 
2 sensores digitais (interruptor e botão) Atuadores: 1 atuador digital (LED); 
1 atuador PWM (servo motor simulado).

- Interface com usuário: Display LCD (16x2 via I2C);
sinal sonoro ou visual (LEDs).

- Outros requisitos: Uso obrigatório de interrupção (Timer1) Código escrito em C puro. Implementação no Tinkercad com manipulação de registradores.

Para a realização do trabalho e atendimento aos requisitos previamente estabelecidos, foi montado um protótipo funcional do comedouro automático para pets. O sistema foi estruturado com base em componentes essenciais, cada um responsável por desempenhar funções específicas dentro da lógica de controle automatizado e seguro da liberação de ração, com verificação periódica do nível de alimento e sinalização de alertas em casos críticos.

A tabela a seguir apresenta os principais componentes utilizados no projeto, acompanhados de suas respectivas quantidades e observações sobre sua aplicação no sistema:

<div align="center">
Tabela 01 - Componentes do circuito

| Componentes                        | Quantidade | Observações                           |
|-----------------------------------|------------|----------------------------------------|
| Arduino Uno R3                    | 1          | Microcontrolador principal             |
| Potenciômetros                    | 3          | Controle de tempo, ângulo e nível      |
| Interruptor deslizante            | 1          | Modo ON/OFF                            |
| Botão                             | 1          | Ação manual do sistema                 |
| Resistores diversos               | 5          | 220Ω, 100Ω, 10kΩ                        |
| LEDs (vermelho, verde e laranja) | 2          | Indicação visual de estado             |
| Osciloscópio virtual              | 1          | Para verificação de sinal PWM          |
| Display LCD (I2C 0x27)            | 1          | Interface de exibição de informações   |

**Fonte:** Elaborada pelos autores.
</div>

### 2.2 Montagem do circuito

A figura abaixo ilustra a montagem física do circuito no simulador Tinkercad, utilizando a placa Arduino Uno R3 como núcleo de controle. O sistema foi desenvolvido para atender aos requisitos de automação de um comedouro para animais de estimação, integrando sensores, atuadores e interface de usuário.

<div align="center">
**Figura 01** - Montagem do circuito no simulador Tinkercad
![Montagem](ComedouroPet/imagem1.png)
**Fonte:** www.tinkercad.com
</div>
