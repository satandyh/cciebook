---
description: 'Цикл 5. Тема 29: NTP 8.3'
---

# Лабораторная по теме 29

{% file src="../../.gitbook/assets/lab029.zip" caption="Начальная конфигурация" %}

Задание \#1 для лабораторной:  
1. Загрузить начальную конфигурацию SW1, SW2, SW3, SW4, R1, R2, R3, R4, R5, R6, R7, R8, R9, R10.  
2. На всех маршрутизаторах настроить протокол маршрутизации RIP версии 2, отключить автосуммаризацию. Если есть проблемы с маршрутизацией, решить ее.  
3. Назначить R10 NTP сервером и настроить часовой пояс по МСК +00.  
4. Настроить R1, R4, R5, R6, R7, R8, R9 для синхронизации времени от R10, используя соответствующий Source интерфейс.  
5. Настроить R3 для синхронизации времени от R10, используя Source интерфейс E0/1.34 как основной, а интерфейс E0/1.235 как дополнительный  
6. Настроить R2 для синхронизации времени от R10, используя Source интерфейс E0/1.23 как основной, а интерфейс E0/1.235 как дополнительный.  
7. На всех маршрутизаторах настроить аутентификацию NTP с номером ключа 1 и паролем CCIEinaYEAR  
8. На всех клиентских маршрутизаторах настроить access-list с названием NTP\_SERVER для доверенного сервера NTP R10.  
9. На R10 настроить access-list с названием NTP\_CLIENTS с указанием диапазона адресов клиентов для синхронизации времени.

{% file src="../../.gitbook/assets/lab029\_answers.zip" caption="Конечная конфигурация" %}

