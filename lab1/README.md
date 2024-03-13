# Лабораторная работа 1

**Название:** "Разработка драйверов символьных устройств"

**Цель работы:** ...

## Описание функциональности драйвера

При записи текста в файл символьного устройства должен осуществляться подсчет введенных цифр. Последовательность полученных результатов (количество цифр) с момента загрузки модуля ядра должна выводиться при чтении файла.

## Инструкция по сборке

make


## Инструкция пользователя

sudo insmod ch_drv.ko
echo "1234" | sudo tee \dev\var6
cat \dev\var6
sudo rmmod ch_drv

## Примеры использования

oleg@oleg-VirtualBox:~/newrep/lab1$ sudo rmmod ch_drv
oleg@oleg-VirtualBox:~/newrep/lab1$ sudo insmod ch_drv.ko
oleg@oleg-VirtualBox:~/newrep/lab1$ 
oleg@oleg-VirtualBox:~/newrep/lab1$ echo "1234" | sudo tee /dev/var6 
1234
oleg@oleg-VirtualBox:~/newrep/lab1$ sudo cat /dev/var6 
Digits count: 4

