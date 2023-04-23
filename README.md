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
![image](https://user-images.githubusercontent.com/128420038/233825906-a12339f0-72f9-4510-8a85-f58f14335250.png)









## Components
| Ref. | Descripció| Datasheet |
| ------ | -----------------| ------------------|
|PIC18F258|Microcontrolador|[Datasheet](https://www.mouser.es/datasheet/2/268/41159e-30206.pdf)|
|LM1117|Regulador de tensió|[Datasheet](https://www.ti.com/lit/ds/snos412q/snos412q.pdf?ts=1679503528555&ref_url=https%253A%252F%252Fwww.ti.com%252F)|
|FDC2212|Sensor de proximitat|[Datasheet](https://www.ti.com/lit/ds/symlink/fdc2212-q1.pdf?ts=1679569328592&ref_url=https%253A%252F%252Fwww.ti.com%252Fproduct%252FFDC2212-Q1)|
|MCP2551|Transceiver|[Datasheet](https://www.mouser.es/datasheet/2/268/20001667G-1115479.pdf)|
|ECS-80-20-20A-TR|Oscillador|[Datasheet](https://ecsxtal.com/store/pdf/csm-8r.pdf)|
|PSR100|Shunt resistor|[Datasheet](https://fscdn.rohm.com/en/products/databook/datasheet/passive/resistor/chip_resistor/psr-e.pdf)|
|AD8616|OpAmp|[Datasheet](https://www.analog.com/media/en/technical-documentation/data-sheets/AD8615_8616_8618.pdf)|
|ADW1112W|Relé|[Datasheet](https://www.datasheetq.com/datasheet-download/853198/1/Panasonic/ADW1112W)|
|1393280-5|Relé micro K|[Datasheet](https://www.te.com/commerce/DocumentDelivery/DDEController?Action=srchrtrv&DocNm=V23086X0000A001&DocType=Data+Sheet&DocLang=English&DocFormat=pdf&PartCntxt=1393280-5)|
|BLDC-48|Brushless motor|[Datasheet](https://www.farnell.com/datasheets/526541.pdf)|
|GBR-612|Heating Element|[Datasheet](https://www.tme.eu/Document/745dece1e8a1927996aa7af3a5cfc3a0/GBR-612_ENG.pdf)|
|BC 817/25|BJT|[Datasheet](https://pdf1.alldatasheet.com/datasheet-pdf/view/16111/PHILIPS/BC817-25.html)|
|TCA39306|Level Shifter|[Datasheet](https://www.ti.com/lit/ds/symlink/tca39306.pdf?ts=1680614676613&ref_url=https%253A%252F%252Fwww.google.com%252F)|


## Simulacions
Anem a veure diferents simulacions que hem pogut fer amb LTSPICE per comprovar el correcte funcionament del projecte.
### Reguladors de tensió
El primer a simular ha estat els reguladors de tensió a utilitzar, una de les més senzilles:
![image](https://user-images.githubusercontent.com/128420038/227760246-3e0efe11-65da-41eb-b58c-1ed1ec8b9907.png)

I podem comprovar que els potencials als nodes són els dessitjats:

![image](https://user-images.githubusercontent.com/128420038/227760309-8d6813f3-3f38-48f9-ae12-8ec50400e39f.png)

### Relé
Malauradament LTSPICE no té relés. Hem utilitzat un interruptor per tensió i hem aproximat alguns dels seus paràmetres al nostre relé, per a fer una simulació aproximada:

![image](https://user-images.githubusercontent.com/128420038/227760389-f3919231-660b-4d24-bc1f-4cc55b69f14e.png)

I així, podem comprovar que passa la tensió dessitjada:

![image](https://user-images.githubusercontent.com/128420038/227760407-5c292cef-1b9b-4fa3-b518-837812bd249a.png)

### Control de corrent
L'últim sistema que podem simular és el sistema d'amplificadors operacionals que permetran regular el corrent del motor i, per tant, el final de carrera d'aquest:

![image](https://user-images.githubusercontent.com/128420038/229271632-b0513e5e-26a8-4b4c-8614-7f9909abfa8c.png)



Aleshores es pot comprovar que si la font és de 1.33 A (funcionament normal), la sortida és el valor baix de saturació:

![image](https://user-images.githubusercontent.com/128420038/229271663-7c15f7c8-27c9-4324-a3b2-15aeda58307d.png)


I en canvi, si la font és de 1.95 A (realment es retallaria abans), la sortida serà el valor alt de tensió:

![image](https://user-images.githubusercontent.com/128420038/229271793-8ee0b926-4a4c-4e1a-be12-ad74cd024eb2.png)



## Esquemàtic
![image](https://user-images.githubusercontent.com/128420038/233825973-53deaa02-17bd-4681-b001-617c45e16158.png)


## Layout
![image](https://user-images.githubusercontent.com/128420038/233826438-b03afc99-19bf-4384-b9ad-912167408e00.png)


## 3D Model
![image](https://user-images.githubusercontent.com/128420038/233826459-a53e86c0-dd47-47e7-90e2-bee8354d0589.png)




## Historial de canvis
|Data| Autor/a |Descripció|
| ------ | -----------------| ------------------|
|23/03/23|Bethany Quintero i Jan Castillo|Segona versió diagrama de blocs i selecció de components|
|23/03/23|Bethany Quintero i Jan Castillo|Correcció diagrama de blocs i afegit el BJT a components|
|26/03/23|Jan Castillo|Actualització diagrama de blocs i components (OPAMP). Afegides les simulacions i els resultats|
|27/03/23|Jan Castillo|Actualització de components (driver canviat per relés) i, per tant, actualitzat també el diagrama de blocs. Actualització de la simulació del final de carrera|
|27/03/23| Bethany Quintero | Primera versió de l'esquemàtic|
|28/03/23| Bethany Quintero | Correcció del driver i afegits els valors dels components que faltaven a l'esquemàtic|
|1/04/23| Jan Castillo |Afegit Level Shifter a components. Actualització del diagrama de blocs i canviat el valor Vref de la simulació del final de carrera.|
|2/04/23| Jan Castillo |Canviat Level Shifter i, per tant, el diagrama de blocs.|
|5/04/23| Bethany Quintero | Canviat el model del level shifter. Actualització esquemàtic: afegits els divisors de tensions per Vref i level shifter.|
|6/04/23| Jan Castillo | Alguns canvis a l'esquemàtic.|
|6/04/23| Bethany Quintero | Canvi a l'esquemàtic.|
|9/04/23| Bethany Quintero | Canvi de nets a l'esquemàti.c|
|10/04/23| Jan Castillo i Bethany Quintero |Primera versió Layout.|
|23/04/23| Jan Castillo i Bethany Quintero |Actualització diagrama de blocs, esquemàtic i layout finals.|
