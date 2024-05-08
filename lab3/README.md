# Лабораторная работа 3

**Название:** "Разработка драйверов сетевых устройств"

**Цель работы:** получить знания и навыки разработки драйверов сетевых
интерфейсов для операционной системы Linux

## Описание функциональности драйвера

1.1. Драйвер должен создавать виртуальный сетевой интерфейс в ОС
Linux.
1.2. Созданный сетевой интерфейс должен перехватывать пакеты
родительского интерфейса (eth0 или другого).
1.3. Сетевой интерфейс должен реализовывать логику работы с
перехваченным трафиком в соответствии с заданиями по
вариантам.
1.4. Должна иметься возможность просмотра статистики работы
созданного интерфейса.

UDP пакеты длиной больше 100 байт. Вывести длину.
Состояние разбора пакетов необходимо выводить в кольцевой
буфер ядра.

## Инструкция по сборке

* make - скомпилировать проект
* make load - загрузить модуль в ядро линукс


## Инструкция пользователя

make  
make load  
echo -n "данные" | nc -u -w1 192.168.1.50 22  
dmesg

## Примеры использования

root@zc2:~/OlegSh# make  
root@zc2:~/OlegSh# make load  
sudo insmod lab3.ko
root@zc4:~# echo -n "My udp packet bbbbbyyyeraradsfafh;af21sdafasdfasdfdfsahfjkasdfhsadfhafldhakfjdhalskjfdhasdfkadfhslhfdjklsahflahsfjaflashfdljkasfdhkfhdsjkfhsakfhsaj;adfh;sadfhklsadhjlfasdfklsahfjkdshaklfsa" | nc -u -w1 192.168.1.50 22  
root@zc4:~# echo -n "My udp packet" | nc -u -w1 192.168.1.50 22  
root@zc4:~# echo -n "My udp packet" | nc -u -w1 192.168.1.50 22  
root@zc4:~# echo -n "My udp packet bbbbbyyyeraradsfafh;af21sdafasdfasdfdfsahfjkasdfhsadfhafldhakfjdhalskjfdhasdfkadfhslhfdjklsahflahsfjaflashfdljkasfdhkfhdsjkfhsakfhsaj;adfh;sadfhklsadhjlfasdfklsahfjkdshaklfsa" | nc -u -w1 192.168.1.50 22  
root@zc2:~/OlegSh# dmesg  
[ 4423.906649] Captured UDP datagram, saddr: 192.168.1.86[ 4423.906675] daddr: 192.168.1.50  
[ 4423.906684] Data length: 188. Data:[ 4423.906694] My udp packet bbbbbyyyeraradsfafh;af21sdafasdfasdfdfsahfjkasdfhsadfhafldhakfjdhalskjfdhasdfkadfhslhfdjklsahflahsfjaflashfdljkasfdhkfhdsjkfhsakfhsaj;adfh;sadfhklsadhjlfasdfklsahfjkdshaklfsa  
[ 4512.722508] Captured UDP datagram, saddr: 192.168.1.86[ 4512.722533] daddr: 192.168.1.50  
[ 4512.722542] Data length: 188. Data:  
