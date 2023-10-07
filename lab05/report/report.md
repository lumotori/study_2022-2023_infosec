---
## Front matter
title: "Лабораторная работа № 5"
subtitle: "Дискреционное разграничение прав в Linux.  Исследование влияния дополнительных атрибутов"
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

### Изучение механизмов изменения идентификаторов, применения SetUID- и Sticky-битов. Получение практических навыков работы в консоли с дополнительными атрибутами. Рассмотрение работы механизма смены идентификатора процессов пользователей, а также влияние бита Sticky на запись и удаление файлов.
---
1. Подготовила лабораторный стенд, выполнила все необходимые команды из пункта 5.2.1. (рис. @fig:001)
   
![Подготовка лабораторного стенда](image/1.png){#fig:001 width=70%}

2. Вошла в пользователя guest. Создала программу simpleid.c командой touch (рис. @fig:002)

![Файл simpleid.c](image/2.png){#fig:002 width=70%}

3. Скомпилировала программу и убедилась, что файл программы создан(рис. @fig:003) 

![Файл скомпилирован](image/3.png){#fig:003 width=70%}

4. Выполнила программу simpleid командой ./simpleid. Выполнила системную программу id. Результат совпал(рис. @fig:004)
   
![Результаты запуска](image/4.png){#fig:004 width=70%}

5. Создала программу simpleid2.c, содержащую в себе усложненый код программы simpleid.c. (рис. @fig:005) 

![Программа simpleid2.c](image/5.png){#fig:005 width=70%} 

6. Скомпилировала и запустила simpleid2.c (рис. @fig:006).

![Результат работы simpleid2.c](image/6.png){#fig:006 width=70%}

7. От имени суперпользователя (перешла в него командой su) выполнила команды chown root:guest /home/guest/simpleid2 и chmod u+s /home/guest/simpleid2. Эти команды установили права над файлом суперпользователя (рис. @fig:007).

![Чтение файла](image/7.png){#fig:007 width=70%}

8. Выполнила проверку правильности установки новых атрибутов и смены владельца файла simpleid2 (рис. @fig:008).

![Проверка правильности](image/8.png){#fig:008 width=70%}

9. Запустила simpleid2 и id. Результат совпал (рис. @fig:009).
   
![Попытка стереть содержимое файла](image/9.png){#fig:009 width=70%}

10. Проделала тоже самое относительно SetGID-бита (рис. @fig:010).

![Изменение прав](image/10.png){#fig:010 width=70%}

11. Создала программу readfile.c (рис. @fig:011).

![Программа readfile.c](image/11.png){#fig:011 width=70%}

12. Откомпилировала её. Сменила владельца у файла readfile.c и изменила права так, чтобы только суперпользователь (root) мог прочитать его, a guest не мог.  Убедилась, что пользователь guest не может прочитать файл readfile.c (рис. @fig:012)

![Применение команд](image/12.png){#fig:012 width=70%}

13. Сменила у программы readfile владельца и установила SetU’D-бит (рис. @fig:013)

![Смена владельца и ограничений](image/13.png){#fig:013 width=70%}

14. Убедилась, что программа readfile может прочитать файл readfile.c (рис. @fig:014) и файл /etc/shadow (рис. @fig:015).

![Чтение файла readfile.c](image/14.png){#fig:014 width=70%}

![Чтение файла /etc/shadow](image/15.png){#fig:015 width=70%}

15.Приступила ко второй части работы. Выяснила, установлен ли атрибут Sticky на директории /tmp, для чего выполнила команду ls -l / | grep tmp и от имени пользователя guest создала файл file01.txt в директории /tmp со словом test(рис. @fig:016). 

![Применение команд, заполнение файла](image/16.png){#fig:016 width=70%}

16. Просмотрела атрибуты у только что созданного файла и разрешила чтение и запись для категории пользователей «все остальные» (рис. @fig:017).

![Просмотр и установка атрибутов](image/17.png){#fig:017 width=70%}

 17. От пользователя guest2 попробовала прочитать файл /tmp/file01.txt и дозаписать в файл слово test2. Снова проверила содержимое файла (рис. @fig:018). Файл получается прочитать, но не получается дозаписать в него текст. Команда его стирает и пишет новый

![Чтение и дозапись в файл](image/18.png){#fig:018 width=70%}

18. От пользователя guest2 записала в файл /tmp/file01.txt слово test3, стерев при этом всю имеющуюся в файле информацию командой, а затем прочитала его (рис. @fig:019). Команду выполнить удалось.

![Чтение и дозапись в файл](image/19.png){#fig:019 width=70%}

19. От пользователя guest2 попробовала удалить файл /tmp/file01.txt командой rm /tmp/fileOl.txt (рис. @fig:020). Команду выполнить не удалось.

![Попытка удалить файл](image/20.png){#fig:020 width=70%}

20. Повысила права до суперпользователя и выполнила после этого команду, снимающую атрибут t (Sticky-бит) с директории /tmp. Затем покинула режим суперпользователя и от пользователя guest2 проверьте, что атрибута t у директории /tmp нет. Затем снова попыталась удалить файл (рис. @fig:019). Файл удалить получилось.

![Повторная попытка удалить файл](image/21.png){#fig:021 width=70%}
---
# Выводы

В результате выполнения работы я изучила механизм изменения идентификаторов, применения SetUID- и Sticky-битов. Получила практические навыки работы в консоли с дополнительными атрибутами. Рассмотрела работы механизма смены идентификатора процессов пользователей, а также влияние бита Sticky на запись и удаление файлов 

# Библиография

1. [Методический материал] [https://esystem.rudn.ru/pluginfile.php/2090279/mod_resource/content/2/005-lab_discret_sticky.pdf]
2. [Сайт для поиска команд] [https://www.ibm.com/]
