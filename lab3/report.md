University: [ITMO University](https://itmo.ru/ru/)  

Faculty: [FICT](https://fict.itmo.ru)  

Course: [Introduction in routing](https://github.com/itmo-ict-faculty/introduction-in-routing)  

Year: 2023/2024  

Group: K33212  

Author: Deineko Roman Pavlovich

Lab: Lab3  

Date of create: 11.12.2023  

Date of finished: 11.12.2023

# Лабораторная работа №3 "Эмуляция распределенной корпоративной сети связи, настройка OSPF и MPLS, организация первого EoMPLS"
## Цель работы
Изучить протоколы OSPF и MPLS, механизмы организации EoMPLS.
## Ход работы
Согласно заданию, была развернута следующая сеть:
![image](https://github.com/DeinekoRoman/2023_2024-introduction_in_routing-k33212-deineko_r_p/assets/90695269/dc8ab17e-a35b-4264-ba5b-3f9e2b6f0085)

На роутере SPB были созданы и настроены интерфейсы EoMPLS_BR и Lo0. На интерфейсе EoMPLS_BR был настроен VPLS и заданы параметры MAC-адреса, максимального размера передаваемого кадра и адреса конечной точки удаленного узла. Команда '''/routing ospf network add area=backbone''' указывает, что сетевой интерфейс должен быть добавлен в OSPF-зону '''backbone''' (главная зона OSPF с идентификатором 0.0.0.0). Зона OSPF - это логическая группа устройств OSPF, внутри которой маршрутизаторы способны обмениваться информацией о маршрутах.
### Конфигурация R01_SPB
![image](https://github.com/DeinekoRoman/2023_2024-introduction_in_routing-k33212-deineko_r_p/assets/90695269/46e06721-3743-4134-95ba-6cfa241fc04a)

### Конфигурация R01_HKI
![image](https://github.com/DeinekoRoman/2023_2024-introduction_in_routing-k33212-deineko_r_p/assets/90695269/d55556a6-a5d4-461e-956a-77aef05588db)

### Конфигурация R01_MSK
![image](https://github.com/DeinekoRoman/2023_2024-introduction_in_routing-k33212-deineko_r_p/assets/90695269/250ff3a4-aa30-400f-965e-dcfa382cc495)

### Конфигурация R01_LBN
![image](https://github.com/DeinekoRoman/2023_2024-introduction_in_routing-k33212-deineko_r_p/assets/90695269/848a5813-f696-4863-9396-9ecad10470bf)

### Конфигурация R01_LND
![image](https://github.com/DeinekoRoman/2023_2024-introduction_in_routing-k33212-deineko_r_p/assets/90695269/65f6e027-372a-48e4-a816-f54a38568ceb)

### Конфигурация R01_NYC
![image](https://github.com/DeinekoRoman/2023_2024-introduction_in_routing-k33212-deineko_r_p/assets/90695269/4c83295e-28db-434e-aca1-54898e17ecba)

С помощью пакета iproute2 обоим компьютерам были заданы статические ip-адреса

### Топология сети
![image](https://github.com/DeinekoRoman/2023_2024-introduction_in_routing-k33212-deineko_r_p/assets/90695269/91304fb6-8505-42c0-8297-5310f55181e9)

### Проверка доступности
В результате проверки можно убедиться, что все устройства соединены и функционируют в соответствии с заданием
![image](https://github.com/DeinekoRoman/2023_2024-introduction_in_routing-k33212-deineko_r_p/assets/90695269/aa7d188b-fa9e-4200-bacc-7dafe4740f40)
![image](https://github.com/DeinekoRoman/2023_2024-introduction_in_routing-k33212-deineko_r_p/assets/90695269/0f86166c-92d4-418c-9805-419e3924995b)

## Вывод
В результате лабораторной работы удалось ознакомиться с протоколами OSPF и MPLS.
