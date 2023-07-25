# RaceChrono BLE CAN и GPS адаптер

GPS приемник и CAN адаптер для работы с [RaceChrono](https://racechrono.com/). В качестве управляющего МК использован NFR52840. Для упрощения сборки используется готовый модуль [Ebyte E73-2G4M08S1C](https://aliexpress.ru/item/1005004834868792.html) ([datasheet](./doc/S1C_Usermanual_v1.9.pdf))

В качестве GPS приемника используется [Ublox M9N](https://www.u-blox.com/en/product/neo-m9n-module) с частотой обновления 25Ghz.

CAN реализован на [MCP2515](./doc/MCP2515-Stand-Alone-CAN-Controller-with-SPI-20001801J.pdf) и транссивере SN65HVD230.


![device render](./img/nrf52840_dev.png)

[Schematic](./shematic/nrf52840_dev.pdf)