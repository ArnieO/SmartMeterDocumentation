# SmartMeterDocumentation
Document collection: HAN interface for Smart energy meters in European countries

This is a collection of documents related to the HAN (Home Area Network) port on Smart energy meters ("Smart meters") in some European countries. 

| Country | Physical plug | Pinout | Signals | Protocol | Encryption? |
| --- | --- | --- | --- | --- | --- |
| Norway | RJ45 Female 8p8c ("Ethernet") | ![image](https://user-images.githubusercontent.com/10295178/135722554-d181142c-c82c-4ec2-a710-183ffa9b96b4.png) | MODBUS <br/> V<sub>high</sub> = 24V <br/> V<sub>low</sub> = 12V <br/> **Maximum current:** <br/> - Kamstrup: I<sub>max</sub> = 6 mA <br/> - Kaifa: I<sub>max</sub> = 30 mA  <br/> - Aidon: I<sub>max</sub> = 21 mA| | No |
| Norway and Denmark,<br/>Kamstrup built-in HAN port | Female 2x3 pin header 2.54mm <br/> ![image](https://user-images.githubusercontent.com/10295178/135723960-ffad1276-5f5a-4dde-bade-e9effa551767.png) | ![image](https://user-images.githubusercontent.com/10295178/135723985-b57b74e0-28cf-48a3-9de6-e9b19e23fb11.png) | ![image](https://user-images.githubusercontent.com/10295178/135724009-9f7fe890-b8cd-4b7b-b9fa-c5ca978f570c.png) | | Encrypted in Denmark, not in Norway |
| Sweden | RJ12 Female 6p6c ("Phone system")| ![image](https://user-images.githubusercontent.com/10295178/135724732-d5ca9a0c-4257-40c5-87b1-72bb95a5deff.png)| **+5V**: I<sub>max</sub> = 250 mA <br/> **Request**: tied to +5V <br/> **Data**: Open collector | [IEC 62056-21](https://en.wikipedia.org/wiki/IEC_62056#IEC_62056-21) (DLMS/COSEM-protocol) <br/> Mode D | No |
 
