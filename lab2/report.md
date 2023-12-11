University: [ITMO University](https://itmo.ru/ru/)  

Faculty: [FICT](https://fict.itmo.ru)  

Course: [Introduction in routing](https://github.com/itmo-ict-faculty/introduction-in-routing)  

Year: 2023/2024  

Group: K33212  

Author: Deineko Roman Pavlovich

Lab: Lab2  

Date of create: 11.12.2023  

Date of finished: 11.12.2023

# Лабораторная работа №2 "Эмуляция распределенной корпоративной сети связи, настройка статической маршрутизации между филиалами"
## Цель работы
Ознакомиться с инструментом ContainerLab и методами работы с ним, изучить работу VLAN, IP адресации и т.д.
## Ход работы
На всех интерфейсах роутеров были настроены ip-адреса, а также созданы dhcp-серверы
### Конфигурация R01.MSK
![image](https://github.com/DeinekoRoman/2023_2024-introduction_in_routing-k33212-deineko_r_p/assets/90695269/e420d82c-67f4-40b8-bf4c-9b6524e0e7ad)

### Конфигурация R01.FRT
![image](https://github.com/DeinekoRoman/2023_2024-introduction_in_routing-k33212-deineko_r_p/assets/90695269/97a08cfe-36b6-412b-98d1-08d560fdd1ba)

### Конфигурация R01.BRL
![image](https://github.com/DeinekoRoman/2023_2024-introduction_in_routing-k33212-deineko_r_p/assets/90695269/e42338c1-ba2b-4a4c-917a-912ffab3722b)

На компьютерах были настроены dhcp-клиенты для получения ip-адресов от сервера, а также настроены статитечские маршруты

### Конфигурация PC.MSK
![image](https://github.com/DeinekoRoman/2023_2024-introduction_in_routing-k33212-deineko_r_p/assets/90695269/d3890bd3-408a-4103-87c9-74ef6259d7e2)

### Конфигурация PC.FRT
![image](https://github.com/DeinekoRoman/2023_2024-introduction_in_routing-k33212-deineko_r_p/assets/90695269/185882b8-df7f-487c-8a4e-785351ead9c2)

### Конфигурация PC.BRL
![image](https://github.com/DeinekoRoman/2023_2024-introduction_in_routing-k33212-deineko_r_p/assets/90695269/21f3038c-1df0-4067-adc3-4919fb9ff713)

### Настройка PC2
С помощью пакетов iproute2 и dhcpcd5 через dhcp-сервера компьютерами были получены соответствующие ip адреса (Компьютер PC1 был настроен аналогично)
![image](https://github.com/DeinekoRoman/2023_2024-introduction_in_routing-k33212-deineko_r_p/assets/90695269/0617ad09-ad29-4dc4-9086-57fd85f6b26e)

### Топология сети
![image](https://github.com/DeinekoRoman/2023_2024-introduction_in_routing-k33212-deineko_r_p/assets/90695269/1b5dab6d-141b-45b4-8b1a-0cb3e3001b28)

### Проверка доступности
В результате проверки можно убедиться, что все устройства соединены и функционируют в соответствии с заданием
![image](https://github.com/DeinekoRoman/2023_2024-introduction_in_routing-k33212-deineko_r_p/assets/90695269/26e38df5-82f3-4969-a7cd-123ae5230180)
![image](https://github.com/DeinekoRoman/2023_2024-introduction_in_routing-k33212-deineko_r_p/assets/90695269/5548760a-ca1b-4ad3-ad2d-55c1cd8a3849)
![image](https://github.com/DeinekoRoman/2023_2024-introduction_in_routing-k33212-deineko_r_p/assets/90695269/4f0dc8fb-fd3c-47c8-a1fe-cec99f340605)

## Вывод
В результате лабораторной работы удалось ознакомиться с настройкой DHCP-сервера и статической маршрутизации.


