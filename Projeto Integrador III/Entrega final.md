# Sistema de Monitoramento IoT de Baixo Custo para Pecuária de Precisão com Comunicação LoRaWAN e Análise de Movimento por MPU6050

<details>
<summary><strong>Abstract</strong></summary>

<br>

Livestock monitoring is critical for ensuring animal welfare, improving productivity, and reducing losses in rural farming. This work presents the development of a low-cost, energy-efficient IoT-based system for real-time tracking and behavior analysis of cattle in extensive pasture environments in Brazil. The proposed solution integrates the TTGO T-Beam v1.2 microcontroller, equipped with GPS and the MPU6050 inertial sensor, to collect geolocation and movement data. Communication is handled via LoRaWAN using The Things Network (TTN), ensuring long-range and low-power data transmission. A conditional uplink mechanism transmits sensor data only when anomalous movement is detected, optimizing power consumption. The backend architecture uses MQTT and Node-RED for data processing and visualization in a web dashboard. Preliminary tests confirm stable sensor integration and efficient detection of unusual activity, validating the system’s potential for smart livestock management. The proposed system is scalable, cost-effective, and suitable for deployment in remote areas, supporting the advancement of precision livestock farming in Brazil.

**Keywords**: Livestock Monitoring, IoT, Sensors, LoRaWAN.

</details>

## Introdução

A Internet das Coisas (IoT) conecta sensores e atuadores por meio de Redes de Sensores Sem Fio (WSN – Wireless Sensor Network), permitindo a coleta e troca de dados em tempo real. Essa tecnologia tem transformado setores como o agronegócio, ao viabilizar a automação e o monitoramento remoto, aumentando a produtividade, eficiência e sustentabilidade, mesmo em regiões com recursos limitados (Lu et al., 2024).

Na agricultura, os sistemas baseados em IoT monitoram aspectos cruciais como temperatura, umidade, umidade do solo e níveis de nutrientes, permitindo a otimização de recursos e o aumento da produtividade das lavouras (Chamara et al., 2022). Da mesma forma, na pecuária, dispositivos IoT viabilizam o monitoramento em tempo real do comportamento, da saúde e da localização dos animais, fornecendo dados valiosos para que os produtores aprimorem a gestão do rebanho e a produtividade das fazendas (McClune et al., 2014; Ladha et al., 2013).

A agropecuária é um pilar essencial da economia brasileira, gerando milhões de empregos e respondendo por parcela significativa das exportações. No entanto, há muitos obstáculos a serem superados, como as consequências das mudanças climáticas, oscilações nos preços das commodities, falta de de mão de obra qualificada e acesso limitado a tecnologias avançadas, especialmente em áreas rurais e remotas.

Em especial, os pecuaristas brasileiros enfrentam desafios para monitorar de forma eficiente a saúde e o bem-estar dos animais, evitar fugas e furtos e administrar adequadamente os recursos. Tais desafios são ainda mais complexos em propriedades de grande extensão, comuns no Brasil, onde o pasto extenso dificulta o rastreamento e a proteção dos animais. Com IoT, é possível monitorar o rebanho continuamente, detectar comportamentos atípicos e antecipar intervenções de saúde animal. (Farooq et al., 2022). Isso permite aos produtores agir de forma rápida e preventiva, melhorando o cuidado com os animais, reduzindo perdas e otimizando a gestão geral da fazenda.

Embora a adoção da IoT na pecuária brasileira ainda esteja em desenvolvimento, seu potencial para transformar práticas tradicionais está se tornando cada vez mais evidente. Com o apoio de políticas públicas, incentivos tecnológicos e iniciativas de pesquisa aplicada, os produtores brasileiros podem utilizar sistemas IoT para reduzir perdas, detectar doenças precocemente e promover uma produção mais eficiente, inteligente e sustentável.

O monitoramento dos movimentos e comportamentos dos animais fornece dados essenciais sobre saúde e bem-estar. Mudança nos padrões de atividade frequentemente sinalizam estresse, doenças ou lesões, possibilitando intervenções antecipadas (Atthari, 2017). Isso é especialmente relevante em regiões do interior do Brasil, onde os animais pastam livremente e estão mais suscetíveis a se perderem ou serem furtados. Soluções de rastreamento baseadas em IoT contribuem para reduzir esses riscos, aumentar a segurança no campo e reforçar a estabilidade econômica das comunidades agropecuárias. A imagem abaixo mostra uma visão geral de um sistema com vários rastreadores de gado conectados ao servidor back-end por meio de um gateway LoRaWAN.
Os parâmetros de atividade coletados de cada dispositivo ativo são armazenados em um banco de dados SQL. Essa representação visual demonstra ideias futuras ao projeto atual.
<p align="center">
Figura 1: Representação geral de um sistema com vários rastreadores de gado
<img width="759" height="409" alt="image" src="https://github.com/user-attachments/assets/3767840f-8618-41e3-9857-0280808975ee" /> <br>
Fonte: Khadijah et al., 2019
</p>

Para uma implantação bem-sucedida dessas redes, ainda há desafios técnicos significativos a serem superados: condições ambientais adversas, alcance de comunicação, qualidade de serviço (QoS), custo de implementação e consumo energético (vida útil da bateria).

Nesse contexto, o protocolo LoRaWAN (Long Range Wide Area Network) tem se destacado como uma solução viável para aplicações de IoT em áreas rurais e remotas. Estudos recentes mostraram a eficácia do LoRa em resolver problemas de conectividade em regiões com infraestrutura limitada. Joshitha et al. (2021) estudaram um sistema baseado em LoRa para transmissão de dados a longa distância, destacando sua capacidade de operar em locais sem acesso a redes de comunicação convencionais. O mesmo estudo introduziu um dispositivo de rastreamento de longo alcance utilizando LoRa, garantindo autonomia de redes de terceiros e redução de custos operacionais.

Além disso, o LoRa utiliza modulação CSS (chirp spread spectrum) e opera na faixa ISM sub-GHz, oferecendo boa transmissão de sinal e resistência a interferências, características ideais para áreas com vegetação densa ou relevo acidentado, comuns no interior brasileiro.

O principal dispositivo de monitoramento de gado utilizado nesta pesquisa foi o TTGO T-Beam, um microcontrolador que integra LoRa, GPS, Wi-Fi e o sensor MPU6050, tornando-o ideal para regiões remotas com conectividade limitada e desafios energéticos. O módulo GPS permite o rastreamento preciso da localização, essencial para a segurança dos animais e redução de riscos durante o pasto livre. O Wi-Fi possibilita o envio de dados para plataformas em nuvem, facilitando o acesso remoto às informações em tempo real. Já o sensor MPU6050, que mede aceleração e velocidade angular, fornece dados detalhados sobre movimentos e orientação dos animais, possibilitando a identificação de comportamentos anormais que possam indicar sofrimento, doenças ou lesões (Khadijah et et al., 2025). As principais especificações do hardware utilizado estão listadas na Tabela 1. 

### Tabela 1 – Especificações técnicas do microcontrolador TTGO T-Beam v1.2 ESP32

| **Modelo**                    | **TTGO T-Beam v1.2 ESP32**                                 |
|------------------------------|-------------------------------------------------------------|
| **Bandas ISM (MHz)**         | IN865–867                                                   |
| **Semtech**                  | SX1276                                                      |
| **Potência de transmissão**  | 20 dBM                                                      |
| **Fator de espalhamento (SF)** | 7, 12                                                     |
| **Largura de banda (kHz)**   | 125 kHz, 250 kHz                                            |
| **Consumo de energia**       | **Modo ativo** (transmissão GPS & LoRa): 100–150 mA  <br> **Modo inativo**: 10–15 mA  <br> **Modo de sono profundo**: 1–2 mA |
| **Peso**                     | 52 g                                                       |


Com essa combinação de tecnologias, o Brasil pode contar com uma solução escalável, eficiente e de baixo custo para o gerenciamento pecuário. No cenário rural brasileiro, o LoRaWAN se destaca por sua capacidade de comunicação de longo alcance, baixo consumo de energia e uso de frequências não licenciadas, tornando-se ideal para aplicações como o rastreamento de gado em extensas regiões (Davcev et al., 2018).

O uso do TTGO T-Beam neste estudo tem como objetivo abordar os desafios específicos da pecuária brasileira, ao oferecer um sistema integrado de monitoramento em tempo real, rastreamento por GPS e análise de comportamento animal. Essa tecnologia representa uma ferramenta eficaz para aprimorar a gestão agropecuária, promovendo melhor cuidado com os animais, redução de perdas e aumento da resiliência econômica para enfrentar os desafios contemporâneos do setor agrícola nacional.


## Revisão da literatura

A Internet das Coisas (IoT) tem se destacado como uma solução tecnológica promissora para a transformação de setores tradicionais, como a agricultura e a pecuária, permitindo a automação de processos e a coleta de dados em tempo real. Essa transformação é possível graças ao avanço de sensores inteligentes, microcontroladores com conectividade sem fio e protocolos de comunicação de baixo consumo energético, como o LoRaWAN.

Vários estudos exploram o uso do LoRaWAN em ambientes remotos para monitoramento de condições ambientais e localização de ativos. Joshitha et al. (2021) propuseram um sistema de rastreamento animal com base em LoRa, destacando sua eficiência em áreas sem infraestrutura de comunicação convencional, o que reforça a viabilidade da tecnologia em ambientes rurais brasileiros. Davcev et al. (2018) também demonstraram que o LoRaWAN oferece um equilíbrio ideal entre longo alcance, baixo consumo de energia e operação em bandas não licenciadas, fatores críticos para o monitoramento pecuário em grandes propriedades.

No contexto específico da pecuária, Farooq et al. (2022) destacaram a importância de sistemas de monitoramento comportamental para a identificação precoce de doenças ou situações de estresse, a partir de dados coletados por sensores de movimento. O trabalho de Atthari (2017) complementa essa perspectiva ao mostrar como variações na atividade física de animais podem indicar anomalias comportamentais, sendo uma alternativa promissora para o manejo preventivo do rebanho.

Com relação ao uso de hardware, a placa TTGO T-Beam, baseada no microcontrolador ESP32 e equipada com GPS e LoRa, tem se mostrado uma escolha robusta para aplicações em IoT rural. Angriawan e Anugraha (2019) exploraram o uso do GPS integrado ao TTGO T-Beam para rastreamento em tempo real, além de utilizarem o acelerômetro MPU6050 para detectar padrões de movimento. Essa combinação de sensores também foi destacada por Mahaputra et al. (2019) e Putra e Romahadi (2021), que demonstraram a integração de múltiplas fontes de dados em sistemas embarcados de baixo custo.

Com base nessas referências, o presente trabalho desenvolveu um protótipo funcional para o monitoramento de gado em tempo real, utilizando um TTGO T-Beam alimentado por pilha, integrado ao sensor inercial MPU6050 e ao módulo GPS. O firmware foi construído com base na biblioteca LMIC-node, amplamente utilizada para aplicações com LoRaWAN. Após o pareamento com o The Things Network (TTN), utilizando as chaves DevEUI, AppEUI e AppKey (com o DevEUI obtido a partir do MAC do ESP32), foi possível estabelecer a comunicação com o backend da rede.

A lógica do sistema foi implementada para enviar as coordenadas GPS a cada 30 segundos, enquanto os dados do acelerômetro são enviados apenas quando há movimentação superior a 2.1g, simulando comportamentos atípicos em bovinos, como agitação repentina, quedas ou tentativa de fuga. Os dados recebidos pelo TTN foram encaminhados via protocolo MQTT para um ambiente Node-RED, onde foram processados e visualizados em um dashboard. A visualização propõe gráficos com dados do acelerômetro e um mapa interativo com as posições obtidas pelo GPS (utilizando o módulo worldmap).

Comparando-se com estudos anteriores, nota-se que a maioria dos protótipos em aplicações similares utiliza intervalos de transmissão maiores (ex: 10–15 minutos), focando na economia de energia e na durabilidade das baterias, como em Schulthess et al. (2024). Em contrapartida, este projeto priorizou a alta frequência de dados e a reatividade a eventos, embora ainda não tenha sido realizada uma análise da duração da bateria. Além disso, poucos trabalhos integram todos esses elementos em um único sistema: rastreabilidade, detecção de movimento anômalo e visualização em tempo real, de forma acessível e adaptável ao contexto brasileiro.

Portanto, a proposta desenvolvida pelo presente trabalho se diferencia ao combinar hardware de baixo custo, sensores estratégicos, comunicação LoRaWAN, processamento local e visualização remota, oferecendo uma solução escalável e aplicável à realidade de produtores rurais no Brasil. Ao alinhar os aprendizados da literatura internacional com a experimentação prática em território nacional, o projeto avança no desenvolvimento de ferramentas digitais acessíveis para o agronegócio.

## Objetivo Geral
Desenvolver e validar um sistema de monitoramento de bovinos baseado em Internet das Coisas (IoT), utilizando comunicação LoRaWAN e sensores embarcados para rastreamento por GPS e detecção de comportamentos anômalos, com foco na aplicabilidade em ambientes rurais brasileiros de baixa infraestrutura tecnológica.

### Objetivos Específicos
* Projetar um protótipo de dispositivo IoT utilizando o microcontrolador TTGO T-Beam com sensores GPS e MPU6050 integrados;

* Implementar a comunicação de longo alcance com baixo consumo energético por meio do protocolo LoRaWAN, utilizando a infraestrutura do The Things Network (TTN);

* Configurar o envio condicional de dados, baseado na detecção de aceleração acima de limiares predefinidos, visando identificar comportamentos atípicos dos animais;

* Realizar testes de bancada para validação do funcionamento simultâneo dos sensores e da comunicação com a rede LoRaWAN;

* Integrar os dados recebidos a uma plataforma de visualização em tempo real via protocolo MQTT e dashboard desenvolvido no Node-RED;

* Avaliar o desempenho do sistema em relação à responsividade, precisão dos dados e viabilidade de aplicação prática no contexto da pecuária de precisão.

## **Materiais e Métodos**

### **1. Materiais Utilizados**

O protótipo foi desenvolvido utilizando os seguintes componentes de hardware:

* **TTGO T-Beam v1.2**: placa baseada no microcontrolador ESP32, com conectividade LoRa (SX1276), GPS (u-blox NEO-6M) e Wi-Fi integrada.
* **Sensor inercial MPU6050**: sensor de 6 eixos (acelerômetro e giroscópio).
* **Fonte de alimentação**: pilha Li-Ion recarregável 18650 (3.7V).
* **Antena LoRa**: integrada ao TTGO.
* **Computador pessoal** com PlatformIO como ambiente de desenvolvimento (executando no VS Code), bibliotecas LMIC-node(..) e conexão com a internet para configuração do backend (TTN, Node-RED).
  
* **Plataformas utilizadas**:

  * **The Things Network (TTN)** para comunicação com a rede LoRaWAN.
  * **Node-RED** para recepção, visualização e dashboard via protocolo MQTT.
  * **MQTT broker** (Mosquitto ou TTN MQTT Bridge).

### **2. Métodos**
### **2.1 Configuração do Hardware**

#### **2.1.1 Fundamentos do Sistema de Posicionamento Global (GPS) e Testes Iniciais**

O Global Positioning System (GPS) é um sistema de navegação por satélite que permite determinar com precisão a localização de um objeto em qualquer lugar da superfície terrestre, por meio da sincronização de sinais recebidos de satélites. O GPS faz parte do conjunto de tecnologias GNSS (Global Navigation Satellite System) e requer a captação de sinais de, no mínimo, três satélites para calcular coordenadas bidimensionais (latitude e longitude) ou de quatro satélites para determinar a posição tridimensional (latitude, longitude e altitude) [Angriawan and Anugraha, 2019].

A comunicação entre o ESP32 e o módulo GPS da TTGO ocorre via UART1 (Universal Asynchronous Receiver-Transmitter), uma interface serial assíncrona de baixo nível muito comum em microcontroladores. Nessa configuração, a porta UART1 é utilizada para receber os dados NMEA (National Marine Electronics Association), que são sentenças de texto padronizadas que contém informações de navegação, como latitude, longitude, horário, número de satélites conectados, altitude, entre outros.

Para configurar a leitura dos dados, utilizou-se a biblioteca TinyGPSPlus, que oferece uma abstração eficiente para decodificação das sentenças NMEA. Ela possibilita a extração direta de valores como latitude, longitude, número de satélites e altitude com precisão e facilidade, otimizando o processo de desenvolvimento.
```
#include <TinyGPSPlus.h>
#include <HardwareSerial.h>

TinyGPSPlus gps;
HardwareSerial SerialGPS(1);

void setup() {
  Serial.begin(115200);
  SerialGPS.begin(9600, SERIAL_8N1, 34, 12); 
}
```

No trecho acima, a instância SerialGPS configura a UART1 com taxa de transmissão de 9600 bps, e os pinos 34 (RX) e 12 (TX), conforme mapeamento padrão da TTGO T-Beam. A função gps.encode() da biblioteca TinyGPSPlus processa os bytes recebidos e atualiza automaticamente os campos relevantes.

Os testes foram realizados em ambiente externo, garantindo uma visibilidade direta para o céu. Essa prática é essencial, pois obstáculos físicos como podem dificultar a aquisição de sinal dos satélites. Após o posicionamento adequado da antena do GPS, foi observado a fixação estável de pelo menos 5 satélites, o que garantiu a leitura confiável dos parâmetros de localização tridimensional.

A cada segundo, o sistema verificava se novos dados estavam disponíveis com gps.location.isUpdated(), imprimindo os valores recebidos no monitor serial. As leituras consistentes de latitude, longitude e altitude demonstraram que a recepção e decodificação dos dados NMEA estavam sendo realizadas corretamente.
```
  if (gps.location.isUpdated()) {
    Serial.print("Latitude: ");
    Serial.println(gps.location.lat(), 6);
    Serial.print("Longitude: ");
    Serial.println(gps.location.lng(), 6);
    Serial.print("Satélites: ");
    Serial.println(gps.satellites.value());
    Serial.print("Altitude: ");
    Serial.println(gps.altitude.meters());
  }
```
Esse teste isolado foi fundamental para assegurar que o módulo GPS estivesse operacional antes da integração com o sistema LoRaWAN e com o acelerômetro MPU6050. O uso das bibliotecas TinyGPSPlus e HardwareSerial revelou-se apropriado tanto pela sua simplicidade quanto pela eficácia no processamento dos dados GNSS, particularmente em um contexto com restrições de recursos computacionais, como o da TTGO.


#### ** 2.1.3 Integração do Sensor MPU6050 via I²C**

Após os testes individuais com o módulo GPS embarcado na placa TTGO T-Beam, foi realizada a integração do acelerômetro MPU6050 ao sistema. O objetivo deste teste foi verificar a leitura simultânea de dados de localização (GPS) e aceleração (MPU6050), assegurando que ambos os sensores operam corretamente em conjunto, utilizando as interfaces UART e I2C da placa TTGO.

O MPU6050 foi o sensor escolhido para o presente trabalho. Trata-se de uma Unidade de Medida Inercial (IMU) que integra sensores de aceleração, nos eixos X, Y e Z, e de rotação angular (giroscópio) nos mesmos eixos. Além disso, possui uma interface de comunicação simples, utilizando o protocolo I2C, o que facilita sua integração com controladores, sendo utilizado neste caso o ESP32. A escolha desse sensor se deu por suas diversas vantagens, como o fato de ser compacto, oferecendo em um único chip a leitura de aceleração e rotação. Ele também apresenta alta precisão, o que o torna confiável para aplicações que exigem medições consistentes. Seu excelente custo-benefício o torna ideal para prototipagem, e seu baixo consumo de energia o torna adequado para sistemas embarcados e dispositivos móveis (Fedorov et al., 2015).

A comunicação com o módulo GPS foi realizada via UART1, utilizando os pinos 34 (RX) e 12 (TX). Já o acelerômetro MPU6050 foi conectado ao barramento I2C padrão (pinos 21 SDA e 22 SCL). O código utilizado baseou-se novamente na bibliotecas TinyGPS++ com adição da MPU6050, que oferecem alto nível de abstração para facilitar a leitura de dados dos respectivos sensores. Além disso, ele foi estruturado para ler continuamente os dados do GPS, verificando a disponibilidade de novas leituras, obter os valores brutos de aceleração do MPU6050 e converter os valores brutos em g (gravidade). 
<p align="center">
Figura 2: Protótipo do Hardware IoT. <br>
<img width="696" height="552" alt="image" src="https://github.com/user-attachments/assets/4624dd4a-6baf-42da-a6d3-710d82916f03" />  <br>
Fonte: Khadijah et al., 2019 <br>
Figura 3: Foto ilustrativa de como será utilizado o colar no gado. 
<img width="804" height="583" alt="image" src="https://github.com/user-attachments/assets/98c6baed-087b-46c2-9cc1-d22798e6153e" />  <br>
Fonte: Barker et al., 2018
</p>

Para a identificação de comportamentos anômalos em bovinos, é fundamental compreender os padrões normais de aceleração durante as atividades rotineiras dos animais. Estudos indicam que, durante a locomoção em piso rígido, como concreto, as pernas das vacas apresentam uma aceleração média na faixa de 1,62 a 1,72 g, enquanto em pisos mais macios, esse valor tende a ser levemente inferior. Essas faixas representam padrões típicos de caminhada e movimentação tranquila (Chapinal et al., 2011). O acelerômetro, nesse caso, pode ser utilizados para detectar desvios desses valores, que podem indicar comportamentos fora do normal, como mancar, agitação, brigas, fugas ou até mesmo tentativas de levantar-se de maneira brusca. 

Em pesquisas voltadas à classificação automática de comportamento animal, valores médios de aceleração iguais ou superiores a 2,1 g têm sido usados como limiar para identificar atividades elevadas ou atípicas, especialmente quando persistem por janelas de tempo superiores a dois minutos. Assim, valores que se mantêm consistentemente acima desse patamar podem ser interpretados como indicadores de comportamento anômalo, principalmente quando analisados em conjunto com outros dados, como posicionamento ou observação visual (Barker, Z.E. et al., 2018). Esse conhecimento é fundamental para o desenvolvimento de sistemas de monitoramento automatizado no contexto da pecuária de precisão.

Durante os testes em bancada, foi possível observar a correta leitura e impressão dos dados no terminal serial, conforme o exemplo:
```
Latitude  : -26.91235
Longitude : -49.0731
Satellites: 5
Altitude  : 34.58 M
Time      : 14:32:18
Aceleração total (G): 1.03
```
O sistema se mostrou estável e responsivo durante todo o experimento, sendo possível visualizar alertas de movimentação brusca ao movimentar manualmente o módulo MPU6050. A integração dos sensores e o sucesso na coleta paralela dos dados validam essa etapa como fundamental para a evolução do projeto, possibilitando o início do último teste, o envio de dados via LoRaWAN.


### **2.2 Programação do Dispositivo**

### **2.2.1 Configuração LoRaWAN no LMIC-node**

Com a validação individual dos módulos GPS e acelerômetro MPU6050 concluída, foi iniciada a etapa de integração do sistema com a rede LoRaWAN por meio do The Things Network (TTN). Para isso, utilizou-se a biblioteca LMIC-node, baseada na pilha MCCI LMIC, adaptada para facilitar o desenvolvimento com placas ESP32 como a TTGO T-Beam. Essa biblioteca oferece uma estrutura modular, facilitando a integração de sensores e o envio de pacotes LoRa de forma eficiente.

Para permitir a comunicação da placa TTGO T-Beam com a rede The Things Network (TTN) via protocolo LoRaWAN, foi utilizada a biblioteca de código aberto LMIC-node. Essa biblioteca já fornece uma estrutura modular compatível com o padrão OTAA (Over-The-Air Activation), exigindo apenas a personalização dos arquivos de chave e alguns parâmetros de rede.

O primeiro passo foi a geração do identificador DevEUI, que representa de forma única o dispositivo na rede LoRaWAN. Para isso, foi carregado um código simples no ESP32 que imprime o endereço MAC no monitor serial, por exemplo:
```
void setup() {
  Serial.begin(115200);
  Serial.println("DevEUI:");
  uint64_t chipid = ESP.getEfuseMac();
  for (int i = 0; i < 8; i++) {
    Serial.printf("%02X-", (uint8_t)(chipid >> (8 * (7 - i))));
  }
}
```
O valor obtido foi então utilizado como DevEUI e substituído na estrutura do arquivo lorawan-keys.h, localizado na pasta keyfiles da biblioteca LMIC-node.

A chave AppEUI foi definida manualmente, seguindo o padrão de 8 bytes em hexadecimal, enquanto a AppKey foi gerada automaticamente pela plataforma TTN no momento do registro do dispositivo. Ambas foram adicionadas ao arquivo lorawan-keys.h, substituindo os valores de exemplo:
```
static const u1_t PROGMEM APPEUI[8] = { 0x11, 0x00, 0xFF, 0xEE, 0xDD, 0xCC, 0xBB, 0xAA };
static const u1_t PROGMEM DEVEUI[8] = { ... };  // Do MAC
static const u1_t PROGMEM APPKEY[16] = { ... }; // Gerada pelo TTN
```
Também foi atualizado o identificador do dispositivo para fins de organização no monitor serial e na interface do TTN:

```
#define DEVICEID "gps1"
```
No arquivo platformio.ini, foi selecionada a placa ttgo-lora32-v1, compatível com a TTGO T-Beam, além da região de frequência AU915 (utilizada no Brasil). A estrutura ficou semelhante a:

```
[env:ttgo-lora32-v1]
platform = espressif32
board = ttgo-lora32-v1
framework = arduino
```
A LoRaWAN AU915 possui múltiplas sub-bandas (0 a 7). Para garantir a compatibilidade com o gateway local, foi configurada a sub-banda 2 diretamente no código principal (.cpp), com a seguinte linha:

```
LMIC_selectSubBand(2);
```
Essa sub-banda deve coincidir com a sub-banda configurada no gateway LoRaWAN que está sendo utilizado.

Com a configuração concluída, foi realizada a compilação e o upload do código baseado na estrutura do LMIC-node. O código gerenciava automaticamente a requisição OTAA e, após a confirmação do evento EV_JOINED, iniciava o envio periódico de pacotes via uplink para a TTN.

No TTN Console, os pacotes eram recebidos corretamente, permitindo a visualização dos dados transmitidos diretamente pela interface da rede.

### 2.2.2 **Integração dos Sensores com Envio Condicional via LoRaWAN**

Após estabelecer a conexão com a rede LoRaWAN por meio do LMIC-node, foi iniciada a etapa de integração dos sensores responsáveis pela coleta dos dados ambientais. O sistema foi expandido para incorporar um acelerômetro MPU6050 e o módulo GPS interno da placa TTGO T-Beam, com o objetivo de detectar movimentos anômalos em animais e associar essa movimentação à localização geográfica no momento da ocorrência. Foram incluídas ao projeto as bibliotecas necessárias para comunicação com os sensores:

```
#include <Wire.h>
#include <MPU6050.h>
#include <TinyGPS++.h>
```
No código principal da LMIC-node, as leituras e o processamento dos sensores foram inseridos dentro da função processWork(), que é executada de forma cíclica após a inicialização e conexão do dispositivo à rede LoRaWAN. O primeiro passo dentro da função foi verificar se o dispositivo já estava conectado com sucesso (checando se LMIC.devaddr != 0). Em seguida, os dados do GPS e do acelerômetro foram adquiridos:
```
if (LMIC.devaddr == 0) return;
while (gpsSerial.available()) {
    gps.encode(gpsSerial.read());
}
int16_t ax, ay, az;
mpu.getAcceleration(&ax, &ay, &az);

// Conversão para unidade de gravidade (g)
float xg = ax / 16384.0;
float yg = ay / 16384.0;
float zg = az / 16384.0;

float totalAccel = sqrt(xg * xg + yg * yg + zg * zg);
```
O valor da aceleração total (totalAccel) foi comparado a um limiar de 2.1 g, valor empiricamente definido para simular comportamentos anômalos no gado, como quedas, corridas repentinas ou convulsões como já visto. Caso esse limiar fosse ultrapassado e os dados de localização estivessem válidos (gps.location.isValid()), o dispositivo prepararia os dados para envio via LoRaWAN.

Devido à limitação de payloads LoRa (geralmente 11 a 51 bytes em redes LoRaWAN Classe A), os dados foram compactados em um buffer de 9 bytes, onde: latitude com 4 bytes (int32_t), com precisão de até 6 casas decimais, convertido por multiplicação por 1e6; Longitude com 4 bytes (int32_t), também multiplicado por 1e6; E por último, a aceleração com 1 byte, convertido para inteiro com duas casas decimais, multiplicado por 100 (exemplo: 1.78g se torna 178). Segue abaixo parte do código que define a quantidade de casas decimais:

```
int32_t latEnc = lat * 1e6;
int32_t lonEnc = lon * 1e6;
uint8_t accelByte = (uint8_t)(totalAccel * 100);

payloadBuffer[0] = latEnc >> 24;
payloadBuffer[1] = latEnc >> 16;
payloadBuffer[2] = latEnc >> 8;
payloadBuffer[3] = latEnc;
payloadBuffer[4] = lonEnc >> 24;
payloadBuffer[5] = lonEnc >> 16;
payloadBuffer[6] = lonEnc >> 8;
payloadBuffer[7] = lonEnc;
payloadBuffer[8] = accelByte;
```
Com os dados devidamente preparados, a função scheduleUplink() foi chamada para enviar o payload ao TTN (The Things Network), utilizando uplink programado com prioridade normal (10):
```
scheduleUplink(10, payloadBuffer, 9);
```
Caso o movimento fosse inferior ao limiar definido ou se os dados de GPS estivessem indisponíveis, o envio não era realizado, e uma mensagem de status deverá ser impressa na serial como previsto no código:
```
Serial.println("🔵 Nenhum movimento relevante ou GPS inválido.");
```
Essa abordagem permite reduzir o número de transmissões, economizando energia e largura de banda na rede LoRaWAN — aspectos críticos para aplicações em áreas rurais.

### **2.3 Integração com Backend e Visualização via MQTT**

A escolha do protocolo de comunicação é um dos elementos críticos em projetos de Internet das Coisas (IoT), principalmente quando os dispositivos operam em redes com largura de banda limitada e exigências energéticas restritas, como em aplicações com LoRaWAN em ambientes rurais. Neste projeto, optou-se pela utilização do protocolo MQTT (Message Queuing Telemetry Transport) em detrimento do tradicional HTTP, visando garantir maior eficiência na comunicação entre os dispositivos e o backend de visualização de dados.

Segundo estudo de Thangavel et al. (2018), o MQTT se destaca por utilizar um modelo de publicação e assinatura (publish/subscribe) baseado em conexões TCP persistentes, o que proporciona menor consumo de banda, baixa latência e eficiência energética significativamente superior ao modelo request/response do HTTP. O artigo também ressalta que o MQTT permite a configuração de níveis de Qualidade de Serviço (QoS), essenciais para garantir a entrega confiável das mensagens, um aspecto importante em aplicações que monitoram comportamentos críticos de animais.

Além disso, o cabeçalho compacto do MQTT e seu baixo overhead tornam o protocolo ideal para dispositivos com recursos limitados, como os empregados neste estudo, baseados no microcontrolador TTGO T-Beam com sensores embarcados. A integração com o The Things Network (TTN) foi realizada via TTN MQTT bridge, o que exigiu a geração de uma chave de autenticação (API Key) diretamente no console da plataforma e sua posterior configuração no fluxo de dados do Node-RED, ferramenta responsável pela visualização dos dados em tempo real em um dashboard interativo. A Tabela 3 mostra os parâmetros utilizados para a configuração do protocolo MQTT no backend TTN. 

### Tabela 2 – Especificações do TTGO T-Beam v1.1 ESP32 
  
| Parâmetro       | Valor                                                       |
| --------------- | ----------------------------------------------------------- |
| **MQTT Host**   | `nam1.cloud.thethings.network`                              |
| **Porta**       | `8883` (SSL/TLS)                                            |
| **Username**    | `gps-agro@ttn`                                              |
| **Password**    | A **chave gerada** dessa API key                            |
| **Tópico MQTT** | `v3/gps-agro@ttn/devices/+/up`                              |

O uso da porta 8883 com TLS garante segurança na transmissão dos dados sensíveis. Além disso, o uso do tópico genérico com coringa + facilita a subscrição de múltiplos dispositivos no mesmo dashboard
A adoção do MQTT, portanto, alinha-se às melhores práticas para comunicação em sistemas IoT distribuídos, conforme demonstrado pela literatura, assegurando um balanceamento adequado entre confiabilidade, leveza e escalabilidade da solução proposta.

A arquitetura do backend foi composta por três elementos principais: Broker MQTT (TTN MQTT Bridge) responsável por receber os pacotes uplink transmitidos pela rede LoRaWAN e disponibilizá-los para assinantes MQTT; Node-RED, um ambiente de programação visual usado para processar os dados em tempo real, convertê-los para formatos legíveis e alimentar os dashboards interativos; Dashboard Web construída no próprio Node-RED, utilizando widgets de gráfico e mapa interativo (worldmap) para exibir a trajetória dos animais e os dados de aceleração.

Essa abordagem permitiu uma visualização eficiente dos eventos capturados pelo dispositivo, como movimentos anômalos e localização GPS, com mínimo atraso, sem a necessidade de chamadas HTTP periódicas (polling), que aumentariam o tráfego de rede e o consumo de energia.


## Resultados

Este trabalho utiliza dados temporais de um módulo GPS e do sensor MPU6050 para rastrear localização e movimento. Após a implementação completa do protótipo, foram realizados testes de envio e recepção de dados por meio da infraestrutura da The Things Network (TTN), utilizando comunicação LoRaWAN. O foco principal desta etapa foi verificar a integridade dos dados transmitidos, a resposta do sistema a eventos de movimento anômalo e a correta visualização no dashboard construído via Node-RED. 

A imagem 4 mostra a interface do TTN onde são exibidos os dados recebidos em tempo real dos dispositivos conectados. Aqui é possível visualizar o payload (dados enviados pelo sensor), junto com os metadados da transmissão, como a intensidade do sinal (RSSI), relação sinal-ruído (SNR), frequência utilizada, e o timestamp da mensagem. Essa visão é útil para monitorar se os dispositivos estão enviando dados corretamente e para uma análise rápida dos valores recebidos.

<p align="center"> 
Figura 4: Registro dos dados recebidos em tempo real no Live Data do TTN (The Things Network) </br> 
<img width="1519" height="452" alt="image" src="https://github.com/user-attachments/assets/3bc6aaff-0857-42dc-8ad4-50741ec3b6bf" />  </br> 
Fonte: Autor </br> 
</p>

No contexto de comunicação LoRaWAN, os dados enviados pelo dispositivo são compactados em um payload binário (em bytes), que precisa ser interpretado corretamente no backend (no caso, o The Things Stack). O código a seguir foi desenvolvido para garantir a interpretação correta e segura (como mostrado na figura 4) dos 9 bytes recebidos em cada uplink, evitando erros comuns relacionados à conversão de inteiros com sinal e à estrutura dos dados.

A latitude e longitude são enviadas como inteiros de 32 bits com sinal (signed int32), ou seja, podem conter valores negativos. No entanto, o JavaScript possui limitações ao usar operadores bitwise (<<), principalmente quando o primeiro byte tem o bit mais significativo ativado, pois isso pode resultar em valores incorretos devido à forma como o JavaScript lida com bits de sinal. Para evitar isso, o código utiliza um ArrayBuffer e DataView, que são objetos nativos do JavaScript criados justamente para manipular dados binários de forma precisa e com controle explícito sobre o tipo (int32, uint8, etc.) e o endianness (ordem dos bytes).

```
function decodeUplink(input) {
  if (input.bytes.length !== 9) {
    return {
      errors: ["Payload inválido, deve ter 9 bytes."]
    };
  }
  const buffer = new ArrayBuffer(4);
  const view = new DataView(buffer);

  // Função segura para ler int32 de forma assinada
  function readInt32(bytes, offset) {
    const b = bytes.slice(offset, offset + 4);
    for (let i = 0; i < 4; i++) view.setUint8(i, b[i]);
    return view.getInt32(0); // padrão big-endian
  }

  const latRaw = readInt32(input.bytes, 0);
  const lonRaw = readInt32(input.bytes, 4);
  const accelRaw = input.bytes[8];

  return {
    data: {
      latitude: latRaw / 1e6,
      longitude: lonRaw / 1e6,
      acceleration_g: accelRaw / 100.0
    }
  };
}
```

Contanto, durante os testes, os pacotes uplink foram transmitidos para a TTN sempre que o acelerômetro detectava uma movimentação superior a 2.1 g e os dados do GPS estavam válidos. O payload enviado incluía latitude, longitude e aceleração total em um formato compacto de 9 bytes.

Esses dados foram redirecionados para o Node-RED via MQTT, onde foi possível decodificá-los. Com isso, foi possível construir um dashboard funcional, exibindo a ideia de como ficará a visualização da localização dos animais no mapa (worldmap) e os eventos de movimentação com base nos dados do sensor MPU6050. A seguir, a figura 5 apresenta o ambiente de desenvolvimento e da interface gráfica desenvolvida no Node-RED, utilizadas no projeto de monitoramento de gado.

<p align="center"> 
Figura 5: Fluxogramado Sistema no Node-RED </br> 
<img width="1287" height="394" alt="image" src="https://github.com/user-attachments/assets/28ed163f-786d-477c-bb11-163778a30ea9" />
</p> 

Os dados de localização GPS foram visualizados corretamente no mapa interativo (worldmap) e na dashboard, mais especificamente na aba "Mapa" mostrada na figura 7. Já os dados de aceleração (MPU6050), embora coletados e transmitidos, não estão sendo corretamente interpretados no TTN e, portanto, ainda não aparecem no dashboard como valores legíveis. As imagens a seguir apresentam o dashboard completo desenvolvido com Node-RED.

<p align="center"> 
Figura 6: Interface UI com Subpáginas de Aceleração e Localização </br>
<img width="258" height="380" alt="image" src="https://github.com/user-attachments/assets/d12d91f7-f566-4be0-8f66-7b4544dc00aa" /> </br>
Fonte: Autor </br>
Figura 7: Dashboard do Node-RED para visualização de aceleração (dados não recebidos corretamente) </br> 
<img width="1916" height="560" alt="image" src="https://github.com/user-attachments/assets/277af276-f9c8-46de-90ed-4c0431b46cad" /> </br>
Fonte: Autor </br>
Figura 8: Dashboard do Node-RED para visualização da posição do gado </br>
<img width="1907" height="916" alt="image" src="https://github.com/user-attachments/assets/dfdfa7eb-1ea5-4367-95b5-e4436b60a470" /> </br>
Fonte: Autor </br>
Figura 9:  Página do Worldmap para visualização do rastreamento </br>
<img width="1911" height="916" alt="image" src="https://github.com/user-attachments/assets/5d1b892a-eb51-49bb-9c3b-9fcd0a7bee05" /> </br>
Fonte: Autor
</p>

Apesar dessas limitações, os testes confirmam que o sistema é capaz de identificar movimentos fora do padrão e associá-los a coordenadas geográficas, cumprindo seu objetivo principal. O uso de MQTT mostrou-se eficiente para transportar os dados entre o TTN e o Node-RED com baixa latência.


## Conclusão

Em suma, foi desenvolvido um sistema baseado em IoT utilizando a placa TTGO T-Beam com suporte a GPS, acelerômetro (MPU6050) e conectividade LoRaWAN, com o objetivo de monitorar em tempo real a movimentação e localização de animais em áreas rurais. Diferentemente de abordagens que priorizam a economia de energia com intervalos longos de envio de dados, este sistema priorizou a alta frequência de amostragem, enviando informações a cada 30 segundos ou imediatamente após detecção de movimentos anômalos.

Os dados capturados pelos sensores foram processados e transmitidos para a rede The Things Network (TTN) via protocolo LoRaWAN utilizando o método OTAA. Com isso, foi possível visualizar com precisão os dados de localização no site (TTN) e os eventos de movimentação com base no acelerômetro. O sistema mostrou-se eficaz na captação de dados relevantes para rastreamento de animais em tempo real, podendo contribuir para o controle de posicionamento e segurança do rebanho. 

### Dificuldades encontradas

Durante o desenvolvimento do projeto, foram encontradas diversas dificuldades técnicas, especialmente relacionadas à integração das diferentes camadas de hardware e software envolvidas. Uma das principais barreiras iniciais foi o entendimento da biblioteca LMIC-node, utilizada para a comunicação via protocolo LoRaWAN com a rede The Things Network (TTN). Apesar de ser uma biblioteca robusta e amplamente utilizada na comunidade, sua estrutura modular, os diversos arquivos de configuração e os pontos específicos onde o código do usuário deve ser inserido exigiram um esforço considerável de estudo e testes práticos para adaptação às necessidades do projeto.

Outra dificuldade significativa foi o envio correto do payload. Embora os dados estivessem sendo lidos corretamente no sensor MPU6050, houve resistência no entendimento da maneira correta de compactar, codificar e transmitir essas informações via LoRa para que fossem interpretadas corretamente no TTN. Embora fosse possível detectar movimentações e calcular a aceleração total no dispositivo, os dados não estavam sendo transmitidos corretamente ao TTN ou não estavam sendo refletidos como esperado no dashboard do Node-RED. Isso levantou a necessidade de revisar toda a lógica de detecção de movimento, a forma de compactação do payload e o correto agendamento dos uplinks dentro do fluxo da biblioteca LMIC.

Por fim, um desafio recorrente foi a decodificação dos dados no TTN. Sem uma função de decoder ativa, os dados chegavam ao TTN como um array bruto de bytes (frm_payload), o que dificultava a validação visual dos valores de aceleração. Embora fosse possível decodificar esses dados diretamente no Node-RED, isso impôs uma etapa adicional de complexidade e aumentou o risco de erros durante os testes.

Esses obstáculos, embora desafiadores, proporcionaram um aprendizado significativo em protocolos de comunicação sem fio, manipulação de dados binários e integração de sistemas IoT com plataformas na nuvem.

### Sugestões para trabalhos futuros

Apesar dos avanços obtidos neste projeto, ainda há diversas possibilidades de aprimoramento que podem ser exploradas em trabalhos futuros, tanto na parte de software quanto de hardware, com o objetivo de tornar o sistema mais robusto, preciso e funcional.

Uma das principais sugestões é a implementação de um decodificador personalizado diretamente no The Things Network (TTN). Atualmente, os dados são enviados em formato compacto (payload binário) e não são decodificados automaticamente no TTN, dificultando a leitura e análise direta dos valores recebidos. A criação de um script decoder em JavaScript dentro do próprio console TTN permitiria a transformação automática desses dados binários em objetos JSON com campos legíveis (latitude, longitude, aceleração, etc.), facilitando a depuração e a integração com plataformas externas como o Node-RED.

Além disso, é recomendável otimizar o intervalo de envio dos dados. Atualmente, o sistema foi configurado para enviar pacotes a cada 30 segundos, mas observou-se que o TTN efetivamente os processa em intervalos maiores, frequentemente a cada 1 minuto. Isso pode ser reflexo das limitações de duty cycle (limite de tempo de transmissão permitido por norma regulatória em redes LoRaWAN) impostas pelas normas de comunicação LoRaWAN (especialmente em regiões como AU915). Assim, trabalhar em estratégias de compactação mais eficientes e em um cronograma de transmissão adaptativo, por exemplo, transmitindo apenas quando há mudanças significativas nos dados, pode reduzir o tráfego desnecessário e respeitar os limites da rede.

Outra sugestão importante é a melhoria na lógica de interpretação dos dados do acelerômetro. Embora o sistema seja capaz de detectar movimentos anômalos, ainda há desafios na correta visualização dessas informações no dashboard do Node-RED. Refinar a forma como os dados são empacotados e interpretados permitirá melhor detecção de eventos e maior confiabilidade na identificação de comportamentos atípicos dos animais.

Adicionalmente, o sistema pode ser expandido com novos sensores, como sensores de temperatura corporal, sensores de batimentos cardíacos ou sensores ambientais. A integração desses novos módulos permitirá um monitoramento mais completo do bem-estar animal, transformando o sistema em uma solução ainda mais abrangente para aplicações no agronegócio.

Por fim, propõe-se também a realização de testes com múltiplos dispositivos em campo real, operando simultaneamente. Isso permitirá validar o comportamento do sistema em escala e analisar o desempenho da rede LoRaWAN em cenários mais complexos, com vários nós sensores enviando dados de forma assíncrona para um mesmo gateway.

Essas melhorias futuras têm potencial para transformar a solução proposta em um sistema de monitoramento inteligente e escalável, aplicável a diferentes contextos rurais e adaptável a diversas necessidades do setor agropecuário.

## Referências

LU, J. et al. Secure and real-time traceable data sharing in cloud-assisted IoT. IEEE Internet of Things Journal, v. 11, n. 4, p. 6521–6536, 2024.

CHAMARA, N. et al. Ag-IoT for crop and environment monitoring: past, present, and future. Agricultural Systems, v. 203, p. 103497, 2022.

McCLUNE, D. W. et al. Tri-axial accelerometers quantify behaviour in the Eurasian badger (Meles meles): towards an automated interpretation of field data. Animal Biotelemetry, v. 2, p. 1–6, 2014.

LADHA, C. et al. Dog’s life: wearable activity recognition for dogs. In: Proceedings of the 2013 ACM International Joint Conference on Pervasive and Ubiquitous Computing. p. 415–418, 2013.

FAROOQ, M. S. et al. A survey on the role of IoT in agriculture for the implementation of smart livestock environment. IEEE Access, v. 10, p. 9483–9505, 2022.

ATTHARI, A. Sistem tracking position berdasarkan titik koordinat GPS menggunakan smartphone. Jurnal Infomedia: Teknik Informatika, Multimedia, dan Jaringan, v. 2, n. 1, p. 1–6, 2017.

JOSHITHA, C. et al. LoRaWAN-based cattle monitoring smart system. In: International Conference on Energy, Environment and Sustainability (ICEES). p. 548–552, 2021.

KHADIJAH, A. M. et al. Utilização do sensor MPU6050 na análise de comportamento animal. In: INTERNATIONAL CONFERENCE ON SMART CITIES AND GREEN ICT SYSTEMS (SMARTGREENS), 13., 2025, Angers, França. Anais... Angers: SCITEPRESS – Science and Technology Publications, 2025. DOI: 10.5220/0013296600003663.

DAVCEV, D. et al. IoT agriculture system based on LoRaWAN. In: 14th IEEE International Workshop on Factory Communication Systems (WFCS). p. 1–4, 2018.

ANGRIAWAN, R.; ANUGRAHA, N. Sistem pelacak lokasi sapi com sistema de comunicação LoRa. Inspiration: Jurnal Teknologi Informasi dan Komunikasi, v. 9, n. 1, p. 33–39, 2019.

MAHAPUTRA, I. et al. Rancang bangun sistem keamanan sepeda motor com GPS tracker berbasis mikrokontroler dan aplikasi Android. Majalah Ilmiah Teknologi Elektro, v. 18, n. 3, p. 361–368, 2019.

PUTRA, A.; ROMAHADI, D. Sistem keamanan sepeda motor berbasis Internet of Things (IoT) dengan smartphone menggunakan NodeMCU. Jurnal Teknologi Terpadu, v. 9, n. 1, p. 77–87, 2021.

FEDOROV, D. et al. Using of measuring system MPU6050 for the determination of the angular velocities and linear accelerations. Automatics & Software Enginery, v. 11, n. 1, p. 75–80, 2015.

SCHULTHESS, L.; LONGCHAMP, F.; VOGT, C.; MAGNO, M. A LoRa-based and maintenance-free cattle monitoring system for alpine pastures and remote locations. In: 11th International Workshop on Energy Harvesting & Energy‑Neutral Sensing Systems, 12, 2023, Istambul, Turquia. Proceedings… New York: ACM, 2023. p. 44–50. DOI: 10.1145/3628353.3628549

PORTO, S. M. C.; BONFANTI, M.; MANCUSO, D.; CASCONE, G. Assessing accelerometer thresholds for cow behaviour detection in free stall barns: a statistical analysis. Acta IMEKO, v. 13, n. 1, p. 1–4, mar. 2024. DOI: 10.21014/actaimeko.v13i1.1682.

THANGAVEL, D.; MA, X.; VALERA, A.; TAN, H. X.; TAN, C. K. Y. Performance evaluation of MQTT and CoAP via a common middleware. IEEE Access, v. 6, p. 72338–72350, 2018. DOI: https://doi.org/10.1109/ACCESS.2018.2884903.
