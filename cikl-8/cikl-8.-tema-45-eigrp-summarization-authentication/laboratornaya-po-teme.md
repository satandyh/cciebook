---
description: 'Цикл 8. Тема 45: EIGRP Summarization, Authentication'
---

# Лабораторная по теме 45

{% file src="../../.gitbook/assets/lab045.zip" caption="Начальная конфигурация" %}

1. Загрузить начальную конфигурацию всех устройств.
2. Для задания используется логическая и физическая топологии проекта.
3. На маршрутизаторах R6, R7, R8, R9, R10 настроить classic mode EIGRP следующим образом:
   * Номер автономной системы 100
   * Аннонсировать сети 188.1.0.0 и 180.1.0.0
   * Отключить автосуммаризацию
   * Отключить на маршрутизаторах аннонсирование EIGRP пакетов, туда где в них нет необходимости.
   * Настроить аутентификацию на интерфейсах, подключенных к маршрутизаторам Classic Mode следующим образом:
     * Название ключа CLASSIC\_MODE
     * Номер ключа 1
     * Пароль CLASSIC
   * Настроить аутентификацию на интерфейсах, подключенных к маршрутизаторамс Named Mode следующим образом:
     * Название ключа CLASSIC\_NAMED
     * Номер ключа 2
     * Пароль CLASSIC NAMED
4. На маршрутизаторах R1, R2, R3, R4, R5 настроить Named mode EIGRP следующим образом:
   * Имя NAMEDEIGRP
   * Номер автономной системы 100
   * Аннонсировать сети 188.1.0.0 и 180.1.0.0
   * Отключить автосуммаризацию
   * Настроить аутентификацию на интерфейсах, подключенных к маршрутизаторам с Named Mode следующим образом:
     * Пароль NAMED, зашифрованный уровнем 7
   * Настроить аутентификацию на интерфейсах, подключенных к маршрутизаторам с Classic Mode следующим образом:
     * Название ключа CLASSIC\_NAMED
     * Номер ключа 2
     * Пароль CLASSIC NAMED
5. На всех маршрутизаторах изменить ограничение по хопам от 100 до 200
6. На маршрутизаторе R9 суммаризировать все loopback маршруты в сторону R10
7. На маршрутизаторе R2 настроить маршрут суммарный маршрут по умолчанию в сторону R1.
8. На маршрутизаторе R2 настроить summary-metric со значениями метрик в 1 , применить ее на маршрут по-умолчанию. После всех произведенных действий добиться, чтобы R1 мог использовать маршрут по-умолчанию.

{% file src="../../.gitbook/assets/lab045\_answers.zip" caption="Конечная конфигурация" %}

