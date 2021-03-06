---
description: 'Цикл 5. Тема 27: RIPv2 3.4'
---

# Лабораторная по теме 27

{% file src="../../.gitbook/assets/lab027.zip" caption="Начальная конфигурация" %}

Задание \#1 для лабораторной:  
1. Загрузить начальную конфигурацию SW1, SW2, SW3, SW4, R1, R2, R3, R4, R5, R6, R7, R8, R9, R10.  
2. Настроить на всех маршрутизаторах протокол ripv2 для сетей 180.1.0.0 и 188.1.0.0 и отключить автоматическую суммаризацию сетей.  
3. Проверить что все сети на маршрутизаторах анонсированы и решить проблему в случае, если нет каких-то маршрутов  
4. Маршрутизаторы R3 и R5 настроить таким образом, чтобы они не отправляли RIP сообщения для сегмента сети на интерфейсе E0/1.235, но при этом сохранили возможность получать RIP сообщения от маршрутизатора R2 по этому интерфейсу.  
5. Сформируйте отправляемые от R8 к R7 маршруты так, чтобы они содержали минимальное количество информации для доступа к подсетям, но так чтобы минимально повлиять на маршруты до Loopback интерфейсов других маршрутизаторов: 188.1.89.0\24, 188.1.109.0\24, 188.1.9.0\24, 188.1.10.0\24, 180.1.10.10\32, 180.1.9.9\32, 180.1.8.8\32  
6. Маршрутизатор R1 должен иметь только один общий маршрут, полученный по RIP для получения доступа до всей остальной части сети. Не использовать фильтрацию маршрутов.  
7. Настройте статический маршрут 10.10.10.0/24 на R6 в сторону R7 c отправив его в Null0. Редистрибьютьте его в RIP.  
8. На R2 настроить offset-list таким образом, чтобы трафик до R3 отправлялся через интерфейс E0/1.23  
9. На R6 настроить offset-list таким образом, чтобы маршрут 10.10.10.0 шел не дальше R3  
10. Настроить prefix-list на R6 таким образом, чтобы маршрут 180.1.2.2 не передавался в update rip на всех интерфейсах.

{% file src="../../.gitbook/assets/lab027\_answers.zip" caption="Конечная конфигурация" %}

