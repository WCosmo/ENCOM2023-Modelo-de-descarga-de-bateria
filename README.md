# Modelo de descarga de bateria para dispositivo IoT

Projeto destinado à participação no ENCOM 2023.

Objetivo: Extrair dados provenientes de um cenário proposto de rede IoT, que consiste dos valores de uma bateria recarregável acoplado ao end-node, que pode estar conectado a diferentes sensores que irão gerar diferentes consumos de energia. A partir desses dados, treinar modelos RNA para estimar o tempo a partir de um segmento observado até o ponto de descarga.


## Componentes da rede IoT

End-node:
- RAK5005-O
- RAK4630
- RAK5811
- Bateria recarregável
- Termopar
- Sensor de tensão

Gateway:
- TTGO T-Beam ESP32
- Fonte DC genérica (5V, 1A)


## Implementação do cenário proposto

Topologia da implementação da rede IoT:

![Alt text](ilustracoes/diagrama_iot.drawio.png?raw=true "Diagrama da rede IoT proposta")

End-node utilizado:

![Alt text](ilustracoes/diagrama_iot.drawio.png?raw=true "End-node")

Gateway:

![Alt text](ilustracoes/diagrama_iot.drawio.png?raw=true "Gateway")

## Datasheets/Referência técnica

- RAK5005-O: https://docs.rakwireless.com/Product-Categories/WisBlock/RAK5005-O/Datasheet/
- RAK4630: https://docs.rakwireless.com/Product-Categories/WisDuo/RAK4630-Module/Datasheet/
- RAK5811: https://docs.rakwireless.com/Product-Categories/WisBlock/RAK5811/Datasheet/
- T-Beam: https://doc.riot-os.org/group__boards__esp32__ttgo-t-beam.html
- Bateria: https://icecat.biz/bn/p/vendorName/mpn/desc-32754413.html
- Termopar: https://www.analog.com/media/en/technical-documentation/data-sheets/DS18B20.pdf
- Sensor de Tensão (referência): https://www.circuitschools.com/arduino-voltage-sensor-which-measures-up-to-25v-dc/
