---
## Front matter
title: "Лабораторная работа № 4"
subtitle: "Дискреционное разграничение прав в Linux. Расширенные атрибуты"
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

### Получение практических навыков работы в консоли с расширенными атрибутами файлов.
---
1. От имени пользователя guest определила расширенные атрибуты файла /home/guest/dir1/file1 командой lsattr /home/guest/dir1/file1. (рис. @fig:001)
   
![Определение расширенных атрибутов](image/1.png){#fig:001 width=70%}

2. Установила командой chmod 600 file1 на файл file1 права, разрешающие чтение и запись для владельца файла. (рис. @fig:002)

![Установка прав](image/2.png){#fig:002 width=70%}

3. Попробовала установить на файл /home/guest/dir1/file1 расширенный атрибут a от имени пользователя guest: chattr +a /home/guest/dir1/file1 В ответ получила отказ от выполнения операции.(рис. @fig:003) 

![Попытка установки расширенного атрибута](image/3.png){#fig:003 width=70%}

4. Повысила свои права с помощью команды su. Установила расширенный атрибут a на файл /home/guest/dir1/file1 от имени суперпользователя:(рис. @fig:004)
   
![Использование команды su. Установка расширенного атрибута](image/4.png){#fig:004 width=70%}

5. От пользователя guest проверила правильность установления атрибута. (рис. @fig:005) 

![Проверка установленного атрибута](image/5.png){#fig:005 width=70%} 

6. Выполнила дозапись в файл file1 слова «test» командой echo "test" /home/guest/dir1/file1 (рис. @fig:006). После этого выполнила чтение файла file1 командой cat /home/guest/dir1/file1 (рис. @fig:007). Убедилась, что слово test было успешно записано в file1 (рис. @fig:008).

![Дозапись файла](image/6.png){#fig:006 width=70%}

![Чтение файла](image/7.png){#fig:007 width=70%}

![Проверка записи слова test](image/8.png){#fig:008 width=70%}

7. Попробовала удалить файл file1 командой rm (рис. @fig:010). Попробовала стереть имеющуюся в нём информацию командой echo "abcd" > /home/guest/dirl/file1 (рис. @fig:009). Попробовала переименовать файл командой mv (рис. @fig:011).

![Попытка стереть содержимое файла](image/10.png){#fig:010 width=70%}

![Попытка удаления файла](image/9.png){#fig:009 width=70%}

![Попытка переименовать файл](image/11.png){#fig:011 width=70%}

8. 

---
# Выводы

В ходе выполнения работы, мы смогли приобрести практические навыки работы в консоли с атрибутами файлов для групп пользователей.

# Библиография

1. [Методический материал] https://esystem.rudn.ru/pluginfile.php/2090275/mod_resource/content/4/003-lab_discret_2users.pdf
2. [Методический материал] https://esystem.rudn.ru/pluginfile.php/2090273/mod_resource/content/6/002-lab_discret_attr.pdf
