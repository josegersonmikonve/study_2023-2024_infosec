---
## Front matter
title: "Шаблон отчёта по лабораторной работе"
subtitle: "Простейший вариант"
author: "Дмитрий Сергеевич Кулябов"

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

1. Скачать необходимое ПО (Virtual Box, Kali);
2. Настроить опции в соответствии с требованиями;

# Теоретическое введение

Лабораторная работа подразумевает установку на виртуальную машину VirtualBox (https://www.virtualbox.org/) операционной системы Linux (дистрибутив Kali).


# Выполнение лабораторной работы

Поскольку у меня уже имелся Virtual Box,  я перехожу к скачиванию образа ISO и одновременно с этим начинаю создание виртуальной системы. Даю машине имя и при этом не загружаю сразу образ ISO. Это лучше сделать после первоначальной настройки. В разделе "Оборудование" выставляю основной памяти 2048Мб (рис. [-@fig:000]), (рис. [-@fig:001]), (рис. [-@fig:002])

![Скачивание образа](image/0.png){#fig:000 width=70%}

![Оборудование](image/1.png){#fig:001 width=70%}

![ОЗУ и процессоры](image/2.png){#fig:002 width=70%}

Выбираю графическую настройку в меню Кали (рис. [-@fig:003]).

![Меню оболочек](image/3.png){#fig:003 width=70%}

Устанавливаю образ ISO в меню настроек машины (рис. [-@fig:004]).

![Настройки носителя](image/4.png){#fig:004 width=70%}

Выбираю Английский язык и перехожу в настройки домена сети. Я указала случайное выбранное имя домена, его потом можно будет поменять в настройках (рис. [-@fig:005]), (рис. [-@fig:006]).

![Язык](image/5.png){#fig:005 width=70%}

![Домен](image/6.png){#fig:006 width=70%}

Устанавливаю имя системы  (рис. [-@fig:007]).

![Имя системы](image/7.png){#fig:007 width=70%}

В меню "Разделение диска" выбираю "Использование всего диска"  (рис. [-@fig:008]).

![Partition](image/8.png){#fig:008 width=70%}

Устанавливаю логин для входа в систему (рис. [-@fig:009]).

![Логин](image/9.png){#fig:009 width=70%}

Выбираю программное обеспечение (рис. [-@fig:010]).

![ПО](image/10.png){#fig:010 width=70%}

Установка готова (рис. [-@fig:011]).

![Готово!](image/11.png){#fig:011 width=70%}

# Выводы

Я приобрела практические навыки установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов.

::: {#refs}
:::
