# Título do Trabalho

## Introdução

A Internet das Coisas (IoT) é uma tecnologia  revolucionária que conecta inúmeros dispositivos por meio de redes de internet, permitindo a coleta e a troca de dados em tempo real (Lu et al., 2024). Esses “dispositivos” são, essencialmente, sensores e atuadores equipados com interface de rede sem fio, unidades de processamento e armazenamento. Essa tecnologia tem transformado diversos setores, especialmente o agronegócio, ao impulsionar inovações para melhorar a produtividade, a eficiência no uso de recursos e a sustentabilidade.

Esses dispositivos IoT frequentemente operam em ambientes com recursos limitados, formando o que se conhece como Rede de Sensores Sem Fio (WSN – Wireless Sensor Network). Os dados captados pelos sensores são coletados, roteados por meio da WSN e enviados à nuvem para análise posterior e eventual controle em malha fechada.

Na agricultura, os sistemas baseados em IoT monitoram aspectos cruciais como temperatura, umidade, umidade do solo e níveis de nutrientes, permitindo a otimização de recursos e o aumento da produtividade das lavouras (Chamara et al., 2022). Da mesma forma, na pecuária, dispositivos IoT viabilizam o monitoramento em tempo real do comportamento, da saúde e da localização dos animais, fornecendo dados valiosos para que os produtores aprimorem a gestão do rebanho e a produtividade das fazendas (McClune et al., 2014; Ladha et al., 2013).

A agricultura e a pecuária constituem pilares essenciais da economia brasileira, representando uma parte significativa do PIB nacional e responsável por uma grande parcela das exportações do país. O setor é responsável por milhões de empregos, tanto diretos quanto indiretos, e desempenha um papel fundamental na segurança alimentar mundial. No entanto, há muitos obstáculos a serem superados, como as consequências das mudanças climáticas, oscilações nos preços das commodities, falta de de mão de obra qualificada e acesso limitado a tecnologias avançadas, especialmente em áreas rurais e remotas.

Em especial, os pecuaristas brasileiros enfrentam desafios para monitorar de forma eficiente a saúde e o bem-estar dos animais, evitar fugas e furtos e administrar adequadamente os recursos. Tais desafios são ainda mais complexos em propriedades de grande extensão, comuns no Brasil, onde o pasto extenso dificulta o rastreamento e a proteção dos animais. A IoT surge como uma solução inovadora, permitindo o monitoramento contínuo das condições do rebanho, a detecção de anomalias comportamentais e o envio de alertas prévios sobre possíveis riscos à saúde (Farooq et al., 2022). Isso permite aos produtores agir de forma rápida e preventiva, melhorando o cuidado com os animais, reduzindo perdas e otimizando a gestão geral da fazenda.

Embora a adoção da IoT na pecuária brasileira ainda esteja em desenvolvimento, seu potencial para transformar práticas tradicionais está se tornando cada vez mais evidente. Com o apoio de políticas públicas, incentivos tecnológicos e iniciativas de pesquisa aplicada, os produtores brasileiros podem utilizar sistemas IoT para reduzir perdas, detectar doenças precocemente e promover uma produção mais eficiente, inteligente e sustentável.

O monitoramento dos movimentos e comportamentos dos animais fornece dados essenciais sobre saúde e bem-estar. Mudança nos padrões de atividade frequentemente sinalizam estresse, doenças ou lesões, possibilitando intervenções antecipadas (Atthari, 2017). Isso é especialmente relevante em regiões do interior do Brasil, onde os animais pastam livremente e estão mais suscetíveis a se perderem ou serem furtados. Soluções de rastreamento baseadas em IoT contribuem para reduzir esses riscos, aumentar a segurança no campo e reforçar a estabilidade econômica das comunidades agropecuárias.

No entanto, para uma implantação bem-sucedida dessas redes, ainda há desafios técnicos significativos a serem superados: condições ambientais adversas, alcance de comunicação, qualidade de serviço (QoS), custo de implementação e consumo energético (vida útil da bateria).

Nesse contexto, o protocolo LoRaWAN (Long Range Wide Area Network) tem se destacado como uma solução viável para aplicações de IoT em áreas rurais e remotas, devido à sua grande cobertura, baixo consumo de energia e custo acessível. Estudos recentes monstraram a eficácia do LoRa em resolver problemas de conectividade em regiões com infraestrutura limitada. Joshitha et al. (2021) estudaram um sistema baseado em LoRa para transmissão de dados a longa distância, destacando sua capacidade de operar em locais sem acesso a redes de comunicação convensionais. O mesmo estudo introduziu um dispositivo de rastreamento de longo alcance utilizando LoRa, garantindo autonomia de redes de terceiros e redução de custos operacionais. Os resultados confirmam a adequação do LoRa para o rastreamento animal, com comunicação confiável mesmo em ambientes com poucos recursos.

Além disso, o LoRa utiliza modulação CSS (chirp spread spectrum) e opera na faixa ISM sub-GHz, oferecendo boa penetração de sinal e resistência a interferências — características ideais para áreas com vegetação densa ou relevo acidentado, comuns no interior brasileiro.

O principal dispositivo de monitoramento de gado utilizado nesta pesquisa foi o TTGO T-Beam, um microcontrolador que integra LoRa, GPS, Wi-Fi e o sensor MPU6050, tornando-o ideal para regiões remotas com conectividade limitada e desafios energéticos. O módulo GPS permite o rastreamento preciso da localização, essencial para a segurança dos animais e redução de riscos durante o pasto livre. O Wi-Fi possibilita o envio de dados para plataformas em nuvem, facilitando o acesso remoto às informações em tempo real. Já o sensor MPU6050, que mede aceleração e velocidade angular, fornece dados detalhados sobre movimentos e orientação dos animais, possibilitando a identificação de comportamentos anormais que possam indicar sofrimento, doenças ou lesões (Khadijah et et al., 2025).

Com essa combinação de tecnologias, o Brasil pode contar com uma solução escalável, eficiente e de baixo custo para o gerenciamento pecuário. No cenário rural brasileiro, o LoRaWAN se destaca por sua capacidade de comunicação de longo alcance, baixo consumo de energia e uso de frequências não licenciadas, tornando-se ideal para aplicações como o rastreamento de gado em extensas regiões (Davcev et al., 2018).

O uso do TTGO T-Beam neste estudo tem como objetivo abordar os desafios específicos da pecuária brasileira, ao oferecer um sistema integrado de monitoramento em tempo real, rastreamento por GPS e análise de comportamento animal. Essa tecnologia representa uma ferramenta eficaz para aprimorar a gestão agropecuária, promovendo melhor cuidado com os animais, redução de perdas e aumento da resiliência econômica para enfrentar os desafios contemporâneos do setor agrícola nacional.


## Revisão da literatura

A Internet das Coisas (IoT) tem se destacado como uma solução tecnológica promissora para a transformação de setores tradicionais, como a agricultura e a pecuária, permitindo a automação de processos e a coleta de dados em tempo real. Essa transformação é possível graças ao avanço de sensores inteligentes, microcontroladores com conectividade sem fio e protocolos de comunicação de baixo consumo energético, como o LoRaWAN.

Vários estudos exploram o uso do LoRaWAN em ambientes remotos para monitoramento de condições ambientais e localização de ativos. Joshitha et al. (2021) propuseram um sistema de rastreamento animal com base em LoRa, destacando sua eficiência em áreas sem infraestrutura de comunicação convencional, o que reforça a viabilidade da tecnologia em ambientes rurais brasileiros. Davcev et al. (2018) também demonstraram que o LoRaWAN oferece um equilíbrio ideal entre longo alcance, baixo consumo de energia e operação em bandas não licenciadas — fatores críticos para o monitoramento pecuário em grandes propriedades.

No contexto específico da pecuária, Farooq et al. (2022) destacaram a importância de sistemas de monitoramento comportamental para a identificação precoce de doenças ou situações de estresse, a partir de dados coletados por sensores de movimento. O trabalho de Atthari (2017) complementa essa perspectiva ao mostrar como variações na atividade física de animais podem indicar anomalias comportamentais, sendo uma alternativa promissora para o manejo preventivo do rebanho.

Com relação ao uso de hardware, a placa TTGO T-Beam, baseada no microcontrolador ESP32 e equipada com GPS e LoRa, tem se mostrado uma escolha robusta para aplicações em IoT rural. Angriawan e Anugraha (2019) exploraram o uso do GPS integrado ao TTGO T-Beam para rastreamento em tempo real, enquanto Fedorov et al. (2015) utilizaram o acelerômetro MPU6050 para detectar padrões de movimento em aplicações com sensores inerciais. Essa combinação de sensores também foi destacada por Mahaputra et al. (2019) e Putra e Romahadi (2021), que demonstraram a integração de múltiplas fontes de dados em sistemas embarcados de baixo custo.

Com base nessas referências, o presente trabalho desenvolveu um protótipo funcional para o monitoramento de gado em tempo real, utilizando um TTGO T-Beam alimentado por pilha, integrado ao sensor inercial MPU6050 e ao módulo GPS. O firmware foi construído com base na biblioteca LMIC-node, amplamente utilizada para aplicações com LoRaWAN. Após o pareamento com o The Things Network (TTN), utilizando as chaves DevEUI, AppEUI e AppKey (com o DevEUI obtido a partir do MAC do ESP32), foi possível estabelecer a comunicação com o backend da rede.

A lógica do sistema foi implementada para enviar as coordenadas GPS a cada 30 segundos, enquanto os dados do acelerômetro são enviados apenas quando há movimentação superior a 1.55g, simulando comportamentos atípicos em bovinos, como agitação repentina, quedas ou tentativa de fuga. Os dados recebidos pelo TTN foram encaminhados via protocolo MQTT para um ambiente Node-RED, onde foram processados e visualizados em um dashboard. A visualização incluiu gráficos com dados do acelerômetro e um mapa interativo com as posições obtidas pelo GPS (utilizando o módulo worldmap).

Comparando-se com estudos anteriores, nota-se que a maioria dos protótipos em aplicações similares utiliza intervalos de transmissão maiores (ex: 10–15 minutos), focando na economia de energia e na durabilidade das baterias, como em Schulthess et al. (2024). Em contrapartida, este projeto priorizou a alta frequência de dados e a reatividade a eventos, embora ainda não tenha sido realizada uma análise da duração da bateria — aspecto previsto para testes futuros. Além disso, poucos trabalhos integram todos esses elementos em um único sistema: rastreabilidade, detecção de movimento anômalo e visualização em tempo real, de forma acessível e adaptável ao contexto brasileiro.

Portanto, a proposta aqui desenvolvida se diferencia ao combinar hardware de baixo custo, sensores estratégicos, comunicação LoRaWAN, processamento local e visualização remota, oferecendo uma solução escalável e aplicável à realidade de produtores rurais no Brasil. Ao alinhar os aprendizados da literatura internacional com a experimentação prática em território nacional, o projeto avança no desenvolvimento de ferramentas digitais acessíveis para o agronegócio.
[Deve-se citar trabalhos relacionados ao seu problema ou da área que estão mais próximos (para casos específicos); o que estiver mais próximo do seu trabalho. Os trabalhos são citados para destacar o que já foi feito de importante e resultados obtidos sobre o problema em questão. São trabalhos que complementam ou que são utilizados para fins de comparação. Citar sempre a referência completa se estiver relacionado diretamente com o trabalho, explicar o objetivo e detalhes gerais enfatizando as diferenças com o seu trabalho Indicar os resultados que serão utilizados para comparação com o seu trabalho Destacar os pontos positivos e negativos do trabalho. Citam-se os negativos por que no seu trabalho seriam positivos.]

## Materiais e Métodos

Na seção **"Materiais e Métodos"** (ou "Metodologia", dependendo do modelo), você deve descrever **de forma clara e objetiva** como o seu projeto foi realizado na prática, quais **componentes foram utilizados**, **como foram integrados**, **quais bibliotecas ou plataformas foram usadas**, e **como os testes foram conduzidos**.

Essa parte deve permitir que outra pessoa, com conhecimento técnico, **possa replicar o seu projeto** com base apenas no que você escreveu.

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

Inicialmente, foi realizado o teste isolado dos módulos **GPS** e **MPU6050** conectados à placa TTGO T-Beam, com o objetivo de garantir o correto funcionamento de cada componente. O sensor MPU6050 foi conectado via protocolo I²C aos pinos do ESP32, e o GPS utilizou a porta UART padrão da placa.


### **2.2 Programação do Dispositivo**

A programação foi realizada na **IDE Arduino**, com base na biblioteca **LMIC-node**, amplamente utilizada para dispositivos LoRaWAN. Para a autenticação na rede TTN, foram obtidas as chaves:

* **DevEUI** (derivado do MAC address do ESP32),
* **AppEUI** e
* **AppKey** (geradas via TTN Console).

O código foi adaptado para:

* Enviar dados de **localização GPS a cada 30 segundos**.
* Monitorar o acelerômetro em tempo real, enviando um pacote somente se a aceleração em qualquer eixo excedesse **1.55g**, simulando um comportamento incomum no rebanho (queda, corrida, tentativa de fuga etc.).

As mensagens foram transmitidas em **uplink** via LoRaWAN com codificação personalizada (payload com latitude, longitude e valor de aceleração).

### **2.3 Backend e Visualização**

Os dados recebidos pela TTN foram encaminhados para o **Node-RED** via protocolo **MQTT**, utilizando as credenciais fornecidas pelo TTN MQTT Bridge.

No Node-RED, foi desenvolvido um **dashboard interativo**, composto por:

* **Gráficos de aceleração** para cada eixo (X, Y, Z) em tempo real.
* Um **mapa geográfico (módulo Worldmap)** que exibe a posição atual dos animais com base nas coordenadas GPS.


### **2.4 Testes Realizados**

O sistema foi testado em ambiente controlado, simulando o deslocamento do dispositivo e movimentações bruscas para verificar a eficácia da detecção por aceleração. Os testes focaram nos seguintes pontos:

* Estabilidade da comunicação LoRaWAN com a TTN.
* Precisão das leituras do GPS e acelerômetro.
* Correção e frequência dos dados enviados.
* Funcionamento do MQTT e atualização em tempo real do painel no Node-RED.

**Observação:** até o momento, **não foi realizada a análise do consumo energético** ou da **autonomia da bateria**. Esses testes estão previstos para fases posteriores do projeto.


## Resultados

[Incluir e comentar sobre: Diagrama final do protótipo, descrição dos testes realizados, apresentação e análise dos resultados dos testes realizados, fotos, diagramas, tabelas comparativas.]

## Conclusão

### Dificuldades encontradas

[Apresente as dificuldades encontradas durante ao longo do desenvolvimento do seu trabalho.]

### Sugestões para trabalhos futuros

[Apresente suas sugestões de trabalhos futuros.]

## Referências

[Inserir todas as referências utilizadas. Sugere-se o uso do site referenciabibliografica.net para a geração das referências. Veja o exemplo abaixo.]
