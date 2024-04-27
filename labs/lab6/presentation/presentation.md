---
## Front matter
lang: ru-RU
title: Лабораторная работа №6
subtitle: Информационная безопасность
author:
  - НВЕ МАНГЕ ХОСЕ ХЕРСОН МИКО
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 12.03.2024

## i18n babel
babel-lang: russian
babel-otherlangs: english

## Formatting pdf
toc: false
toc-title: Содержание
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
 - '\makeatletter'
 - '\beamer@ignorenonframefalse'
 - '\makeatother'
---
# Информация

:::::::::::::: {.columns align=center}
::: {.column width="70%"}

  * НВЕ МАНГЕ ХОСЕ ХЕРСОН МИКО
  * Студент, НКАбд-03-22
  * Российский университет дружбы народов
  * [1032225355@pfur.ru](mailto: 1032225355@pfur.ru)

:::
::: {.column width="30%"}

![](./image/photo.jpg)

:::
::::::::::::::

# Цель работы

Целью работы является изучение механизмов изменения идентификаторов, применения SetUID- и Sticky-битов.

# Подготовка к выполнению работы

![Проверка установки ПО](image/0.png){#fig:000 width=70%}

##

![setenforce 0](image/1.png){#fig:001 width=70%}

# Выполнение лабораторной работы

## Создание программы

![Вход в систему от другого пользователя](image/2.png){#fig:002 width=70%}

## Создание программы

![Заполнение элементарной программы](image/4.png){#fig:004 width=70%}

## Создание программы

![Компиляция и запуск программы](image/6.png){#fig:006 width=70%}

## Создание программы

![Команда id](image/7.png){#fig:007 width=70%}

## Создание программы

![Заполнение программы](image/8.png){#fig:008 width=70%}

## Создание программы

![Компиляция и запуск программы](image/9.png){#fig:009 width=70%}

## Создание программы

![Поменяла владельца программы](image/10.png){#fig:010 width=70%}

## Создание программы

![ls -l](image/11.png){#fig:011 width=70%}

## Создание программы

![Сравнение результатов](image/12.png){#fig:012 width=70%}

## Создание программы

![Создание программы](image/13.png){#fig:013 width=70%}

## Создание программы

![Компиляция программы](image/14.png){#fig:014 width=70%}

## Создание программы

![Смена владельца](image/15.png){#fig:015 width=70%}

## Создание программы

![Результат работы программы](image/16.png){#fig:016 width=70%}

##  Исследование Sticky-бита

![Выполнение задач](image/17.png){#fig:017 width=70%}

##  Исследование Sticky-бита

![Работа с файлами](image/18.png){#fig:018 width=70%}

##  Исследование Sticky-бита

![Работа с атрибутом t](image/19.png){#fig:019 width=70%}

##  Исследование Sticky-бита

![Возвращение Sticky](image/20.png){#fig:020 width=70%}

# Выводы

Я изучила механизмы изменения идентификаторов, применения SetUID- и Sticky-битов. Полученила практических навыков работы в консоли с дополнительными атрибутами.

