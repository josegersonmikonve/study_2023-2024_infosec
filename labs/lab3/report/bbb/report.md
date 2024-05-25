---
## Front matter
title: "Лабораторная работа №3"
subtitle: "Основы информационной безопасности"
author: "НВЕ МАНГЕ ХОСЕ ХЕРСОН МИКО"

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

Целью работы является получение практических навыков работы в консоли с атрибутами файлов для групп пользователей.


# Выполнение лабораторной работы

Создаю пользователя guest2 и задаю ему пароль (рис. [-@fig:001]). Пользователь guest у меня уже создан.

![Создание guest2](image/1.png){#fig:001 width=70%}

Добавляю пользователя guest2 в группу guest (рис. [-@fig:003]).

![Добавление в группу guest](image/2.png){#fig:003 width=70%}

Затем осуществляю вход в систему от двух пользователей на двух консолях через команду **su -** (рис. [-@fig:004]).

![Вход в систему](image/3.png){#fig:004 width=70%}

Для обоих пользователей определяю директорию командой pwd. Все совпадает. Так же уточняю имя моего пользователя, его группу и кто входит в нее и к каким группам принадлежит. Сравниваю полученную информацию с содержимым файла /etc/group. Всё совпадает (рис. [-@fig:005]),(рис. [-@fig:006]).

![Сравнение](image/4.png){#fig:005 width=70%}


![Сравнение](image/4.1.png){#fig:006 width=70%}

От имени пользователя guest2 выполняю регистрацию пользователя guest2 в группе guest командой **newgrp guest** (рис. [-@fig:007]).

![Регистрация guest2 в группе guest](image/5.png){#fig:007 width=70%}

От имени пользователя guest изменяю права директории /home/guest, разрешив все действия для пользователей группы (рис. [-@fig:008]).

![Разрешаю все действия](image/6.png){#fig:008 width=70%}

От имени пользователя guest снимаю с директории /home/guest/dir1 все атрибуты командой **chmod 000 dir1** (рис. [-@fig:009]).

![Снятие с директории /home/guest/dir1 всех атрибутов](image/7.png){#fig:009 width=70%}

# Выводы

Я получила практические навыки работы в консоли с атрибутами файлов для групп пользователей.


