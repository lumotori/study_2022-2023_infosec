---
## Front matter
title: "Отчет по лабораторной работе №1"
subtitle: "Установка и конфигурация операционной системы на виртуальную машину"
author: "Казакова Виктория Алексеевна"

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

# Poccийскийский университет дружбы народов
### Отчёт по лабораторной работе № 1
### Дисциплина : Информационная безопасность
##### Студент: Казакова Виктория Алексеевна 1032201659
##### Группа: НФИбд-01-20
---
#### Цель работы

##### Целью данной работы является приобретение практических навыков
установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов.
---
#### Ход работы
1. Установила виртуальную машину (Oracle) и операционную систему (Centos)
2. Создала виртуальную машину, ввела все необходимые значения: объем памяти, количество ядер процессора, тип и формат жесткого диска (рис.1-3)(рис.1 @fig:001) (рис.2 @fig:002) (рис.3 @fig:003) 

![Создание виртуальной машины 1](image/1.png){#fig:001 width=70%}

![Создание виртуальной машины 2](image/2.png){#fig:002 width=70%}

![Создание виртуальной машины 3](image/3.png){#fig:003 width=70%}

3. Установила центос (рис.4 @fig:004)
   
![Установка образа](image/4.png){#fig:004 width=70%}

Установка центос (рис.5 @fig:005)
   
![Установка образа](image/5.png){#fig:005 width=70%}

4. Настройка образа.
- Выбор языка (рис.6 @fig:006)
   
![Выбор языка](image/6.png){#fig:006 width=70%}

- Обзор установки (рис.7 @fig:007)
   
![Меню установки](image/7.png){#fig:007 width=70%}

- Выбор даты и времени (рис.8 @fig:008)
   
![Выбор даты и времени](image/8.png){#fig:008 width=70%}

- Выбор приоритетной раскладки (рис.9 @fig:009)
   
![Выбор раскладки](image/9.png){#fig:009 width=70%}

- Выбор предварительной установки программ (рис.10 @fig:010)
   
![Выбор программ](image/10.png){#fig:010 width=70%}

- Выбор kdump (рис.11 @fig:011)
   
![Выбор kdump](image/11.png){#fig:011 width=70%}

- Сеть и имя узла (рис.12 @fig:012)
   
![Сеть и имя узла](image/12.png){#fig:012 width=70%}

5. Установка образа действий дополнительной гостевой ОС (рис.13 @fig:013)
   
![Установка образа](image/13.png){#fig:013 width=70%}

6. Осуществила поиск в терминале информацию по пк (рис.14 @fig:014)
   (рис.15 @fig:015)
   
![Поиск версии ядра](image/14.png){#fig:014 width=70%}(рис.5 @fig:005)
   
![Поиск остальной информации](image/15.png){#fig:015 width=70%}

---
#### Вывод
##### Приобрела практические навыки установки операционной системы на виртуальную машину, настроила минимально необходимые для дальнейшей работы сервисов.
