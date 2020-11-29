Сайт выбранный для экспериментов: itrobo.ru

Комманды помогающие найти ip - ping и nslookup
![2020-11-25 10_20_04-Командная строка — копия](https://user-images.githubusercontent.com/70691216/100554200-22837d00-32a4-11eb-85cd-5f7dedbae7f4.png)
ip адрес - 141.8.194.64

nslookup -query=mx
![2020-11-25 10_23_18-Командная строка](https://user-images.githubusercontent.com/70691216/100554278-a9d0f080-32a4-11eb-8596-9fac21b30cd5.png)
Помогает узнать серверную почту - mail.itrobo.ru

nslookup -query=soa
![2020-11-25 10_23_18-Командная строка](https://user-images.githubusercontent.com/70691216/100554278-a9d0f080-32a4-11eb-8596-9fac21b30cd5.png)
Помогает узнать первичное название сервера, почта администратора сервера домена, серийный номер, период времени, через который вторичный DNS-сервер отправит запрос первичному, с целью проверки, поменялся ли серийный номер. Интервал для повторного соединения с первичным DNS-сервером

nslookup -query=nx показало ip и адрес, а nslookup -type=any не удалось найти
![2020-11-25 10_25_52-Командная строка](https://user-images.githubusercontent.com/70691216/100554445-be61b880-32a5-11eb-89f8-74147ea1d1db.png)

С помощью wireshark я попытлся изучить трафик сайта, но он ничего не выдавал, поэтому я поменял сайт на kombik.com ip: 94.130.37.108, с помощью комманд ip.src и ip.dst у меня выдавало практически одно и тоже 
![2020-11-25 13_45_58-Photos](https://user-images.githubusercontent.com/70691216/100554540-5a8bbf80-32a6-11eb-9916-0275b5fb7c26.png)
![2020-11-25 13_45_58-Photos](https://user-images.githubusercontent.com/70691216/100554540-5a8bbf80-32a6-11eb-9916-0275b5fb7c26.png)
ip.dst отвечает за отправленный трафик на этот ip

ip.addr отвечает за фильтрацию трафика, в котором упоминается этот ip 
![2020-11-25 13_48_01-Photos](https://user-images.githubusercontent.com/70691216/100554624-de45ac00-32a6-11eb-82d1-de9dffbd6a5d.png)

upd.src у меня не стал работать, поэтому его тут нет

arp.src.hw_mac используется для фильтрации по arp протокола по mac адресу
![2020-11-25 13_49_42-Photos](https://user-images.githubusercontent.com/70691216/100554650-10efa480-32a7-11eb-97de-f364bbb713ed.png)

eth.dst - фильтр трафика по mac адресу получателя
![2020-11-25 13_50_37-Photos](https://user-images.githubusercontent.com/70691216/100554679-46948d80-32a7-11eb-9a8c-f847ccd47095.png)

eth.src - фильтр трафика по mac адресу отправителя
![2020-11-25 13_51_34-Photos](https://user-images.githubusercontent.com/70691216/100554688-59a75d80-32a7-11eb-99df-059f60e5ba65.png)
