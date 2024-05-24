# Promiscuous mode

## Windows
Включение:
```shell
netsh interface set interface "Ethernet" admin=enable
```
Отключение:
```shell
netsh interface set interface "Ethernet" admin=disable
netsh interface set interface "Ethernet" admin=enable
```
Меняем `"Ethernet"` на имя вашего сетевого интерфейса.

## macOS
Включение:
```shell
sudo ifconfig en0 promisc
```
Отключение:
```shell
sudo ifconfig en0 -promisc
```
Меняем `en0` на имя вашего сетевого интерфейса.

## Linux
Включение:
```shell
sudo ifconfig eth0 promisc
```
Отключение:
```shell
sudo ifconfig eth0 -promisc
```
Меняем `eth0` на имя вашего сетевого интерфейса.

