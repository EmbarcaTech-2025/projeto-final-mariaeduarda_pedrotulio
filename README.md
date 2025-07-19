PROJETO FINAL: Rastreador Pessoal de Bem-Estar e Segurança 

Documento: Definição de Requisitos e Lista de Materiais 

Data: 14 de julho de 2025 

Versão: 1.0 

1. Descrição do Problema 

Indivíduos como idosos, pessoas que vivem sozinhas ou trabalhadores em ambientes isolados enfrentam um risco elevado em caso de emergências físicas, como quedas, onde o acesso a ajuda pode ser demorado ou impossível. Paralelamente, a população em geral está cada vez mais exposta a níveis elevados de estresse, com poucas ferramentas acessíveis e privadas para monitoramento do estado fisiológico e gestão da saúde mental. Existe uma lacuna no mercado para um dispositivo unificado que ofereça tanto uma rede de segurança para emergências físicas quanto um suporte proativo para o bem-estar mental do dia a dia. 

2. Objetivo do Projeto 

Desenvolver um protótipo funcional de um dispositivo eletrônico portátil e vestível, capaz de monitorar a segurança física e o bem-estar mental de um usuário. O sistema deverá integrar funcionalidades de detecção de queda, botão de pânico com alerta de emergência via rádio de longo alcance (LoRa), e monitoramento de sinais vitais (frequência cardíaca, SpO2). Adicionalmente, o dispositivo atuará como uma ferramenta de saúde mental, oferecendo análise de estresse através da Variabilidade da Frequência Cardíaca (HRV), exercícios de respiração guiada e um diário de humor. Todos os dados relevantes serão registrados em um cartão de memória para análise de padrões e histórico pessoal. 

3. Requisitos Técnicos 

3.1. Requisitos Funcionais (RF) 

RF01: Monitoramento de Sinais Vitais: O sistema deverá ler e exibir em tempo real a frequência cardíaca (em BPM) e a saturação de oxigênio no sangue (SpO2). 

RF02: Análise de Estresse (HRV): O sistema deverá ser capaz de calcular a Variabilidade da Frequência Cardíaca (HRV) para fornecer um indicador do nível de estresse fisiológico do usuário. 

RF03: Detecção Automática de Queda: O sistema deverá utilizar o acelerômetro para detectar automaticamente um evento de queda e iniciar um protocolo de alerta. 

RF04: Alerta de Pânico Manual: O sistema deverá permitir que o usuário acione manualmente um alerta de emergência através de um botão dedicado no teclado matricial. 

RF05: Rastreamento Geográfico: O sistema deverá adquirir as coordenadas de localização (latitude e longitude) através do módulo GPS. 

RF06: Comunicação de Alerta Remoto: Em caso de alerta (queda ou pânico), o sistema deverá transmitir uma mensagem via LoRa contendo um sinal de emergência e as últimas coordenadas GPS registradas. 

RF07: Exercício de Respiração Guiada: O sistema deverá fornecer uma interface visual no display LCD para guiar o usuário através de um exercício de respiração com ritmo controlado. 

RF08: Diário de Humor: O sistema deverá permitir ao usuário registrar uma nota de humor (escala de 1 a 5) através do teclado matricial. 

RF09: Registro de Dados (Data Logging): O sistema deverá salvar todos os eventos importantes (alertas, quedas), registros de humor e medições de sinais vitais (HR, SpO2, HRV) em um arquivo de texto no cartão SDCARD, com data e hora correspondentes. 

RF10: Interface com o Usuário: O sistema deverá exibir todas as informações, menus e alertas de forma clara no display LCD, permitindo a navegação entre os modos "Segurança" e "Bem-Estar". 

3.2. Requisitos Não Funcionais (RNF) 

RNF01: Portabilidade: O dispositivo final deverá ser compacto e leve o suficiente para ser carregado ou vestido pelo usuário confortavelmente. 

RNF02: Autonomia de Energia: Sendo alimentado por bateria, o protótipo deverá ter uma autonomia de, no mínimo, 4 horas de uso contínuo para fins de demonstração. 

RNF03: Usabilidade: A interface do usuário deverá ser intuitiva. A ativação do pânico e a navegação entre os menus principais devem ser simples e diretas. 

RNF04: Responsividade: O sistema deverá responder aos comandos do teclado e a eventos de queda em tempo real (latência inferior a 1 segundo). O alerta de pânico deve ser acionado em menos de 3 segundos após o comando. 

RNF05: Robustez: O protótipo deverá ser montado em um case (caixa protetora) que o proteja de impactos leves do uso cotidiano. 

4. Lista de Materiais 

Componente 

Interface / Tipo 

Função Principal no Projeto 

Placa Principal BitDogLab 

Microcontrolador 

Cérebro do projeto, processamento de todos os dados e lógica. 

[Sensor i2c] Oxímetro e Batimentos Cardíacos 

I2C 

Medição de SpO2, Frequência Cardíaca e dados para cálculo de HRV. 

[Sensor i2c] Acelerômetro 

I2C 

Detecção de movimento e algoritmo de detecção de queda. 

Periférico GPS 

UART 

Aquisição de coordenadas geográficas para localização. 

Periférico Comunicação LoRa 

SPI 

Transmissão do sinal de alerta de emergência de longo alcance. 

Periférico Display LCD 320x240 pixels 

SPI 

Interface principal com o usuário, exibição de todos os dados e menus. 

Periférico Teclado Matricial 

GPIO 

Entrada do usuário para acionar pânico, navegar em menus e registrar humor. 

Periférico Armazenamento SDCARD 

SPI 

Armazenamento de histórico de dados e eventos (Data Logging). 

Gerenciador de Bateria bq25622 

I2C (Embarcado) 

Gerenciamento de carga e fornecimento de energia da bateria. 

Bateria de Li-Ion ou LiPo 

Energia 

Fonte de alimentação para garantir a portabilidade do dispositivo. 

Estação Base Receptora 

LoRa + MCU 

Necessário um segundo kit (MCU + LoRa) para receber e demonstrar o alerta. 

Protoboard e Jumpers 

Conexão 

Conexão dos periféricos à placa principal durante o desenvolvimento. 

Case para Protótipo 

Estrutura 

Caixa (impressa em 3D ou outra) para proteger e dar forma final ao dispositivo.
