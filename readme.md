# RaceChrono BLE CAN и GPS адаптер

[English version](./readme_en.md)

GPS приемник и CAN адаптер для работы с [RaceChrono](https://racechrono.com/) через BLE ([подробности протокола](https://github.com/aollin/racechrono-ble-diy-device)). 

В качестве управляющего МК использован NRF52840. Для упрощения сборки используется готовый модуль [Ebyte E73-2G4M08S1C](https://aliexpress.ru/item/1005004834868792.html) ([datasheet](./doc/S1C_Usermanual_v1.9.pdf))

В качестве GPS приемника используется [Ublox M9N](https://www.u-blox.com/en/product/neo-m9n-module) с частотой обновления 25Hz.

CAN реализован на [MCP2515](./doc/MCP2515-Stand-Alone-CAN-Controller-with-SPI-20001801J.pdf) и транссивере SN65HVD230. Для упрощения покупки mcp2515 снята с [готового модуля](https://aliexpress.ru/item/32817132818.html), с которого так же был снят кварц и конденсаторы кварца.

![device render](./img/nrf52840_dev.png)

[Схема](./shematic/nrf52840_dev.pdf)

Проект выполнен в Kicad 7.

## Список компонентов

Интерактивный BOM находится в bom/ibom.html

| Элемент     | Количество | Номинал | Посадочное место | Описание
| ----------- | ----------- | ----------- | ----------- | -----------
|C1, C18, C19|3|1uF|Capacitor_SMD:C_0805_2012Metric| |
|C2, C12     |2|10uF|Capacitor_SMD:C_0805_2012Metric| | 
|C3, C4      |2|C_Small|Capacitor_SMD:C_0603_1608Metric|Сняты с модуля CAN|
|C5, C6, C13, C14, C49|5|0.1uF|Capacitor_SMD:C_0805_2012Metric| |
|C7|1|1F|Capacitor_THT:CP_Radial D8.0mm_P3.50mm|Используется как источник резервного питания GPS модуля|
|C11, C20, C40|3|0.01uF|Capacitor_SMD:C_0603_1608Metric| |
|C15|1|1.6pF|Capacitor_SMD:C_0402_1005Metric| |
|C16, C17|2|47uF|Capacitor_Tantalum SMD:CP_EIA-7343-31_Kemet-D| |
|D1, D2|  2|LED_Small|LED_SMD:LED_1206_3216Metric| |
|D3    |1|NUP2105L|Package_TO_SOT_SMD:SOT-23|Dual Line CAN Bus Protector, 24Vrwm|
|D4    |1|1N4148|Diode_SMD:D_SOD-323| |
|D18   |1|BZT52C16S|Diode_SMD:D_SOD-323| |
|D19   |1|STPS2L25|Diode_SMD:D_SMB"| |
|J1|1|Conn 01x04|JST_XH_S4B-XH-A-1_1x04_P2.50mm_Horizontal| |
|J2|1|Coaxial Power|SMA_Amphenol_901-144_Vertical| |
|J3|1|SWD|PinHeader_2x05_P1.27mm_Vertical_SMD| |
|L1|1|8.2uH|power:Inductor8.2| |
|L2|1|27nH|Inductor_SMD:L_0805_2012| |
|Q5|1|AO3401A|Package_TO_SOT_SMD:SOT-23| |
|R1, R2|2|1K|Resistor_SMD:R_0805_2012Metric| |
|R3|1|120|Resistor_SMD:R_0603_1608Metric| |
|R4|1|100|Resistor_SMD:R_0805_2012Metric| |
|R27|1|10K|Resistor_SMD:R_0603_1608Metric| |
|R28|1|187K|Resistor_SMD:R_0603_1608Metric| |
|R29|1|60.4K|Resistor_SMD:R_0603_1608Metric| |
|R40|1|10|Resistor_SMD:R_1206_3216Metric| |
|U1|1|E73-2G4M08S1C|E73-2G4M08S1C-52840| |
|U2|1|MCP2515-xSO|Package_SO:SOIC-18W|Stand-Alone CAN Controller with SPI Interface<br>Снят с модуля CAN|
|U3|1|ST1S14PHR_MY|Package_SO:SOIC-8-1EP| |
|U4|1|NCP3335|Package_SO:OnSemi_Micro8| |
|U5|1|SN65HVD230|Package_SO:SOIC-8|CAN Bus Transceivers, 3.3V, 1Mbps, Low-Power capabilities|
|U17|1|NEO-9M|ublox:NEO-M8N|Ublox M9N|
|Y1|1|8Mhz|Crystal:Crystal_HC49-4H_Vertical|Снят с модуля CAN|
