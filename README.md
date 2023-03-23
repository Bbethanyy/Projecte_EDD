View this project on [CADLAB.io](https://cadlab.io/project/26669). 

# Projecte EDD: Disseny eletrònic d'un maleter
**Membres del grup:** Jan Castillo, Bethany Quintero
----------------------------------------------------
## Objectiu
Dissenyar un sistema electrònic capaç d'obrir un maleter d'un automòbil utilitzant un sensor de proximitat i que pogui escalfar el vidre que l'acompanya.

## Requisits/Especificacions
- Microcontrolador 
- Dos reguladors de tensions: un pel microcontrolador i l'altre per al sensor
- Sensor de proximitat per detectar un gest amb el peu 
- Resistèncias calefactores per escalar el vidre
- Driver per controlar el Brushless DC motor per obrir i tancar el maleter
- Resistor shunt per indicar el final de la carerra
- Connectors

## Diagrama de blocs
![image](https://user-images.githubusercontent.com/128420038/227268940-f2d4ecee-97e2-4adf-a1d6-e2de319b6b33.png)


## Components
| Ref. | Descripció| Datasheet |
| ------ | -----------------| ------------------|
|PIC18F258|Microcontrolador|[Datasheet](https://www.mouser.es/datasheet/2/268/41159e-30206.pdf)|
|LM1117|Regulador de tensió|[Datasheet](https://www.ti.com/lit/ds/snos412q/snos412q.pdf?ts=1679503528555&ref_url=https%253A%252F%252Fwww.ti.com%252F)|
|FDC2212|Sensor de proximitat|[Datasheet](https://www.ti.com/lit/ds/symlink/fdc2212-q1.pdf?ts=1679569328592&ref_url=https%253A%252F%252Fwww.ti.com%252Fproduct%252FFDC2212-Q1)|
|MCP2551|Transceiver|[Datasheet](https://www.mouser.es/datasheet/2/268/20001667G-1115479.pdf)|
|ECS-80-20-20A-TR|Oscillador|[Datasheet](https://ecsxtal.com/store/pdf/csm-8r.pdf)|
|DRV8316C-Q1|Driver|[Datasheet](https://www.ti.com/lit/ds/symlink/drv8316-q1.pdf?HQS=dis-mous-null-mousermode-dsf-pf-null-wwe&ts=1679570127047&ref_url=https%253A%252F%252Fwww.mouser.es%252F)|
|PSR100|Shunt resistor|[Datasheet](https://fscdn.rohm.com/en/products/databook/datasheet/passive/resistor/chip_resistor/psr-e.pdf)|
|INA420|OpAmp|[Datasheet](https://www.ti.com/lit/ds/symlink/ina240.pdf?ts=1679555341146&ref_url=https%253A%252F%252Fwww.ti.com.cn%252Fproduct%252Fcn%252FINA240)|
|ADW1112W|Relé|[Datasheet](https://www.datasheetq.com/datasheet-download/853198/1/Panasonic/ADW1112W)|
|BLDC-48|Brushless motor|[Datasheet](https://www.farnell.com/datasheets/526541.pdf)|
|GBR-612|Heating Element|[Datasheet](https://www.tme.eu/Document/745dece1e8a1927996aa7af3a5cfc3a0/GBR-612_ENG.pdf)|
|BC 817/25|BJT|[Datasheet](https://pdf1.alldatasheet.com/datasheet-pdf/view/16111/PHILIPS/BC817-25.html)|

## Historial de canvis
|Data| Autor|Descripció|
| ------ | -----------------| ------------------|
|23/03/23|Bethany Quintero i Jan Castillo|Segona versió diagrama de blocs i selecció de components|
|23/03/23|Bethany Quintero i Jan Castillo|Correcció diagrama de blocs i afegit el BJT a components|
