---
description: 'Цикл 6, Тема 31: STP 1.4'
---

# Лабораторная по теме 31

{% file src="../../.gitbook/assets/lab031.zip" caption="Начальная конфигурация" %}

Задание \#1 для лабораторной:  
1. Загрузить начальную конфигурацию R1, R4, SW1, SW2, SW3, SW4.  
2. Перевести все коммутаторы в режим работы RSTP.  
3. Назначить SW1 Root Bridge используя команду root primary для vlan 10, определив максимальное количество коммутаторов между R1 и R4 равное 4.  
4. Назначить SW4 Secondary Root Bridge используя команду root secondary для vlan 10, определив максимальное количество коммутаторов между R1 и R4 равное 4.  
5. Выполнить следующие настройки на всех коммутаторах для vlan 10:  
• Уменьшить время отправки на половину от значения по умолчанию.  
6. Порты E0/0 на SW1 и SW4 коммутаторах перевести в режим, в котором при изменении состояния порта не будет отправляться TCN.  
7. Порты E0/0 на SW1 и SW4 коммутаторах настроить таким образом, чтобы при получении BPDU они переходили в режим Error disable.  
8. На SW1 и SW4 настроить время восстановления портов, попавших под режим Error disable вследствии получения BPDU за 30 секунд.  
9. Порты E0/0 на SW1 и SW4 коммутаторах настроить таким образом, чтобы при получении Superior BPDU они переставали передавать трафик.  
10. Перевести все активные порты на коммутаторах в режим работы point-to-point.

{% file src="../../.gitbook/assets/lab031\_answers.zip" caption="Конечная конфигурация" %}

