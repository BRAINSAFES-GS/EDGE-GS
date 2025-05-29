# EDGE-GS


 ## Descrição do Problema

---

- Inundações e transbordamentos em reservatórios, caixas d’água e cisternas podem causar sérios problemas, tanto em ambientes domésticos quanto industriais. Monitorar o nível da água de forma contínua é fundamental para garantir segurança, evitar desperdícios, e permitir ações preventivas rápidas.
-  Este projeto visa criar um Sistema de Monitoramento de Nível de Água, capaz de:
- Detectar o nível de água utilizando um sensor ultrassônico (HC-SR04);
- Exibir informações em tempo real em um display LCD I2C;
- Indicar visualmente o nível por meio de LEDs de diferentes cores;
- Emitir alertas sonoros com um buzzer quando o nível estiver alto ou crítico;
- Registrar os dados historicamente na EEPROM para posterior análise.

---


 #  Projeto de Monitoramento de Nível de Água com Arduino

##  Componentes Utilizados:
- Arduino Uno
- Sensor Ultrassônico HC-SR04
- Display LCD 16x2 com módulo I2C
- 4 LEDs (Verde, Amarelo, Vermelho, Roxo)
- Buzzer Piezoelétrico
- Resistores para LEDs (220Ω ou 330Ω)
- Protoboard
- Jumpers

---

##  Esquema de Conexões

###  Display LCD I2C
| Pino LCD I2C | Arduino |
|----------------|---------|
| VCC            | 5V      |
| GND            | GND     |
| SDA            | A4      |
| SCL            | A5      |

---

###  Sensor Ultrassônico HC-SR04
| Pino HC-SR04 | Arduino |
|---------------|---------|
| VCC           | 5V      |
| GND           | GND     |
| TRIG          | D8      |
| ECHO          | D9      |

---

###  LEDs Indicadores
| Cor     | Pino Arduino | Observação                |
|---------|---------------|---------------------------|
| Verde   | D2            | Nível Seguro              |
| Amarelo | D3            | Nível de Atenção          |
| Vermelho| D4            | Nível Alto (com buzzer)   |
| Roxo    | D5            | Nível Crítico (com buzzer)|

 Todos os LEDs possuem resistores conectados no terminal negativo (catodo), que vão para o GND.

---

###  Buzzer
| Terminal | Arduino |
|-----------|---------|
| +         | D6      |
| -         | GND     |

---

###  Alimentação Geral
- **5V do Arduino** → linha positiva da protoboard (vermelha).
- **GND do Arduino** → linha negativa da protoboard (azul ou preta).

---

##  Tabela de Funcionamento dos Níveis

| Distância (cm) | LED Ativo | Ação no Buzzer | Estado no LCD                      |
|-----------------|-----------|----------------|-------------------------------------|
| ≥ 100           | Verde     | Off            | "Nível de Água: Bom"               |
| 100 ~ 60        | Amarelo   | Off            | "Nível de Água: Alerta!"           |
| 60 ~ 30         | Vermelho  | Beep           | "Nível de Água: Alto! Abaixar!"    |
| ≤ 30            | Roxo      | Beep Contínuo  | "Nível de Água: CRITICO!"          |

---

##  Esquema do Circuito

---

![Captura de Tela (60)](https://github.com/user-attachments/assets/7610a037-aed4-4bee-823f-fdab728f90de)



##  Guia para Simular o Projeto

---

 Simule no Wokwi:
Acesse este link: https://wokwi.com/projects/432250963743949825

Clique em "Start Simulation" para rodar o projeto.

Observe o funcionamento no display LCD, nos LEDs e no buzzer conforme você ajusta o nível de água (alterando a distância no sensor ultrassônico virtual).
