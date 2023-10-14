---
## Front matter
title: "Лабораторная работа № 6"
subtitle: "Мандатное разграничение прав в Linux"
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
lot: false
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

Развить навыки администрирования ОС Linux. Получить первое практическое знакомство с технологией SELinux1. Проверить работу SELinx на практике совместно с веб-сервером Apache.

# Ход работы

1. Вошла в систему с полученными учётными данными и убедилась, что SELinux работает в режиме enforcing политики targeted (рис. @fig:001).

![Конфигурация SELinux](image/1.png){#fig:001 width=70%}

1. Обратилась с помощью браузера к веб-серверу, запущенному на моем компьютере, и убедилась, что он работает (рис. @fig:002).

![Обращение к веб-серверу](image/2.png){#fig:002 width=70%}

3. Нашла веб-сервер Apache в списке процессов, определила его контекст безопасности  (рис. @fig:003).

![Контекст безопасности веб-сервера Apache](image/3.png){#fig:003 width=70%}

4. Посмотрела текущее состояние переключателей SELinux для Apache (рис. @fig:004).

![Текущее состояние переключателей SELinux для Apache](image/4.png){#fig:004 width=70%}

5. Посмотрела статистику по политике с помощью команды seinfo (рис. @fig:005).

![Статистика по политике](image/5.png){#fig:005 width=70%}

6. Определила тип файлов и поддиректорий, находящихся в директории /var/www (рис. @fig:006).

![Тип файлов и поддиректорий, находящихся в директории /var/www](image/6.png){#fig:006 width=90%}

7. Определила тип файлов, находящихся в директории /var/www/html.
8. Определила круг пользователей, которым разрешено создание файлов в директории /var/www/html.

9. Создала от имени суперпользователя html-файл /var/www/html/test.html (рис. @fig:007)(рис. @fig:008) 

![Создание файла /var/www/html/test.html](image/7.png){#fig:007 width=70%}

![Создание файла /var/www/html/test.html](image/8.png){#fig:008 width=70%}

10. Проверила контекст созданного файла (рис. @fig:009)
![Работа с параметрами readfile](image/9.png){#fig:009 width=70%}
По умолчанию присваивается контекст unconfined_u:object_r:httpd_sys_content_t:s0

11. Обратилась к файлу через веб-сервер, введя в браузере адрес http://127.0.0.1/test.html. Убедилась, что файл был успешно отображён (рис. @fig:010).

![Файл test.html в браузере](image/10.png){#fig:010 width=70%}

12. Изучила справку man httpd_selinux и выяснила, какие контексты файлов определены для httpd. Сопоставим их с типом файла test.html.

13. Изменила контекст файла /var/www/html/test.html с httpd_sys_content_t на samba_share_t (рис. @fig:011).

![Изменение контекста](image/11.png){#fig:011 width=70%}

14. Попробовала ещё раз получить доступ к файлу через веб-сервер. В ответ получила запись Forbidden. You don't have permission to access /test.html on this server.

15. Просмотрела log-файлы веб-сервера Apache и системный лог-файл (рис. @fig:012).

![Содержимое логов](image/12.png){#fig:012 width=70%}
Мне не удалось получить доступ к файлу из-за измененного контекста.

17. Выполнила перезапуск веб-сервера. Сбоя не произошло.

18. Проанализировала лог-файлы.

19. Выполнила команду semanage port -a -t http_port_t -р tcp 81. После этого проверила список портов командой semanage port -l | grep http_port_t (рис. @fig:013).

![Попытка добавления порта 81 в список и вывод списка допустимых портов](image/13.png){#fig:013 width=70%}

20. Попробовала удалить привязку http_port_t к 81. Удаление невозможно. Удалила файл /var/www/html/test.html (рис. @fig:014).

![Попытка удаления привязки к порту 81. Удаление файла /var/www/html/test.html](image/14.png){#fig:014 width=70%}


# Выводы

В рамках данной лабораторной работы были развиты навыки администрирования ОС Linux. Получено первое практическое знакомство с технологией SELinux1. Проверена работа SELinx на практике совместно с веб-сервером Apache.


# Список литературы

[1][Методический материал] [https://esystem.rudn.ru/pluginfile.php/2090279/mod_resource/content/2/005-lab_discret_sticky.pdf]
[2][Методический материал] [https://esystem.rudn.ru/pluginfile.php/2090282/mod_resource/content/2/006-lab_selinux.pdf]
