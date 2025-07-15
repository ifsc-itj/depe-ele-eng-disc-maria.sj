# Título do Trabalho

## Introdução

A Internet das Coisas (IoT) é uma tecnologia  revolucionária que conecta inúmeros dispositivos por meio de redes de internet, permitindo a coleta e a troca de dados em tempo real (Lu et al., 2024). Esses “dispositivos” são, essencialmente, sensores e atuadores equipados com interface de rede sem fio, unidades de processamento e armazenamento. Essa tecnologia tem transformado diversos setores, especialmente o agronegócio, ao impulsionar inovações para melhorar a produtividade, a eficiência no uso de recursos e a sustentabilidade.

Esses dispositivos IoT frequentemente operam em ambientes com recursos limitados, formando o que se conhece como Rede de Sensores Sem Fio (WSN – Wireless Sensor Network). Os dados captados pelos sensores são coletados, roteados por meio da WSN e enviados à nuvem para análise posterior e eventual controle em malha fechada.

Na agricultura, os sistemas baseados em IoT monitoram aspectos cruciais como temperatura, umidade, umidade do solo e níveis de nutrientes, permitindo a otimização de recursos e o aumento da produtividade das lavouras (Chamara et al., 2022). Da mesma forma, na pecuária, dispositivos IoT viabilizam o monitoramento em tempo real do comportamento, da saúde e da localização dos animais, fornecendo dados valiosos para que os produtores aprimorem a gestão do rebanho e a produtividade das fazendas (McClune et al., 2014; Ladha et al., 2013).

A agricultura e a pecuária constituem pilares essenciais da economia brasileira, representando uma parte significativa do PIB nacional e responsável por uma grande parcela das exportações do país. O setor é responsável por milhões de empregos, tanto diretos quanto indiretos, e desempenha um papel fundamental na segurança alimentar mundial. No entanto, há muitos obstáculos a serem superados, como as consequências das mudanças climáticas, oscilações nos preços das commodities, falta de de mão de obra qualificada e acesso limitado a tecnologias avançadas, especialmente em áreas rurais e remotas.

Em especial, os pecuaristas brasileiros enfrentam desafios para monitorar de forma eficiente a saúde e o bem-estar dos animais, evitar fugas e furtos e administrar adequadamente os recursos. Tais desafios são ainda mais complexos em propriedades de grande extensão, comuns no Brasil, onde o pasto extenso dificulta o rastreamento e a proteção dos animais. A IoT surge como uma solução inovadora, permitindo o monitoramento contínuo das condições do rebanho, a detecção de anomalias comportamentais e o envio de alertas prévios sobre possíveis riscos à saúde (Farooq et al., 2022). Isso permite aos produtores agir de forma rápida e preventiva, melhorando o cuidado com os animais, reduzindo perdas e otimizando a gestão geral da fazenda.

Embora a adoção da IoT na pecuária brasileira ainda esteja em desenvolvimento, seu potencial para transformar práticas tradicionais está se tornando cada vez mais evidente. Com o apoio de políticas públicas, incentivos tecnológicos e iniciativas de pesquisa aplicada, os produtores brasileiros podem utilizar sistemas IoT para reduzir perdas, detectar doenças precocemente e promover uma produção mais eficiente, inteligente e sustentável.

O monitoramento dos movimentos e comportamentos dos animais fornece dados essenciais sobre saúde e bem-estar. Mudança nos padrões de atividade frequentemente sinalizam estresse, doenças ou lesões, possibilitando intervenções antecipadas (Atthari, 2017). Isso é especialmente relevante em regiões do interior do Brasil, onde os animais pastam livremente e estão mais suscetíveis a se perderem ou serem furtados. Soluções de rastreamento baseadas em IoT contribuem para reduzir esses riscos, aumentar a segurança no campo e reforçar a estabilidade econômica das comunidades agropecuárias. A imagem abaixo mostra uma visão geral de um sistema com vários rastreadores de gado conectados ao servidor back-end por meio de um gateway LoRaWAN.
Os parâmetros de atividade coletados de cada dispositivo ativo são armazenados em um banco de dados SQL. Essa representação visual demonstra ideias futuras ao projeto atual.

<img width="759" height="409" alt="image" src="https://github.com/user-attachments/assets/3767840f-8618-41e3-9857-0280808975ee" />


Para uma implantação bem-sucedida dessas redes, ainda há desafios técnicos significativos a serem superados: condições ambientais adversas, alcance de comunicação, qualidade de serviço (QoS), custo de implementação e consumo energético (vida útil da bateria).

Nesse contexto, o protocolo LoRaWAN (Long Range Wide Area Network) tem se destacado como uma solução viável para aplicações de IoT em áreas rurais e remotas, devido à sua grande cobertura, baixo consumo de energia e custo acessível. Estudos recentes monstraram a eficácia do LoRa em resolver problemas de conectividade em regiões com infraestrutura limitada. Joshitha et al. (2021) estudaram um sistema baseado em LoRa para transmissão de dados a longa distância, destacando sua capacidade de operar em locais sem acesso a redes de comunicação convensionais. O mesmo estudo introduziu um dispositivo de rastreamento de longo alcance utilizando LoRa, garantindo autonomia de redes de terceiros e redução de custos operacionais. Os resultados confirmam a adequação do LoRa para o rastreamento animal, com comunicação confiável mesmo em ambientes com poucos recursos.

Além disso, o LoRa utiliza modulação CSS (chirp spread spectrum) e opera na faixa ISM sub-GHz, oferecendo boa penetração de sinal e resistência a interferências — características ideais para áreas com vegetação densa ou relevo acidentado, comuns no interior brasileiro.

O principal dispositivo de monitoramento de gado utilizado nesta pesquisa foi o TTGO T-Beam, um microcontrolador que integra LoRa, GPS, Wi-Fi e o sensor MPU6050, tornando-o ideal para regiões remotas com conectividade limitada e desafios energéticos. O módulo GPS permite o rastreamento preciso da localização, essencial para a segurança dos animais e redução de riscos durante o pasto livre. O Wi-Fi possibilita o envio de dados para plataformas em nuvem, facilitando o acesso remoto às informações em tempo real. Já o sensor MPU6050, que mede aceleração e velocidade angular, fornece dados detalhados sobre movimentos e orientação dos animais, possibilitando a identificação de comportamentos anormais que possam indicar sofrimento, doenças ou lesões (Khadijah et et al., 2025).

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

Após os testes individuais com o módulo GPS embarcado na placa TTGO T-Beam, foi realizado a integração do acelerômetro MPU6050 ao sistema. O objetivo deste teste foi verificar a leitura simultânea de dados de localização (GPS) e aceleração (MPU6050), assegurando que ambos os sensores operam corretamente em conjunto, utilizando as interfaces UART e I2C da placa TTGO.

O MPU6050 foi o sensor escolhido para o presente trabalho. Trata-se de uma Unidade de Medida Inercial (IMU) que integra sensores de aceleração, nos eixos X, Y e Z, e de rotação angular (giroscópio) nos mesmos eixos. Além disso, possui uma interface de comunicação simples, utilizando o protocolo I2C, o que facilita sua integração com controladores, sendo utilizado neste caso o ESP32. A escolha desse sensor se deu por suas diversas vantagens, como o fato de ser compacto, oferecendo em um único chip a leitura de aceleração e rotação. Ele também apresenta alta precisão, o que o torna confiável para aplicações que exigem medições consistentes. Seu excelente custo-benefício o torna ideal para prototipagem, e seu baixo consumo de energia o torna adequado para sistemas embarcados e dispositivos móveis (Fedorov et al., 2015).

A comunicação com o módulo GPS foi realizada via UART1, utilizando os pinos 34 (RX) e 12 (TX). Já o acelerômetro MPU6050 foi conectado ao barramento I2C padrão (pinos 21 - SDA e 22 - SCL). O código utilizado baseou-se novamente na bibliotecas TinyGPS++ com adição da MPU6050, que oferecem alto nível de abstração para facilitar a leitura de dados dos respectivos sensores. Além disso, ele foi estruturado para ler continuamente os dados do GPS, verificando a disponibilidade de novas leituras, obter os valores brutos de aceleração do MPU6050 e converter os valores brutos em g (gravidade). 

<img width="696" height="552" alt="image" src="https://github.com/user-attachments/assets/4624dd4a-6baf-42da-a6d3-710d82916f03" />

Figura 2: Protótipo do Hardware IoT.


Para a identificação de comportamentos anômalos em bovinos, é fundamental compreender os padrões normais de aceleração durante as atividades rotineiras dos animais. Estudos indicam que, durante a locomoção em piso rígido, como concreto, as pernas das vacas apresentam uma aceleração média na faixa de 1,62 a 1,72 g, enquanto em pisos mais macios, esse valor tende a ser levemente inferior. Essas faixas representam padrões típicos de caminhada e movimentação tranquila (Chapinal et al., 2011). O acelerômetros, nesse caso, pode ser utilizados para detectar desvios desses valores, que podem indicar comportamentos fora do normal, como mancar, agitação, brigas, fugas ou até mesmo tentativas de levantar-se de maneira brusca . 

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
#define DEVICEID "meu_dispositivo"
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

Segundo estudo de Thangavel et al. (2018), o MQTT se destaca por utilizar um modelo de publicação e assinatura (publish/subscribe) baseado em conexões TCP persistentes, o que proporciona menor consumo de banda, baixa latência e eficiência energética significativamente superior ao modelo request/response do HTTP. O artigo também ressalta que o MQTT permite a configuração de níveis de Qualidade de Serviço (QoS), essenciais para garantir a entrega confiável das mensagens — um aspecto importante em aplicações que monitoram comportamentos críticos de animais.

Além disso, o cabeçalho compacto do MQTT e seu baixo overhead tornam o protocolo ideal para dispositivos com recursos limitados, como os empregados neste estudo, baseados no microcontrolador TTGO T-Beam com sensores embarcados. A integração com o The Things Network (TTN) foi realizada via TTN MQTT bridge, o que exigiu a geração de uma chave de autenticação (API Key) diretamente no console da plataforma e sua posterior configuração no fluxo de dados do Node-RED, ferramenta responsável pela visualização dos dados em tempo real em um dashboard interativo. Os dados recebidos pela TTN foram encaminhados utilizando as credenciais fornecidas pelo TTN MQTT Bridge conforme mostra a tabela abaixo: 

| Parâmetro       | Valor                                                       |
| --------------- | ----------------------------------------------------------- |
| **MQTT Host**   | `nam1.cloud.thethings.network`                              |
| **Porta**       | `8883` (SSL/TLS)                                            |
| **Username**    | `gps-agro@ttn`                                              |
| **Password**    | A **chave gerada** dessa API key                            |
| **Tópico MQTT** | `v3/gps-agro@ttn/devices/+/up`                              |

A adoção do MQTT, portanto, alinha-se às melhores práticas para comunicação em sistemas IoT distribuídos, conforme demonstrado pela literatura, assegurando um balanceamento adequado entre confiabilidade, leveza e escalabilidade da solução proposta.

A arquitetura do backend foi composta por três elementos principais: Broker MQTT (TTN MQTT Bridge) responsável por receber os pacotes uplink transmitidos pela rede LoRaWAN e disponibilizá-los para assinantes MQTT; Node-RED, um ambiente de programação visual usado para processar os dados em tempo real, convertê-los para formatos legíveis e alimentar os dashboards interativos; Dashboard Web construída no próprio Node-RED, utilizando widgets de gráfico e mapa interativo (worldmap) para exibir a trajetória dos animais e os dados de aceleração.

Essa abordagem permitiu uma visualização eficiente dos eventos capturados pelo dispositivo, como movimentos anômalos e localização GPS, com mínimo atraso, sem a necessidade de chamadas HTTP periódicas (polling), que aumentariam o tráfego de rede e o consumo de energia.

## Resultados

[Incluir e comentar sobre: Diagrama final do protótipo, descrição dos testes realizados, apresentação e análise dos resultados dos testes realizados, fotos, diagramas, tabelas comparativas.]

## Conclusão

### Dificuldades encontradas

[Apresente as dificuldades encontradas durante ao longo do desenvolvimento do seu trabalho.]

### Sugestões para trabalhos futuros

[Apresente suas sugestões de trabalhos futuros.]

## Referências

[Inserir todas as referências utilizadas. Sugere-se o uso do site referenciabibliografica.net para a geração das referências. Veja o exemplo abaixo.]
