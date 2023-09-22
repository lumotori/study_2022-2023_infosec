---
## Front matter
lang: ru-RU
title: Лабораторная работа 3
subtitle: Дискреционно еразграничение прав в Linux. Два пользователя
author:
  - Казакова Виктория Алексеевна
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 09 сентября 2023

## i18n babel
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


## Докладчик

:::::::::::::: {.columns align=center}
::: {.column width="70%"}
  * Казакова Виктория Алексеевна
  * студент кафедры математического модулирования и искусственного интеллекта
  * Российский университет дружбы народов
  * [1032201659@rudn.ru](mailto:1032201659@rudn.ru)
:::
::: {.column width="30%"}



:::
::::::::::::::
# Вводная часть


## Цели и задачи

- Получение практических навыков работы в консоли с атрибутами файлов
- Использование полученных навыков в прошлой лабораторной работе

## Материалы и методы

- Процессор `pandoc` для входного формата Markdown
- Операционная система `Centos 7.0`
- Сервис для хостинга IT-проектов `GitHub`
- Методические материалы

# Результаты выполнения работы

## Создание нового пользователя guest2, установка пароля на него. Добавление пользователя в группу.

![](image/1.png){#fig:001 width=70%}

![](image/2.png){#fig:002 width=70%}

## Осуществила вход в систему от двух пользователей. Для обоих пользователей командой pwd определила директорию, в которой она находится

![](image/3.png){#fig:003 width=70%}

![](image/4.png){#fig:004 width=70%}

## Уточнила имя пользователя (использовала команду whoami), его группу, кто входит в неё и к каким группам принадлежит он сам. Определите командами groups guest и groups guest2, в какие группы входят пользователи
![](image/5.png){#fig:005 width=70%}

![](image/6.png){#fig:006 width=70%}
##Сравнила полученную информацию с содержимым файла /etc/group.

![](image/7.png){#fig:07 width=70%}

# Вывод

В ходе выполнения работы, мы смогли приобрести практические навыки работы в консоли с атрибутами файлов для групп пользователей.
