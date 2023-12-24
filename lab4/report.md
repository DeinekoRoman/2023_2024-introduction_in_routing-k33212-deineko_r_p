University: [ITMO University](https://itmo.ru/ru/)  

Faculty: [FICT](https://fict.itmo.ru)  

Course: [Introduction in routing](https://github.com/itmo-ict-faculty/introduction-in-routing)  

Year: 2023/2024  

Group: K33212  

Author: Deineko Roman Pavlovich

Lab: Lab4  

Date of create: 24.12.2023  

Date of finished: 24.12.2023

# Лабораторная работа №4 "Эмуляция распределенной корпоративной сети связи, настройка iBGP, организация L3VPN, VPLS"
## Цель работы
Изучить протоколы BGP, MPLS и правила организации L3VPN и VPLS.
## Ход работы
Согласно заданию, была развернута следующая сеть:
![image](https://github.com/DeinekoRoman/2023_2024-introduction_in_routing-k33212-deineko_r_p/assets/90695269/ed316146-5c73-4942-a254-acf7736b443e)
На каждом роутере были настроены интерфейсы и BGP. Протокол BGP предназначен для обмена информацией о достижимости подсетей между AS , то есть группами маршрутизаторов под единым техническим и административным управлением, использующими протокол внутридоменной маршрутизации для определения маршрутов внутри себя и протокол междоменной маршрутизации для определения маршрутов доставки пакетов в другие AS.
Для настройки OSPF на всех узлах был создан bridge Lo и добавлена ```area backbone```
