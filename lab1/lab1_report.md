University: [ITMO University](https://itmo.ru/ru/)  

Faculty: [FICT](https://fict.itmo.ru)  

Course: [Introduction in routing](https://github.com/itmo-ict-faculty/introduction-in-routing)  

Year: 2023/2024  

Group: K33212  

Author: Deineko Roman Pavlovich

Lab: Lab1  

Date of create: 29.10.2023  

Date of finished: 30.10.2023

# Лабораторная работа №1 "Установка ContainerLab и развертывание тестовой сети связи"
## Цель работы
Ознакомиться с инструментом ContainerLab и методами работы с ним, изучить работу VLAN, IP адресации и т.д.
## Ход работы
После того, как с помощью make docker-image был собран образ, для развертывания сети необходимо было создать yaml файл:
```
name: lab1
prefix: ""

mgmt:
  network: statics
  ipv4_subnet: 172.20.20.0/24
  
topology:

  nodes:

      R01.TEST:
          kind: vr-ros
          image: vrnetlab/vr-routeros:6.47.9
          mgmt-ipv4: 172.20.20.2

      SW01.L3.01.TEST:
          kind: vr-ros
          image: vrnetlab/vr-routeros:6.47.9
          mgmt-ipv4: 172.20.20.3
          
      SW02.L3.01.TEST:
          kind: vr-ros
          image: vrnetlab/vr-routeros:6.47.9
          mgmt-ipv4: 172.20.20.6

      SW02.L3.02.TEST:
          kind: vr-ros
          image: vrnetlab/vr-routeros:6.47.9
          mgmt-ipv4: 172.20.20.4

      PC1:
          kind: linux
          image: ubuntu:latest
          mgmt-ipv4: 172.20.20.7

      PC2:
          kind: linux
          image: ubuntu:latest
          mgmt-ipv4: 172.20.20.5


  links:
    - endpoints: ["R01.TEST:eth1", "SW01.L3.01.TEST:eth1"]
    - endpoints: ["SW01.L3.01.TEST:eth2", "SW02.L3.01.TEST:eth1"]
    - endpoints: ["SW02.L3.01.TEST:eth2", "PC1:eth1"]
    - endpoints: ["SW01.L3.01.TEST:eth3", "SW02.L3.02.TEST:eth1"]
    - endpoints: ["SW02.L3.02.TEST:eth2", "PC2:eth1"]
```
Далее была проведена настройка каждого устройства в сети отдельно:
### Конфигурация R01.TEST
![image](https://github.com/DeinekoRoman/2023_2024-introduction_in_routing-k33212-deineko_r_p/assets/90695269/b8fb14d5-0de0-4c23-897c-23ecda712344)

### Конфигурация SW01.L3.01.TEST
![image](https://github.com/DeinekoRoman/2023_2024-introduction_in_routing-k33212-deineko_r_p/assets/90695269/ec5f0f08-8638-4169-8590-2e6aa029b1ab)

### Конфигурация SW02.L3.01.TEST
![image](https://github.com/DeinekoRoman/2023_2024-introduction_in_routing-k33212-deineko_r_p/assets/90695269/1d470312-2c2a-470e-876d-924677636bd2)

### Конфигурация SW02.L3.02.TEST
![image](https://github.com/DeinekoRoman/2023_2024-introduction_in_routing-k33212-deineko_r_p/assets/90695269/8c1dcfd1-937b-48d9-87a2-5113c588ad6c)

### Настройка PC2
С помощью пакетов iproute2 и dhcpcd5 через dhcp-сервера компьютерами были получены соответствующие ip адреса (Компьютер PC1 был настроен аналогично)
![image](https://github.com/DeinekoRoman/2023_2024-introduction_in_routing-k33212-deineko_r_p/assets/90695269/0617ad09-ad29-4dc4-9086-57fd85f6b26e)

### Топология сети
![Топология](https://github.com/DeinekoRoman/2023_2024-introduction_in_routing-k33212-deineko_r_p/assets/90695269/562a1fec-ac99-485a-9210-87df1fa2d99e)

### Проверка доступности
В результате проверки можно убедиться, что все устройства соединены и функционируют в соответствии с заданием
![image](https://github.com/DeinekoRoman/2023_2024-introduction_in_routing-k33212-deineko_r_p/assets/90695269/1b0aabfd-fe3f-4a5b-956c-ae1e0a64ffce)

## Вывод
В результате лабораторной работы удалось ознакомиться с инструментом ContainerLab, а также создать сеть и настроить устройства на базе ОС Linux и RouterOS
