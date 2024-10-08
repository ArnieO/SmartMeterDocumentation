# SmartMeterDocumentation
Document collection: HAN interface for Smart energy meters in European countries

## Introduction
This is a collection of documents related to the HAN (Home Area Network) port on Smart energy meters ("Smart meters") in some European countries. The information is edited to the best of my knowledge, but in some case solid information is hard to find - so there might be errors. Please contact me (rise an "issue" here!) if you see errors or misunderstandings.

## National technical requirements
| Country     | National authority                                        | Specification document                                                                                                                                                                                                                                                                                                                          |
|-------------|-----------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Norway      | [Noregs vassdrags- og energidirektorat](http://www.nve.no) | [This document](https://github.com/ArnieO/SmartMeterDocumentation/blob/main/Norway/NVE%20201603186-1-informasjon-til-kundene-via-han-grensesnittet-i-ams-m%C3%A5leren-obis-koder-1772408_1124902_0.pdf) approves the recommendation in [this document](https://github.com/ArnieO/SmartMeterDocumentation/blob/main/Norway/NEK%20AMS%20HAN.pdf). |
| Sweden      | [Energimarknadsinspektionen](https://www.ei.se)           | [Ei-R2017:08](https://github.com/ArnieO/SmartMeterDocumentation/blob/main/Sweden/Funktionskrav-p%C3%A5-elm%C3%A4tare-F%C3%B6rfattningsf%C3%B6rslag-Ei-R2017-08.pdf)                                                                                                                                                                             |
| Denmark     | [Energistyrelsen](https://ens.dk)                         | [Målerbekendtgørelse BEK nr 563 af 02/06/2014](https://github.com/ArnieO/SmartMeterDocumentation/blob/main/Denmark/B20140056305.pdf)<br/>[Målerbekendtgørelse BEK nr 75 af 25/01/2019](https://github.com/ArnieO/SmartMeterDocumentation/blob/main/Denmark/B20190007505.pdf)                                                                    |
| Netherlands | [Netbeheer Nederland](https://www.netbeheernederland.nl)  | [Dutch Smart Meter Requirements v4.0.7 14mar2014](https://github.com/ArnieO/SmartMeterDocumentation/blob/main/Netherlands/DutchSmartMeterRequirements_v4.0.7_14mar2014.pdf)                                                                                                                                                                     |
| Finland     | [Energiavirasto](https://energiavirasto.fi/) | [Suositus sähköenergiamittareiden paikallista asiakasrajapintaa varten](https://sesko.fi/wp-content/uploads/2022/12/Suositus-SK-13-1_H1-asiakasrajapinta_suomenkielinen_2022-12-13.pdf)                                                                                                                                                                     |
| Germany     | [Bundesamt für Sicherheit in der Informationstechnik (BSI)](https://www.bsi.bund.de) | [Smart-Meter-Gateway](https://www.bsi.bund.de/dok/7612230)<br/>[Technische Richtlinie (BSI-TR-03109-1)](https://www.bsi.bund.de/dok/7614914)
|

## HAN interface description
The table shows the interface as seen on the meter.

| Country                                            | Physical plug and Pinout | Signals | Protocol | Encryption? |
|----------------------------------------------------|--------------------------|---------|----------|-------------|
| Norway                                             | RJ45 Female 8p8c ("Ethernet") <br/> ![image](https://user-images.githubusercontent.com/10295178/135722554-d181142c-c82c-4ec2-a710-183ffa9b96b4.png) | M-BUS <br/> V<sub>high</sub> = 24V <br/> V<sub>low</sub> = 12V <br/> **Maximum current:** <br/> - Kamstrup: I<sub>max</sub> = 6 mA <br/> - Kaifa: I<sub>max</sub> = 30 mA  <br/> - Aidon: I<sub>max</sub> = 21 mA| - IEC 62056-7-5 <br/>- MBUS (EN 13757-2) <br/>- RJ-45 socket | No |
| Norway and Denmark,<br/>Kamstrup built-in HAN port | Female 2x3 pin header 2.54mm <br/> ![image](https://user-images.githubusercontent.com/10295178/135723960-ffad1276-5f5a-4dde-bade-e9effa551767.png) <br/> ![image](https://user-images.githubusercontent.com/10295178/135723985-b57b74e0-28cf-48a3-9de6-e9b19e23fb11.png) | ![image](https://user-images.githubusercontent.com/10295178/135724009-9f7fe890-b8cd-4b7b-b9fa-c5ca978f570c.png) <br/> **Note:** DATA_IN is not used (do not connect) | - IEC 62056-7-5 <br/>- MBUS (EN 13757-2) <br/>- RJ-45 socket  | Encrypted in Denmark, not in Norway |
| Sweden                                             | RJ12 Female 6p6c ("Phone system") <br/>![image](https://user-images.githubusercontent.com/10295178/136756312-1575f6ed-3e92-4841-813a-dc6f81be9ce5.png) <br/> ![image](https://user-images.githubusercontent.com/10295178/135724732-d5ca9a0c-4257-40c5-87b1-72bb95a5deff.png)| **+5V**: I<sub>max</sub> = 250 mA <br/> **Request**: tied to +5V <br/> **Data**: Open collector | IEC 62056-7-5 | No |
| Netherlands [^1] [^2]                              | RJ12 Female 6p6c ("Phone system") <br/>![image](https://user-images.githubusercontent.com/10295178/136756312-1575f6ed-3e92-4841-813a-dc6f81be9ce5.png)  <br/> ![image](https://user-images.githubusercontent.com/10295178/135724732-d5ca9a0c-4257-40c5-87b1-72bb95a5deff.png) | **+5V**: I<sub>max</sub> = 250 mA <br/> **Request**: tied to +5V <br/> **Data**: Open collector, 115200 baud (8N1). Data frame interval: 1 sec | [IEC 62056-21](https://en.wikipedia.org/wiki/IEC_62056#IEC_62056-21) (DLMS/COSEM-protocol) <br/> Mode D | No |
| Finland                                            | RJ12 Female 6p6c ("Phone system") <br/>![image](https://user-images.githubusercontent.com/10295178/136756312-1575f6ed-3e92-4841-813a-dc6f81be9ce5.png) <br/> ![image](https://user-images.githubusercontent.com/10295178/135724732-d5ca9a0c-4257-40c5-87b1-72bb95a5deff.png)| **+5V**: I<sub>max</sub> = 250 mA <br/> **Request**: tied to +5V <br/> **Data**: Open collector | IEC 62056-7-5 | No |

[^1]: Reference: [Dutch Smart Meter Requirements, P1 Companion Standard](https://github.com/ArnieO/SmartMeterDocumentation/blob/main/Netherlands/DSMR_P1CompanionStandard_v5.0.2_26feb2016.pdf)
[^2]: As the standard in Netherlands has evolved a  over the years, there seems to be a number of varieties installed as reported by [http://domoticx.com/p1-poort-slimme-meter-hardware/ (Google-translated to English)](https://domoticx-com.translate.goog/p1-poort-slimme-meter-hardware/?_x_tr_sch=http&_x_tr_sl=auto&_x_tr_tl=en&_x_tr_hl=no&_x_tr_pto=nui)

## National issues / specificities
### Norway
Four meter brands are used, chosen by the grid company:
- Aidon
- Kaifa
- Kamstrup
- Landis Gyr (introduced after the initial rollout)

Smart meters delivered in Norway must follow the NVE specification indicated in above tables.
The juridical interface (where grid company responsibility ends and user responsibility starts) is the RJ45 connector.
Kamstrup meters do not have built-in HAN interface, they must be equipped with the [Kamstrup HAN-NVE module](https://github.com/ArnieO/SmartMeterDocumentation/raw/main/Norway/Kamstrup/Kamstrup%20HAN-NVE%20Module%20data%20sheet.pdf). Some grid companies deliver this module pre installed with the meter, other grid companies mails the module to users that request the HAN port to be opened, user then installs it. 
HAN port is by default inactive, users must request opening.
Landis Gyr meters are equipped with a "EmbriQ Politerm801 PLC" module, which provides the NVE-HAN interface with RJ45 connector. EmbriQ has confirmed the electrical specification for the interface is as per paragraph 4.1 in [this document](https://github.com/ArnieO/SmartMeterDocumentation/blob/main/Norway/Landis%20Gyr/OP030a%20Montasjeinstruks%20og%20brukerveiledning.pdf).

### Sweden
The first smart meters installed in Sweden follows the "Norwegian standard" as defined by NVE (MBUS, RJ45 connector). It is unclear whether, and if so when, those meters will be replaced by meters following the Swedish regulatory specification described in above tables.

### Denmark
In Denmark, the majority of grid companies seem to use Kamstrup meters with encrypted HAN ports.

According to [user findings reported here](https://www.ihc-user.dk/forum/forums/topic/7467-kamstrup-elm%C3%A5lere/?do=findComment&comment=58737), some meters seem to have old firmware where data must be pulled from the meter using "Kamstrup proprietary protocol", which is not openly available. This seems to be in breach of the requirement set down in §7 in [BEK nr 75 af 25/01/2019](https://github.com/ArnieO/SmartMeterDocumentation/blob/main/Denmark/B20190007505.pdf) that requires open standards: <br/> 
![image](https://user-images.githubusercontent.com/10295178/137465380-2e3394b5-ebd8-44ce-a304-a350b0c3ff52.png)

The following Danish grid companies have been reported (autumn 2021) to be using (some) Kamstrup meters that require data to be pulled using "Kamstrup proprietary protocol". They seem to prefer replacing the meters with new ones in stead of requesting Kamstrup to upgrade firmware on existing meters.:
- [Nord Energi](https://nordenerginet.dk/) [^3]
- [Elinord](https://www.elinord.dk/)
[^3]: https://github.com/gskjold/AmsToMqttBridge/issues/126#issuecomment-944068744

Useful page for Denmark, giving a geographic overview of the grid companies: https://www.danskenergi.dk/vejledning/nettilslutning/find-netselskab

### Finland
Rollout of RJ-12 meters ongoing. A transition of measurement from 1 hour average into 15 minute average has been decided.
This replacement forces network operators to use meters with P1/HAN -port.
