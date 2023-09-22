---
## Front matter
title: "Отчет по лабораторной работе №3"
subtitle: "Дискреционное разграничение прав в Linux. Два пользователя"
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

# Цель работы

### Получение практических навыков работы в консоли с атрибутами файлов для групп пользователей.
---
1. В установленной при выполнении предыдущей лабораторной работы операционной системе создала учётную запись пользователя guest (использую учётную запись администратора) (рис. @fig:001)
   
![Создание учетной записи пользователя guest](image/1.png){#fig:001 width=70%}

2. Задала пароль для пользователя guest (использую учётную запись администратора)(рис. @fig:002)

![Создание пароля для учетной записи](image/2.png){#fig:002 width=70%}

3. Вошла в систему от имени пользователя guest.
4. Определила директорию, в которой нахожусь, командой pwd. Определила, что она является домашней (рис. @fig:003) 

![Определение директории](image/3.png){#fig:003 width=70%}

5. Уточнила имя пользователя командой whoami (рис. @fig:004)
   
![Уточнение имени пользователя](image/4.png){#fig:004 width=70%}

6. Уточните имя пользователя, его группу, а также группы, куда входит пользователь, командой id. (рис. @fig:005)

![Использование команды id](image/5.png){#fig:005 width=70%}

7. Сравнила вывод id с выводом команды groups. Выяснила, что на эту команду выводить только имя пользователя (рис. @fig:006)
   
![Вывод команды groups](image/6.png){#fig:006 width=70%}

8. Просмотреть файл /etc/passwd командой cat и найти в нем свою учетную запись. Определила uid, gid пользователя. Сравнила найденные значения с полученными в предыдущих пунктах. Они совпали.(рис. @fig:007)
   
![Просмотр файла](image/7.png){#fig:007 width=70%}
