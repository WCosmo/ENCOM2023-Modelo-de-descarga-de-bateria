# Modelo de descarga de bateria para dispositivo IoT

Projeto destinado à participação no ENCOM 2023.

Objetivo: Extrair dados provenientes de um cenário proposto de rede IoT, que consiste dos valores de uma bateria recarregável acoplado ao end-node, que pode estar conectado a diferentes sensores que irão gerar diferentes consumos de energia. A partir desses dados, treinar modelos RNA para estimar o tempo a partir de um segmento observado até o ponto de descarga.

Todas as análises realizadas, modelos implementados e resultados obtidos estão disponíveis no arquivo `ENCOM_2023_-_Modelo_de_descarga.ipynb`.

Informações da publicação:
- Título: Modelo de Descarga para Dispositivo IoT Usando Redes Neurais Artificiais
- Autores: W. A. C. Macedo, T. F. Balbinot, S. B. Santos, W. L. Louzada, V. A. Chaves, E. F. F. de L. Santos, R. T. J. Ramos, F. J. B. Barros
- Disponível em: https://www.iecom.org.br/encom2023/autores.html#anais

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

Parâmetros da trasmissão LoRa:

- Frequência: 915 MHz
- Fator de Espalhamento (SF): 12 
- Potencia de transmissão: 22 dBm
- Tamanho do pacote: 59 quilobytes
- Tempo entre transmissões: 60 segundos

Topologia da implementação da rede IoT:

![Alt text](ilustracoes/diagrama_iot.drawio.png?raw=true "Diagrama da rede IoT proposta")

End-node utilizado:

![Alt text](ilustracoes/end-node.jpg?raw=true "End-node")

Gateway:

![Alt text](ilustracoes/gateway.jpg?raw=true "Gateway")


## Base de dados

Os dados utilizados são provenientes da API Thingspeak, e encontram-se no diretório `base_de_dados`, consistindo de informações dos sensores coletados pelo end-node ao longo do processo de descarga, incluindo o próprio valor de tensão da bateria acoplada ao mesmo. No presente trabalho analisou-se somente a porção dos dados correspondente à referida tensão da bateria, que resultam nas seguintes curvas de descarga:

![Alt text](ilustracoes/dcurves2.png?raw=true "Curvas de descarga")

A forma como os dados foram extraídos e visualizados pode ser consultada em `ENCOM_2023_-_Modelo_de_descarga.ipynb`.


## Datasheets/Referência técnica

- RAK5005-O: https://docs.rakwireless.com/Product-Categories/WisBlock/RAK5005-O/Datasheet/
- RAK4630: https://docs.rakwireless.com/Product-Categories/WisDuo/RAK4630-Module/Datasheet/
- RAK5811: https://docs.rakwireless.com/Product-Categories/WisBlock/RAK5811/Datasheet/
- T-Beam: https://doc.riot-os.org/group__boards__esp32__ttgo-t-beam.html
- Bateria: https://icecat.biz/bn/p/vendorName/mpn/desc-32754413.html
- Termopar: https://www.analog.com/media/en/technical-documentation/data-sheets/DS18B20.pdf
- Sensor de Tensão (referência): https://www.circuitschools.com/arduino-voltage-sensor-which-measures-up-to-25v-dc/
