---
description: 'Цикл 11, Тема 61: OSPF 3.6'
---

# Лабораторная по теме

{% file src="../../.gitbook/assets/lab061.zip" caption="Начальная конфигурация" %}

1. Загрузить начальную конфигурацию всех устройств.
2. Для задания используется логическая и физическая топологии проекта.
3. Настроить маршрутизаторы R4, R5, R6 таким образом, чтобы следующие интерфейсы находились в Area 0 :
   1. Номер ospf процесса 100
   2. R4 — интерфейсы Loopback 0 и E0/1.456
   3. R5 — интерфейсы Loopback 0, E0/1.456, E0/1.5
   4. R6 — интерфейсы Loopback 0, E0/1.456, E0/1.6
4. Настроить маршрутизаторы R2, R3, R4, R5 таким образом, чтобы следующие интерфейсы находились в Area 15 :
   1. Номер ospf процесса 100
   2. R2-  интерфейсы E0/1.23,  E0/1.235
   3. все интерфейсы R3
   4. R4 — интерфейс E0/1.34
   5. R5 — интерфейс E0/1.235
5. Настроить маршрутизаторы R6, R7, R8, R9, R10 таким образом, чтобы следующие интерфейсы находились в Area 107 :
   1. Номер ospf процесса 100
   2. все интерфейсы R7, R8, R9, R10
   3. R6 — интерфейс E0/1.67
6. Настроить маршрутизаторы R1, R2 таким образом, чтобы следующие интерфейсы находились в Area 10 :
   1. Номер ospf процесса 100
   2. R1- интерфейс E0/1.12
   3. R2- интерфейс E0/1.12
7. Настроить маршрутизатор R1 таким образом, чтобы интерфейс Loopback 0 находился в процессе EIGRP 100. Редистрибьютить его в ospf.
8. Поменять полосу пропускания на интерфейсе Multilink1 R9 таким образом, чтобы метрика в таблице маршрутизации на R8 до 180.1.10.10 стала равной 12.
9. На R8 применить auto-cost таким образом, чтобы метрика в таблице маршрутизации на R2 до 180.1.10.10 стала равной последнему октету ip адреса протокола GLBP.
10. Решить проблему получения маршрутов маршрутизатором R1 стандартным для OSPF способом.

{% file src="../../.gitbook/assets/lab061\_answers.zip" caption="Конечная конфигурация" %}
