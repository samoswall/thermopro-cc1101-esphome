# thermopro-cc1101-esphome
Receiving measurements from the ThermoPro TX2 868 MHz sensor using the cc1101 module<br>
<br>
Прием и дешифровка сигналов от ThermoPro TX2 с помощью модуля cc1101 868 MГц<br>
<br>
<img src="https://github.com/samoswall/thermopro-cc1101-esphome/blob/main/ThermoPro.png" height="400" />
<img src="https://github.com/samoswall/thermopro-cc1101-esphome/blob/main/hass.png" height="400" />
<br><br>
Используется компонент для EspHome [https://github.com/gabest11/esphome-cc1101](https://github.com/gabest11/esphome-cc1101)
<br>
# Протокол
| 36&nbsp;бит | Длина  | Описание |
| ----------- | ------ | -------- |
| 0-3         | 4 бита | Тип сенсора (обычно 1001)|
| 4-11        | 8 бит  | Уникальный ID (Генерируется при установке батареек, зависит от их заряда, т.е. если вытащить и вставить батарейки, то ID не поменяется, если установить другие - то поменяется)|
| 12          | 1 бит  | 1 - Низкий заряд батареек, 0 - Заряд в норме|
| 13          | 1 бит  | 1 - Пакет принудительно отправлен нажатием на кнопку ТХ, 0 - периодический автоматический пакет|		
| 14-15       | 2 бита | Номер канала (выбирается переключателем)	00 - 1 канал, 01 - 2 канал,	10 - 3 канал|
| 16-27       | 12 бит | Температура * 10 (целое число со знаком)|
| 28-35       | 8 бит  | Влажность|


