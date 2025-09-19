## Projeto Final: Sistema de Telemetria Veicular
*Documento: Definição de Requisitos e Lista de Materiais*
*Data:* 19 de setembro de 2025
*Versão:* 2.0

Link para vídeo do protótipo: https://www.youtube.com/shorts/0xexnAiSagE <br>
Link para apresentação em slides: https://www.canva.com/design/DAGzAQNm4pQ/IyQZWU2rYadh9C0FGD5n2A/edit?utm_content=DAGzAQNm4pQ&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton

**O projeto e as instruções sobre ele encontram-se no repositório shiftlight, adicionado como submódulo.**

## 📌 Descrição do Problema
Motoristas entusiastas e pilotos amadores buscam aprimorar sua performance e a de seus veículos, mas encontram dificuldades em obter dados detalhados e em tempo real de forma acessível.  
As ferramentas de telemetria existentes podem ser complexas e caras.  
A falta de informações sobre o desempenho do veículo — como a temperatura de admissão, o momento ideal de troca de marcha ou o desempenho em aceleração — impede uma direção mais eficiente e segura.  

Existe uma lacuna no mercado para um dispositivo unificado que compile e apresente essas informações de forma clara e interativa.

---

## 🎯 Objetivo do Projeto
Desenvolver um sistema de **telemetria veicular** utilizando um **Raspberry Pi Pico**, capaz de coletar, processar e exibir informações vitais do veículo em tempo real.  

O sistema utiliza um **script Python** como ponte para se comunicar com um **adaptador OBD-II Bluetooth**, obtendo dados do motor e enviando-os ao Pico via comunicação serial.  

O dispositivo apresenta uma **interface interativa em um display LCD**, controlada por um **joystick**, e integra funcionalidades como:  
- Monitoramento em tempo real  
- **Shift light progressivo** em matriz de LEDs  
- Testes de performance (0-100 km/h)  
- Análise de consumo  
- Sistema de alertas visuais para parâmetros críticos  

---

## ⚙️ Requisitos Técnicos

### 🔹 1. Requisitos Funcionais (RF)
- **RF1 – Visualização no Display**: O sistema exibe em tempo real múltiplos parâmetros do motor, como **RPM, velocidade, temperatura de admissão (IAT), temperatura do líquido de arrefecimento, avanço de ignição e AFR comandado**.  
- **RF2 – Menu Interativo**: O sistema possui um menu interativo, navegável via joystick, permitindo selecionar diferentes modos de operação.  
- **RF3 – Shiftlight Progressivo**: Informa o momento da troca de marcha por meio de uma **matriz de LEDs 5x5**, com efeitos progressivos conforme a RPM aumenta.  
- **RF4 – RPM Alvo Configurável**: O usuário pode ajustar o RPM alvo para o acionamento do shift light através do menu de configurações.  
- **RF5 – Estatísticas de Desempenho**: Registra e exibe o tempo de aceleração de **0 a 100 km/h**.  
- **RF6 – Teste de Gasto de Combustível**: Permite iniciar e parar um teste cronometrado de consumo, exibindo o **volume total gasto em litros**.  
- **RF7 – Sistema de Alertas**: Monitora parâmetros críticos (ex: IAT) e exibe **alerta visual em tela cheia** caso os limites sejam excedidos.  
- **RF8 – Datalogging em CSV**: O script Python grava os dados em arquivos `.csv` para análise posterior.  
- **RF9 – Comunicação Dual-Core**: O firmware do Pico utiliza os **dois núcleos** do microcontrolador:  
  - Um dedicado à recepção de dados seriais.  
  - Outro para lógica principal e interface gráfica.  

---

### 🔹 2. Requisitos Não Funcionais (RNF)
- **RNF1 – Portabilidade/Instalação**: O dispositivo final deve ser **compacto** e de **fácil instalação** no painel do veículo.  
- **RNF2 – Autonomia de Energia**: O protótipo deve ser alimentado via **porta USB**, com consumo otimizado.  
- **RNF3 – Usabilidade**: Interface intuitiva, com navegação por **joystick** e botão de seleção.  
- **RNF4 – Responsividade**: O sistema responde em **tempo real**, com latência mínima para medições críticas como o shift light.  
- **RNF5 – Robustez**: O protótipo deve ser protegido em um **case resistente a vibrações e impactos leves** do ambiente veicular.  

---

## 🛠️ Lista de Materiais

| Componente                  | Interface / Tipo         | Função Principal no Projeto                                                                 |
|-----------------------------|--------------------------|---------------------------------------------------------------------------------------------|
| **Raspberry Pi Pico**       | Microcontrolador         | Cérebro do projeto: processamento, lógica e controle dos periféricos                        |
| **Computador com Python**   | USB/Serial & BLE         | Executa o script que conecta ao OBD-II via Bluetooth e envia dados ao Pico via USB          |
| **Adaptador OBD-II**        | Bluetooth Low Energy     | Leitura de dados da ECU (RPM, velocidade, IAT, etc.)                                        |
| **Display LCD (ex: 240x240)** | SPI                    | Interface principal com o usuário: exibição de dados, menus e alertas                       |
| **Módulo Joystick Analógico** | GPIO / ADC             | Entrada para navegação em menus e interação com o sistema                                   |
| **Matriz de LEDs 5x5 WS2812B** | PIO (GPIO)            | Exibição visual progressiva do shift light                                                  |
| **Módulo de Som / Buzzer**  | GPIO                     | Emite alerta sonoro quando o RPM alvo do shift light é atingido                             |
| **Protoboard e Jumpers**    | Conexão                  | Conexão dos periféricos ao Raspberry Pi Pico durante o desenvolvimento                      |
| **Case para Protótipo**     | Estrutura                | Caixa (impressa em 3D ou outra) para proteger e dar forma final ao dispositivo              |

---
