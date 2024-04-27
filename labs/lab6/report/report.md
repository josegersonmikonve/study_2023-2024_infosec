---
## Front matter
title: "Лабораторная работа №6"
subtitle: "Основы Информационной Безопасности"
author: "НВЕ МАНГЕ ХОСЕ ХЕРСОН МИКО;   НКАбд-03-22."

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Развить навыки администрирования ОС Linux. Получить первое практическое знакомство с технологией SELinux.
Проверить работу SELinx на практике совместно с веб-сервером Apache.


# Задание

1. Подготовить рабочую среду;  
2. Выполнить основную часть работы;  
3. Сделать выводы.  

# Теоретическое введение

1. При подготовке стенда обратите внимание, что необходимая для работы и указанная выше политика targeted и режим enforcing используются в данном дистрибутиве по умолчанию, т.е. каких-то специальных настроек не требуется. При этом следует убедиться, что политика и режим включены, особенно когда работа будет проводиться повторно и велика вероятность изменений при предыдущем использовании системы.
2. При необходимости администратор должен разбираться в работе SELinux и уметь как исправить конфигурационный файл /etc/selinux/config, так и проверить используемый режим и
политику.
3. Необходимо, чтобы был установлен веб-сервер Apache. При установке системы в конфигурации «рабочая станция» указанный пакет не ставится.
4. В конфигурационном файле /etc/httpd/httpd.conf необходимо задать параметр ServerName: ServerName test.ru, чтобы при запуске веб-сервера не выдавались лишние сообщения об
ошибках, не относящихся к лабораторной работе.
5. Также необходимо проследить, чтобы пакетный фильтр был отключён или в своей рабочей конфигурации позволял подключаться к 80-у и 81-у
портам протокола tcp.
Отключить фильтр можно командами  
iptables -F  
iptables -P INPUT ACCEPT  
iptables -P OUTPUT ACCEPT  
либо добавить разрешающие правила:  
iptables -I INPUT -p tcp --dport 80 -j ACCEPT  
iptables -I INPUT -p tcp --dport 81 -j ACCEPT  
iptables -I OUTPUT -p tcp --sport 80 -j ACCEPT  
iptables -I OUTPUT -p tcp --sport 81 -j ACCEPT  
6. Обратите внимание, что данные правила не являются «точными» и рекомендуемыми на все случаи жизни, они лишь позволяют правильно организовать работу стенда.
7. В работе специально не делается акцент, каким браузером (или какой консольной программой) будет производиться подключение к вебсерверу. По желанию могут использоваться разные программы, такие
как консольные links, lynx, wget и графические konqueror, opera,
firefox или др.

# Выполнение лабораторной работы

Перед началом работы я обновила ПО (**yum update -y**, затем установила apache (**yum install httpd -y**).

Вошла в систему с и убедилась, что SELinux работает в режиме enforcing политики targeted с помощью команд **getenforce и sestatus** (рис. [-@fig:001]).

![Проверка работы SELinux](image/1.png){#fig:001 width=70%}

Чтобы работать с библиотекой httpd, скачала ее (рис. [-@fig:002]).

![Установка библиотеки](image/2.png){#fig:002 width=70%}

Убедилась, что веб-сервер работает при помощи утилиты **service httpd start** (рис. [-@fig:003]).

![Запустила работу Apache](image/3.png){#fig:003 width=70%}

Контекст безопасности - system_u:system_r (рис. [-@fig:004]).

![Проверка](image/4.png){#fig:004 width=70%}

Посмотрела текущее состояние переключателей SELinux для Apache с помощью команды **sestatus -b | grep httpd** (рис. [-@fig:005]).

![Текущее состояние переключателей](image/5.png){#fig:005 width=70%}

Посмотрела статистику по политике с помощью команды seinfo. Типы: 5135; пользователи: 8; роли: 15 (рис. [-@fig:006]).

![Статистика](image/6.png){#fig:006 width=70%}

Определила тип файлов и поддиректорий, находящихся в директории /var/www, с помощью команды **ls -lZ /var/www** (папки). Определила круг пользователей, которым разрешено создание файлов в директории /var/www/html (суперпользователю) (рис. [-@fig:007]).

![Папка www](image/7.png){#fig:007 width=70%}

Определила тип файлов, находящихся в директории /var/www/html утилитой **ls -lZ /var/www/html** (не отобразилось ничего) (рис. [-@fig:008]).

![Папка html](image/8.png){#fig:008 width=70%}

Создала html-файл /var/www/html/test.html  (рис. [-@fig:009]).

![Файл html](image/9.png){#fig:009 width=70%}

Проверила контекст созданного файла (httpd_sys_content_t) (рис. [-@fig:010]).

![Контекст](image/10.png){#fig:010 width=70%}

Обратилась к файлу через веб-сервер, введя в браузере адрес http://127.0.0.1/test.html. Файл был успешно отображён (рис. [-@fig:011]).

![Веб-страничка](image/11.png){#fig:011 width=70%}

Тип httpd_sys_content_t позволяет процессу httpd получить доступ к файлу. Благодаря наличию последнего типа мы получили доступ к файлу
при обращении к нему через браузер.
Изменила контекст файла /var/www/html/test.html с **httpd_sys_content_t** на **samba_share_t** с помощью утилиты **chcon -t samba_share_t /var/www/html/test.html**. Контекст поменялся (рис. [-@fig:012]).

![samba_share_t](image/12.png){#fig:012 width=70%}

Попробовала ещё раз получить доступ к файлу через веб-сервер. Ошибка :((  (рис. [-@fig:013]).

![Веб-страница](image/13.pmg){#fig:013 width=70%}

Проанализировала ситуацию. Файл не отображается, так как этот тип не позволяет процессу httpd получить доступ к файлу.
Также просмотрела системный лог-файл tail /var/log/messages (рис. [-@fig:014]).

![Лог-файл](image/14.png){#fig:014 width=70%}

Попробовала запустить веб-сервер Apache на прослушивание ТСР-порта 81. Для этого в файле /etc/httpd/httpd.conf поменяла строчку Listen 80 на Listen 81 (рис. [-@fig:015]).

![Изменение файла](image/15.png){#fig:015 width=70%}

Выполнила перезапуск веб-сервера Apache. Сбой не произошел....
Проанализировала лог-файлы tail -nl /var/log/messages, /var/log/http/error_log, /var/log/http/access_log и /var/log/audit/audit.log  (рис. [-@fig:016]), (рис. [-@fig:017]), (рис. [-@fig:018]).

![Лог](image/16.png){#fig:016 width=70%}

![Лог](image/17.png){#fig:017 width=70%}

![Лог](image/18.png){#fig:018 width=70%}

Выполнила команду **semanage port -a -t http_port_t -р tcp 81**, проверила список портов командой **semanage port -l | grep http_port_t** (рис. [-@fig:019]).

![Настройка порта 81](image/16.npg){#fig:019 width=70%}

Попробовала запустить веб-сервер Apache ещё раз. Не сработало.... (рис. [-@fig:020]).

![Веб-страница](image/17.png){#fig:020 width=70%}

Вернула контекст httpd_sys_cоntent__t к файлу /var/www/html/ test.html.  
После этого попробовала получить доступ к файлу через веб-сервер (рис. [-@fig:021]).

![Веб-страница](image/18.png){#fig:021 width=70%}

Исправила обратно конфигурационный файл apache, вернув Listen 80.
Удалила привязку http_port_t к 81 порту, но появилась ошибка, что этот порт удалить невозможно, даже через суперпользователя.  
Удалила файл /var/www/html/test.html (рис. [-@fig:022]).

![Уаление](image/19.png){#fig:022 width=70%}

# Выводы

Я развила навыки администрирования ОС Linux, получила первое практическое знакомство с технологией SELinux.

