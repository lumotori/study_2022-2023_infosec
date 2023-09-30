---
## Front matter
lang: ru-RU
title: Лабораторная работа 2
subtitle: Дискреционноеразграничение прав в Linux. Основные атрибуты
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
- Закрепление теоретических основ дискреционного разграничения доступа в современных системах с открытым кодом на базе ОС Linux

## Материалы и методы

- Процессор `pandoc` для входного формата Markdown
- Операционная система `Centos 7.0`
- Сервис для хостинга IT-проектов `GitHub`
- Методические материалы

# Результаты выполнения работы

## От имени пользователя guest определила расширенные атрибуты файла

![](image/1.png){#fig:001 width=70%}

## Установила права, разрешающие чтение и запись для владельца файла

![](image/2.png){#fig:002 width=70%}

## Попытка установки расширенного атрибута a от имени пользователя guest

![](image/3.png){#fig:003 width=70%}

## Повысила свои права с помощью команды su и установила атрибут

![](image/4.png){#fig:004 width=70%}

![](image/5.png){#fig:005 width=70%}

## Выполнила дозапись в файл file1 слова «test». После этого выполнила чтение файла file1 командой. Убедилась, что слово test было успешно записано в file1 

![](image/6.png){#fig:006 width=70%}

![](image/7.png){#fig:007 width=70%}

![](image/8.png){#fig:008 width=70%}

## Попробовала удалить файл file1 командой rm, стереть имеющуюся в нём информацию командой echo, переименовать файл командой mv

![](image/9.png){#fig:009 width=70%}

![](image/10.png){#fig:010 width=70%}

![](image/11.png){#fig:011 width=70%}

## Сняла расширенный атрибут a с файла и применила все вышеперечисленные операции

![](image/14.png){#fig:014 width=70%}

![](image/13.png){#fig:013 width=70%}

## Таблица с минимально необходимыми правами для выполнения операций внутри директории

![](image/15.png){#fig:015 width=70%}

![](image/16.png){#fig:016 width=70%}

# Вывод

В результате выполнения работы я повысила свои навыки использования интерфейса командой строки (CLI), познакомилась на примерах с тем, как используются основные и расширенные атрибуты при разграничении доступа. Имели возможность связать теорию дискреционного разделения доступа (дискреционная политика безопасности) с её реализацией на практике в ОС Linux.
