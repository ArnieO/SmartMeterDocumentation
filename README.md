# SmartMeterDocumentation
Document collection: HAN interface for Smart energy meters in European countries

## Introduction
This is a collection of documents related to the HAN (Home Area Network) port on Smart energy meters ("Smart meters") in some European countries. 

## National technical requirements
| Country | National authority | Specification document |
| --- | --- | --- |
| Norway | [Noregs vassdrags- og energidirektorat](http://www.nve.no)| Unclear regulatory situation. [This document](https://github.com/ArnieO/SmartMeterDocumentation/raw/main/Norway/NEK%20AMS%20HAN.pdf) describes the physical interface requirements but not the protocol. Please see each supplier's interface specification [here](https://github.com/ArnieO/SmartMeterDocumentation/tree/main/Norway).   |
| Sweden | [Energimarknadsinspektionen](https://www.ei.se) | [Ei-R2017:08](https://github.com/ArnieO/SmartMeterDocumentation/blob/main/Sweden/Funktionskrav-p%C3%A5-elm%C3%A4tare-F%C3%B6rfattningsf%C3%B6rslag-Ei-R2017-08.pdf) |
| Denmark | [Energistyrelsen](https://ens.dk) | |

## HAN interface description
The table shows the interface as seen on the meter.
| Country | Physical plug and Pinout | Signals | Protocol | Encryption? |
| --- | --- | --- | --- | --- |
| Norway | RJ45 Female 8p8c ("Ethernet") <br/> ![image](https://user-images.githubusercontent.com/10295178/135722554-d181142c-c82c-4ec2-a710-183ffa9b96b4.png) | M-BUS <br/> V<sub>high</sub> = 24V <br/> V<sub>low</sub> = 12V <br/> **Maximum current:** <br/> - Kamstrup: I<sub>max</sub> = 6 mA <br/> - Kaifa: I<sub>max</sub> = 30 mA  <br/> - Aidon: I<sub>max</sub> = 21 mA| | No |
| Norway and Denmark,<br/>Kamstrup built-in HAN port [^1] | Female 2x3 pin header 2.54mm <br/> ![image](https://user-images.githubusercontent.com/10295178/135723960-ffad1276-5f5a-4dde-bade-e9effa551767.png) <br/> ![image](https://user-images.githubusercontent.com/10295178/135723985-b57b74e0-28cf-48a3-9de6-e9b19e23fb11.png) | ![image](https://user-images.githubusercontent.com/10295178/135724009-9f7fe890-b8cd-4b7b-b9fa-c5ca978f570c.png) <br/> **Note:** DATA_IN is not used (do not connect) | | Encrypted in Denmark, not in Norway |
| Sweden | RJ12 Female 6p6c ("Phone system") <br/> ![image](https://user-images.githubusercontent.com/10295178/135724732-d5ca9a0c-4257-40c5-87b1-72bb95a5deff.png)| **+5V**: I<sub>max</sub> = 250 mA <br/> **Request**: tied to +5V <br/> **Data**: Open collector | [IEC 62056-21](https://en.wikipedia.org/wiki/IEC_62056#IEC_62056-21) (DLMS/COSEM-protocol) <br/> Mode D | No |
 
[^1]: **Note regarding use of Kamstrup built-in HAN port in Norway:** <br/> The juridical interface (where grid company responsibility ends and user responsibility starts) is the RJ45 connector on the [Kamstrup HAN-NVE module](https://github.com/ArnieO/SmartMeterDocumentation/raw/main/Norway/Kamstrup/Kamstrup%20HAN-NVE%20Module%20data%20sheet.pdf) provided by the grid company.
    
