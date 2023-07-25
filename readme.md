# RaceChrono BLE CAN и GPS адаптер

GPS приемник и CAN адаптер для работы с [RaceChrono](https://racechrono.com/). В качестве управляющего МК использован NRF52840. Для упрощения сборки используется готовый модуль [Ebyte E73-2G4M08S1C](https://aliexpress.ru/item/1005004834868792.html) ([datasheet](./doc/S1C_Usermanual_v1.9.pdf))

В качестве GPS приемника используется [Ublox M9N](https://www.u-blox.com/en/product/neo-m9n-module) с частотой обновления 25Ghz.

CAN реализован на [MCP2515](./doc/MCP2515-Stand-Alone-CAN-Controller-with-SPI-20001801J.pdf) и транссивере SN65HVD230. Для упрощения покупки mcp2515 используется [готовый модуль](https://aliexpress.ru/item/32817132818.html), с которого была снята сама микросхема MCP2515, а так же кварц и конденсаторы кварца.

![device render](./img/nrf52840_dev.png)

[Schematic](./shematic/nrf52840_dev.pdf)

Проект выполнен в Kicad.

## Список компонентов

Интерактивный BOM находится в bom/ibom.html

| Элемент     | Количество | Номинал | Посадочное место | Описание
| ----------- | ----------- | ----------- | ----------- | -----------
|C1, C18, C19|3|1uF|Capacitor_SMD:C_0805_2012Metric| |
|C2, C12     |2|10uF|Capacitor_SMD:C_0805_2012Metric| | 
|C3, C4      |2|C_Small|Capacitor_SMD:C_0603_1608Metric|Сняты с модуля CAN|
|C5, C6, C13, C14, C49|5|0.1uF|Capacitor_SMD:C_0805_2012Metric| |
|C7|1|1F|Capacitor_THT:CP_Radial_D8.0mm_P3.50mm|Используется как источник резервного питания GPS модуля|
|C11, C20, C40|3|0.01uF|Capacitor_SMD:C_0603_1608Metric| |
|C15|1|1.6pF|Capacitor_SMD:C_0402_1005Metric| |
|C16, C17|2|47uF|Capacitor_Tantalum_SMD:CP_EIA-7343-31_Kemet-D_Pad2.25x2.55mm_HandSolder| |
