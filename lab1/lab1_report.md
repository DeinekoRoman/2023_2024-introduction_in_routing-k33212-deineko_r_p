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
