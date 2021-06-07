# juniper-srx100

| Structure | Состав |

Config-juniper.txt - settings for juniper

README.md - readme

FAQ - en.md - instruction in english

FAQ - ru.md - интсрукция на русском


__________________________________________________________________________________________________________________________________________


EN: The minimum config for Juniper-SRX100B from the series so that at least there is a connection (with a description of the parameters).  


Symbols and abbreviations


LAN - local area network

vlan - virtual local area network

***.***.***.*** - this is the address of the provider

/** - Subnet mask

***** - port



ATTENTION!!! Before using it is recommended to remove all comments in the code, lines start with ##


These settings were used for a uniper that works as a router in a network where there are many vlan,
and the device itself connects to the provider's gateway through the fe0 / 0/0 port and fe0 / 0/1 looks at the LAN network.

As an example, the LAN address was 192.168.0.0
The DNS server has the address 192.168.10.3 because the local network has its own DNS server (but you can use any other one, for example 8.8.8.8)
VLANs 10 to 101 were created

An ssh root connection is configured, but it is better of course to deny and use only the previously created new user for security
Enabled web page access by login and password root or created user (attention to connect to the web page is possible only from the LAN)


route 0.0.0.0/0 next-hop ***.***.***.***; - this line means that all packets from the local network from all devices that need access to
                                             Internet will be sent to the provider's gateway (***.***.***.*** is the provider's gateway address).
                                             Any path for traffic can be configured.
                                             
Ports for connecting to the device from outside using the rdp protocol have been forwarded (this is not safe and it is not recommended to do this !!!)


3 zones configured (zone names can be any)


untrust_internet - internet zone

trust_zone - local trust zone

trust_zone1 - local trust zone 1


__________________________________________________________________________________________________________________________________________


RU: Минимальный конфиг для Juniper-SRX100B из серии что бы хоть была связь (с описанием параметров).


Обозначения и сокращения


LAN - локальная сеть

vlan - виртуальная локальная сеть

***.***.***.*** - так обозначается адрес провайдера

/** - маска подсети 

***** - порт



ВНИМАНИЕ!!! Пред использование рекомендуется убрать всё коментарии в коде, строки начинаются с ##


Данные настройки использовались для юнипера который работает вроли роутера в сети где есть множество vlan, 
а само устройство подключается к шлюзу провайдеру через порт fe0/0/0 а fe0/0/1 смотрит в LAN сеть.

В качестве примера адрес сети LAN был 192.168.0.0
DNS сервер имеет адрес 192.168.10.3 поскольку в локальной сети настроен свой DNS сервер (но можно использовать и любой другой, например 8.8.8.8)
Были созданы VLAN с 10 по 101 

Настроено подключение по ssh root, но лучше конечно запретить и использовать только созданого ранее нового пользователя для безопасности
Включена веб страница доступ по логину и паролю root или созданного пользователя (внимание подключение к веб странице возможно только из LAN)

route 0.0.0.0/0 next-hop ***.***.***.***;  - данная строка означает что все пакеты из локальной сети от всех устройств которым нужен доступ в 
                                             интернет будут отправлять на шлюз провайдера (***.***.***.*** - адрес шлюза провайдера).
                                             Можно настроить любой путь для трафика.
                                             
Проброшены порты для подключение к устройству из вне по протоколу rdp (это не безопасно и не рекомендуется это делать!!!)


Настроены 3 зоны (названия зон могут быть любыми)


untrust_internet - зона интернета

trust_zone - локальная доверительная зона

trust_zone1 - локальная доверительная зона 1
