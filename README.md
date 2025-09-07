## Projeto Final: Sistema de Telemetria Veicular
*Documento: Definição de Requisitos e Lista de Materiais*
*Data:* 14 de julho de 2025
*Versão:* 1.0

Link para vídeo do protótipo: https://www.youtube.com/shorts/0xexnAiSagE

### Descrição do Problema
Motoristas entusiastas e pilotos amadores buscam aprimorar sua performance e a de seus veículos, mas encontram dificuldades em obter dados detalhados e em tempo real de forma acessível. As ferramentas de telemetria existentes podem ser complexas e caras, exigindo conhecimento técnico avançado. A falta de informações sobre o desempenho do veículo, como a temperatura de admissão, o momento ideal de troca de marcha ou o desempenho em aceleração, impede uma direção mais eficiente e segura. Existe uma lacuna no mercado para um dispositivo unificado que compile e apresente essas informações de forma clara e interativa, auxiliando no aprimoramento da pilotagem.

---

### Objetivo do Projeto
Desenvolver um protótipo de um sistema de telemetria veicular capaz de coletar, processar e exibir informações vitais do veículo em um display. O sistema deverá integrar funcionalidades de monitoramento do motor, como a leitura de dados via OBD e a temperatura de admissão, e dados de desempenho, como o tempo de aceleração (0 a 100 km/h) e o consumo de combustível. O dispositivo terá uma interface interativa para que o usuário selecione as informações a serem visualizadas, além de um alerta para a troca de marchas. O sistema também deverá ser capaz de gravar vídeos da pista e monitorar o tempo de percurso via GPS, fornecendo um conjunto abrangente de ferramentas para análise de desempenho.

---

### Requisitos Técnicos

#### 1. Requisitos Funcionais (RF)
*RF1 – Visualização no Display:* O sistema deverá exibir informações do veículo em tempo real no display. <br>
*RF2 – Menu Interativo:* O sistema deverá ter um menu interativo que permitirá ao usuário selecionar as informações que deseja visualizar.<br>
*RF3 – Shiftlight:* O sistema deverá informar o momento certo da troca de marcha por meio de um aviso visual (shiftlight) no display.<br>
*RF4 – Monitoramento da Temperatura de Admissão:* O sistema deverá monitorar e exibir a temperatura do ar de admissão no display.<br>
*RF5 – Estatísticas de Desempenho:* O sistema deverá registrar e exibir estatísticas relacionadas à velocidade/desempenho do carro, como o tempo de 0 a 100 km/h.<br>
*RF6 – Teste de Gasto de Combustível:* O sistema deverá permitir que o usuário defina um tempo para realizar um teste de consumo de combustível e exibir o resultado no display.<br>
*RF7 – Monitoramento da Bateria:* O sistema deverá monitorar e exibir a voltagem da bateria do veículo no display.<br>
*RF8 – Gravação de Vídeo:* O sistema deverá utilizar uma câmera para realizar a gravação de vídeo da pista.<br>
*RF9 – Monitoramento de Percurso:* O sistema deverá utilizar um módulo GPS para monitorar e registrar o tempo de percurso.<br>
*RF10 – Cálculo de Aceleração e Frenagem:* O sistema deverá utilizar um acelerômetro para calcular o tempo de aceleração e frenagem.<br>

#### 2. Requisitos Não Funcionais (RNF)
*RNF1: Portabilidade/Instalação:* O dispositivo final deverá ser compacto e fácil de instalar e remover do veículo.<br>
*RNF2: Autonomia de Energia:* Sendo alimentado pela bateria do veículo, o protótipo deverá ter um consumo de energia otimizado para não impactar o sistema elétrico do carro.<br>
*RNF3: Usabilidade:* A interface do usuário deverá ser intuitiva. A ativação dos testes e a navegação entre os menus devem ser simples e diretas.<br>
*RNF4: Responsividade:* O sistema deverá responder aos comandos do teclado e aos dados do carro em tempo real, com latência inferior a 1 segundo para medições críticas como o shiftlight.<br>
*RNF5: Robustez:* O protótipo deverá ser montado em um case (caixa protetora) que o proteja de vibrações e impactos leves do ambiente veicular.<br>

---

### Lista de Materiais
| Componente | Interface / Tipo | Função Principal no Projeto |
| :--- | :--- | :--- |
| *Placa Principal BitDogLab* | Microcontrolador | Cérebro do projeto, responsável pelo processamento de todos os dados e pela lógica do sistema. |
| *Módulo OBD-II* | CAN/UART | Leitura de dados do motor, como RPM, velocidade, temperatura do motor, entre outros. |
| *[Sensor i2c] Acelerômetro* | I2C | Detecção de movimento para o cálculo de aceleração e frenagem. |
| *Periférico GPS* | UART | Aquisição de coordenadas geográficas para localização e medição de tempo de percurso. |
| *Periférico Display LCD 320x240 pixels* | SPI | Interface principal com o usuário, exibição de todos os dados e menus. |
| *Periférico Teclado Matricial* | GPIO | Entrada do usuário para navegação em menus, início de testes e interação com o sistema. |
| *Periférico Armazenamento SDCARD* | SPI | Armazenamento de histórico de dados e eventos (data logging), e gravações da câmera. |
| *Câmera Veicular* | USB/Interface | Gravação de vídeo da pista para análise. |
| *Protoboard e Jumpers* | Conexão | Conexão dos periféricos à placa principal durante o desenvolvimento. |
| *Case para Protótipo* | Estrutura | Caixa (impressa em 3D ou outra) para proteger e dar forma final ao dispositivo. |
