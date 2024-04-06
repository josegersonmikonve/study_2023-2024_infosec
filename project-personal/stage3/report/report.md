---
## Front matter
title: "Индивидуальный проект этап 3"
subtitle: "Использование Hydra"
author: "НВЕ МАНГЕ ХОСЕ ХЕСОН МИКО; НКАбд-03-22"

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

Попробовать в действии Hydra.

# Выполнение работы

1. Используем пример из задания для работы с Hydra.

![пример из задания](image/1.png){#fig:001 width=70%}

2. Изучим атаку Username/password и атаку Password Spraying в Hydra.

![классические атаки в Hydra](image/2.png){#fig:002 width=70%}

3. Изучим атаку Dictionary в Hydra, как классический вид брутфорс атаки.

![атака Dictionary в Hydra](image/3.png){#fig:003 width=70%}

4. Изучим основные способы защиты от атак Hydra.

![способы защиты от Hydra атак](image/4.png){#fig:004 width=70%}

# Выводы

Я попробовал в действии Hydra.

# Список литературы{.unnumbered}

Кулябов Д.С. "Материалы к учебному проекту"
ROD TRENT - Using Kali Linux and Hydra for Attack Testing and Alert Generation, 2023.
