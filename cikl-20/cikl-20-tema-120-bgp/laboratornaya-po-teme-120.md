---
description: 'Цикл 20, Тема 120:BGP'
---

# Лабораторная по теме 120

1. Для данного задания в качестве начальной конфигурации использовать конечную конфигурацию лабораторного задания 118.
2. Для задания используется логическая и физическая топологии проекта.
3. На маршрутизаторе R2 и R4 настроить редистрибьюцию OSPF маршрутов из AS 41 в AS 51
4. На маршрутизаторах R2 и R4 агрегацию всех IP адресов Loopback0 интерфейсов с маской /21 из AS 41 в AS 51 c опцией Summary Only и опцией восстановления избегания петель.
5. На маршрутизаторе R5 агрегацию всех IP адресов Loopback0 интерфейсов с маской /20 из AS 41 в AS 51 c опцией NO\_EXPORT следующим образом:
   1. Создать Prefix List под названием AGGREGATE
   2. Создать Route Map под названием NO\_EXPORT
      1. Заматчить Prefix List под названием AGGREGATE
      2. Установить Community c опцией NO\_EXPORT
   3. Применить Route Map под названием NO\_EXPORT

